# 4.0 Classes
추상클래스 : 오직 다른 곳에서 상속받을수만 있는 클래스  
추상메소드를 만드려면 메소드를 클래스 안에서 구현해야 함  

메소드 : 클래스 안에 존재하는 함수  

추상메소드 : 추상클래스를 상속받는 모든 것들이 구현해야하는 메소드  

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
