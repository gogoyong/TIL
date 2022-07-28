## TypeScript
- JS는 타입 안정 언어가 아니다.
- JS에서는 ["hello"]+{hi+1} 과 같은 코드가 실행된다.

## Runtime Error
 - 코드가 **실행되는 동안** 일어나는 에러

- TS : JS로 컴파일됨
- TS에서 변수의 **타입을 항상 지정해주지 않아도** 된다.
 : **TS가 종종 타입을 추론**해주기 때문 (infer)
 
 const x : string = "hi" 
 이와 같이 설정한다.
 
 
## Call signatures
- type을 만들 수 있고, 함수를 구현하기 전에, 함수가 어떻게 작동하는지 서술해둘 수 있음.
즉, 파라미터와 함수의 타입을 지정해두는 것임.
```ts
type Add = (a:number, b:number) => number;

const add:Add = (a, b) => a + b
```
## overloading
- 함수가 여러 개의 call signature을 가지고 있을 경우 발생

## polymorphism
many(poly) structures(morphism)  
- 우리가 코드를 작성하고, 함수를 구현하고 사용할 때는 concrete type을 사용해야 함  
(ex. boolean, string, number .. )

- call signature 작성 시 concrete type을 알 수 없을 때 `generic`을 사용함  
```ts
type SuperPrint = {
 <TypePlaceholder>(arr: TypePlaceholder[]) : TypePlaceHolder
}
```

## generic 사용 시 placeholder는 call signature를 요구하는 대로 생성함 (타입 추론)
```ts
type SuperPrint <T,M>(a: T[], b:M) => T

const superPrint: SuperPrint = (a) => a[0]

const a = superPrint([1,2,3,4], "x")
```

- 라이브러리를 만들거나, 다른 개발자가 사용할 기능을 개발하는 경우 제네릭이 유용
- 그 외 대부분의 경우 제네릭을 만들기보다는 사용하는게 대부분임.

type으로 선언한 부분을 아래와 같이도 표시할 수 있음.(같은 결과)
```ts
function superPrint<T>(a: T[]) {
 return a[0]
}
```

제네릭을 사용하여 타입을 생성하고 타입 안에 그것을 넣어줄 때도 사용할 수 있음
number[] 을 Array<number> 과 같이 사용할 수도 있음.
 
