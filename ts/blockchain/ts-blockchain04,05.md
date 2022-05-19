# 4.0 Classes
추상클래스 : 오직 다른 곳에서 상속받을수만 있는 클래스  
추상메소드를 만드려면 메소드를 클래스 안에서 구현해야 함  

메소드 : 클래스 안에 존재하는 함수  

추상메소드(abstract method) : 추상클래스를 상속받는 모든 것들이 구현해야하는 메소드  

private 필드 대신 `protected`를 사용하면  
내부의 `다른 자식 클래스에서 사용할 수 있음`  

```ts
abstract class User {
    constructor(
        protected firstName:string,
        protected lastName:string,
        protected nickname:string
    ) {}
    abstract getNickName():void
    getFullName() {
        return `${this.firstName} ${this.lastName}`
    }
}

class Player extends User{
    getNickName() {
        console.log(this.nickname)
    }
}

const nico = new Player('nico','las','니꼬')

nico.getFullName()
```

---
# 4.1 Recap  
```ts
type Words = {
    [key:string] : string
    // 타입 생성
}



class Dict {
    private words: Words
    // property 만들기
    constructor(){
        this.words = {}
        // 초기화
    }
    add(word:Word){
        if(this.words[word.term] === undefined) {
            this.words[word.term] = word.def;
        }
    }
    def(term:string) {
        return this.words[term]
    }
}

class Word {
    constructor (
        public term: string,
        public def : string
    ) {}
}

const kimchi = new Word('kimchi', '한국의 음식')

const dict = new Dict()

dict.add(kimchi);
dict.def('kimchi')
```
---
# 4.2 Interfaces

type은 다양하게 설정할 수 있음.
```ts
type Nickname = string
type Health = number
type Friends = Array<string>
type Player = {
    nickname:Nickname,
    healthBar:Health
}

const nico : Player = {
    nickname : 'nico',
    healthBar:10
}

type Food = string;

const kimchi:Food = 'delicious'
```

타입을 특정값으로 제한할 수 있음
```ts
type Team = "read" | "blue" | "yellow"
type Health = 1 | 5 | 10

type Player = {
    nickname:string,
    team:Team
    health: Health
}

const nico : Player = {
    nickname:'ncio',
    team: 'yellow',
    health:10
}
```

인터페이스 keyword : 오직 `객체(object)의 모양을 결정해주는 용도로만` 사용  
```ts
interface Player {
    nickname:string,
    team:Team
    health: Health
}
    
interface Person {
    nickname:string,
    team:Team
    health: Health
}
```

```ts
interface User {
    name:string
}

interface Player extends User{}

const nico : Player = {
    name:'nico'
}

// 위와 아래는 동일한 의미를 가짐
type User = {
    name:string
}

type Player = User & {}

const nico : Player = {
    name:'nico'
}
```
인터페이스는 각각의 타입들을 합칠 수 있다.  
(type으로는 불가능함)  
```ts
interface User {
    name:string
}

interface User{
    lastName:string
}

interface User {
    health:number
}

const nico : User = {
    name:'nico',
    lastName:'2',
    health:1
}
```
인터페이스는 객체지향 프로그래밍 개념을 활용해서 디자인함  
타입은 조금 더 개방적임.  

