- 멀티프로세스 : OS에서 여러가지 프로그램을 실행하는 것  
- 멀티스레드 : 하나의 프로세스(실행된 프로그램)에서 여러 동작을 동시에 하게 할 때 쓰는 방식  

- Prop을 받고, return으로 반환해줌 : 외부자를 위한 데이터  
- state도 인풋되어 return으로 반환해줌  : 내부자를 위한 데이터  

```jsx
import {useState} from 'react'

const[mode, setMode] = useState('WELCOME')
```
