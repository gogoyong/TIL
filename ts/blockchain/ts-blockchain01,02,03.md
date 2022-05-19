- 더 나은 개발 경험과 생산적인 개발을 원하는 JS 개발자를 위한 것

- 타입 `안정성`  

JS는 매우 유연한 언어임  

입력값의 타입, 입력값의 갯수 모두 컴파일 전에 확인할 수 있음.  
> 이런 보호장치 : `타입 추론`에 의함  

데이터와 변수 타입을 명시적으로 정의할 수 있고,
또는 JS처럼 변수만 생성하고 넘어가도 됨.(이럴 경우는 TS가 타입을 추론해 줌)  

```ts
const player : {
    name:string,
    age?:number
    // age : number | undefind
} = {
    name:'nico',
}
```
? : 선택적 변수(optional variable)

```ts
type Age = number;
type Name = string;
type Player = {
    name:Name,
    age?:Age
}

function playerMaker(name:string) : Player {
  // name 인자의 타입 지정, 그리고 playerMaker 함수의 타입 지정
    return {
        name
    }
}

const nico=playerMaker('nico')
nico.age = 12

```
화살표 함수 타입은 아래와 같이
```ts
const playerMaker = (name:string) : Player => ({name})
```

`readonly `타입 > push같이 내용을 변형시키는 것을 막음  
filter, map 등은 가능

: 즉 불변성을 갖게 함, JS에서는 없음  

`tuple`
: 정해진 갯수, 정해진 순서에 맞는 타입을 가진 배열(array)  

`any` : TS를 빠져나오는 방법  

TS의 type checker와 친해져야 함.  

unknown
```ts
let a:unknown;

if (typeof a==='number'){
    let b = a + 1
}


if(typeof a ==='string'){
    let b=a.toUpperCase();
}
```

void : 아무것도 return하지 않는 함수를 대상으로 사용  
```ts
function hello() {
    console.log('x')
}
// hello함수는 return하지않으므로 void타입임
```

never : 절대 return하지 않을 때 사용  
함수에서 예외가 발생할 때, 
``` ts
function hello():never {
    throw new Error('xxx')
}
```
```ts
function hello(name:string|number){
    if(typeof name === 'string'){
        name
    } else if (typeof name === 'number'){
        name
    } else {
        name
    }
}
```

# 3.0 Call signatures  
Call signature: 함수위에 마우스를 올렸을때 보임  
함수를 어떻게 호출해야하는 것인지 알려줌, 함수의 반환타입도 알려줌  
```ts
type Add = (a:number, b:number) => number;

const add:Add = (a,b) => a+b
```

# 3.1 overloading  
함수가 여러개의 call signatures를 갖고 있을때 발생함  

```ts
type Config = {
    path: string,
    state: object
}

type Push = {
    (path:string):void
    (config: Config) : void
}

const push:Push = (config) => {
    if (typeof config === 'string') console.log(config)
    else {
        console.log(config.path, config.state)
    }
}
```

```ts
type Add = {
    (a:number,b:number):number
    (a:number, b:number, c:number):number
}

const add:Add = (a,b,c?:number) => {
    if(c) return a+b+c
    return a+b
}
```

# 3.2 Polymorphism 다향성  
many structures (여러가지 다른 형태들)  
- concrete type : string, number, unknown, void 등등
- generic type: 타입의 `placeholder` (타입 추론)  
 => call signature작성시 여기에 들어올 타입을 확실히 알수 없을 경우 사용한다.  

 ```ts
 type SuperPrint = {
    <T>(arr:T[]) : T
}

const superPrint : SuperPrint = (arr) => arr[0]

const a = superPrint([1,2,3,4])
const b = superPrint([true,false,true])
const c = superPrint([1,2,true,false, 'hello'])
```

# 3.3 Generics Recap
타입스크립트는 generic을 처음 인식했을 때와  
generic의 순서를 기반으로 generic의 타입을 인식함  

# 3.4 Conclusions
```ts
type Player<E> = {
    name:string
    extraInfo:E
}
type NicoExtra = {
    favFood:string
}
type NicoPlayer = Player<NicoExtra>

const nico: NicoPlayer = {
    name:'nico',
    extraInfo : {
        favFood:'kimchi'
    }
}

const lynn: Player<null> = {
    name:'lynn',
    extraInfo:null
}
```
```ts
type A = Array<number>

let a:A = [1,2,3,4]
```


