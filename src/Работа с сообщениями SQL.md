Для получения ID затронутой строки внутри триггера можно использовать специальную переменную `NEW` или `OLD`, в зависимости от типа операции. 

В случае операций INSERT и UPDATE, переменная `NEW` содержит новую версию строки, а в случае операции DELETE - переменная `OLD` содержит старую версию строки.

Вот пример, как можно получить ID затронутой строки внутри вашей функции `notify_users_changes()`:

```sql
CREATE OR REPLACE FUNCTION notify_users_changes() RETURNS TRIGGER AS $$
DECLARE
  affected_id INTEGER;
BEGIN
  IF (TG_OP = 'INSERT') THEN
    affected_id := NEW.id; -- Предполагаем, что у вас есть столбец `id`
    PERFORM pg_notify('users_changes', 'insert:' || affected_id);
  ELSIF (TG_OP = 'UPDATE') THEN
    affected_id := NEW.id;
    PERFORM pg_notify('users_changes', 'update:' || affected_id);
  ELSIF (TG_OP = 'DELETE') THEN
    affected_id := OLD.id;
    PERFORM pg_notify('users_changes', 'delete:' || affected_id);
  END IF;
  
  RETURN NULL;
END;
$$ LANGUAGE plpgsql;
```

В этом примере, я добавил переменную `affected_id`, которая будет содержать ID затронутой строки. Затем, для операций INSERT и UPDATE, я присваиваю значение `NEW.id` переменной `affected_id`, а для операции DELETE - `OLD.id`. После этого, я добавил `affected_id` в сообщение уведомления, чтобы передать информацию об ID затронутой строки.

Обратите внимание, что предполагается, что у вас есть столбец `id` в таблице пользователей, и вы можете заменить `id` на имя конкретного столбца, содержащего ID в вашей таблице.