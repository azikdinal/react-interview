В TypeScript вы можете добавлять модификаторы доступа к свойствам и методам класса, чтобы определить их уровень доступа извне класса. Модификаторы доступа позволяют контролировать, какие части кода могут читать и изменять свойства класса, а также вызывать его методы.

В TypeScript есть три модификатора доступа: `public`, `private` и `protected`. Вот как они работают:

1. `public`: Это модификатор доступа по умолчанию. Свойства и методы, объявленные с модификатором `public`, доступны из любого места в программе.
```typescript
class Person {
  public name: string;
  
  public constructor(name: string) {
    this.name = name;
  }

  public greet() {
    console.log(`Hello, my name is ${this.name}.`);
  }
}
```
В этом примере свойство `name` и метод `greet()` объявлены с модификатором `public`. Они могут быть доступны извне класса, и объекты класса могут читать и изменять значение `name` и вызывать метод `greet()`.

2. `private`: Свойства и методы, объявленные с модификатором `private`, доступны только внутри класса. Они не могут быть доступны извне класса или его потомков.
```typescript
class Person {
  private age: number;
  
  constructor(age: number) {
    this.age = age;
  }

  private getAge() {
    return this.age;
  }
}
```
В этом примере свойство `age` и метод `getAge()` объявлены с модификатором `private`. Они могут быть использованы только внутри класса `Person`, и объекты класса не могут напрямую читать или изменять значение `age` или вызывать метод `getAge()`.

3. `protected`: Свойства и методы, объявленные с модификатором `protected`, доступны внутри класса и его потомков, но не доступны извне класса или его потомков.
```typescript
class Person {
  protected address: string;
  
  constructor(address: string) {
    this.address = address;
  }

  protected getAddress() {
    return this.address;
  }
}
```
В этом примере свойство `address` и метод `getAddress()` объявлены с модификатором `protected`. Они могут быть использованы внутри класса `Person` и его потомков, но не доступны извне.

Модификаторы доступа позволяют контролировать уровень доступа к свойствам и методам класса, что помогает обеспечить инкапсуляцию, безопасность и гибкость при разработке приложений.