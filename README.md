# Typechain

Learing Typescript by making a blockchain with it.

## TypeScript 특징

### 1️⃣ Types

파라미터와 리턴값에 `타입`을 선언하여 보다 예측 가능하게 프로그래밍을 할 수 있다.

```ts
const name: string = 'bora';

const sayHello = (name: string): void => console.log(`Hi, ${name}`);
```

### 2️⃣ Optional Parameter

선언한 함수의 파라미터 개수와 함수가 실행될 때 파라미터 개수가 일치하지 않으면 에러가 난다.  
 파라미터 뒤에 `?`를 붙이면 해당 파라미터는 옵션이 되어, 함수 실행시 파라미터가 없어도 에러가 발생하지 않는다.

```ts
const greeting = (name: string, age?: number): string =>
  `I'm ${name}. I'm ${age} years old!`;
greeting('bora');
```

### 3️⃣ Interface

`interface`를 통해서 `Object`의 속성값의 type을 설정할 수 있다.
interface는 typescript에서만 작동한다.(JS로 변환 시켰을때에는 없어짐)

```ts
interface Human {
  name: string;
  age: number;
  gender: string;
}
const person = {
  name: 'bora',
  gender: 'female',
  age: 22,
};
```

### 4️⃣ class

객체를 만드는 방법중 또다른 방법 class와 typescipt에 대해 알아보자.  
 Typescript에서 `class`를 사용할때 `접근제한자`를 사용하여 속성을 설정할 수 있다.  
 `private` 속성일 경우 class 밖에서는 속성을 사용할 수 없다.
이를 통해 객체의 속성을 보호할 수 있다.  
 또한 `생성자 함수`에서는 일반함수와 마찬가지로 파라미터의 type을 설정해야한다.  
 interface의 경우 컴파일 후 js 코드에서는 완전히 사라지지만
class는 타입과 접근제한자를 제외한 것은 그대로 js코드에 남아 있다.

```ts
class Human {
  public name: string;
  public age: number;
  public gender: string;
  constructor(name: string, age: number, gender: string) {
    this.name = name;
    this.age = age;
    this.gender = gender;
  }
}

const bora = new Human('Bora', 18, 'female');
```
