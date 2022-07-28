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

