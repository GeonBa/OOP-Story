# 🏫The Class🏫

<hr />

### 일반화  `generalization`

- 특수한 것에서 일반적이며 공통적인 것을 끌어낸다는 것
- `A는 B의 일종이다`
- 특수한 개념 -> 일반적인 개념



### 특수화 `specialization`

- 일반적이고 공통적인 것에서 좀 더 특수한 것을 끌어내는 것



### 상속 `inheritance`

- 일반적인 개념 -> 특수한 개념
- 일반화와 특수화 관계를 구현하는 방법



### 상속의 종류

- 구현 상속 `implementation inheritance`
  - 자식 클래스는 부모 클래스가 구현한 특성이나 메서드를 상속 받음
- 인터페이스 상속 `interface inheritance`
  - 부모 클래스가 인터페이스인 경우, 자식 클래스는 부모 클래스로부터 구현 코드를 상속 받는 것이 아닌, 부모 클래스에서 정의한 일종의 계약 사항만을 상속 받아 수행 --> 실현 `realization`



### 저스트 상속

- EX1)

  ```
  class Parent {
  	private long money;
  	public long getFinancialCondition() {
  		return money;
  	}
  }
  
  class Child extends Parent {
  
  }
  ```

- Child 클래스는 Parent 클래스의 멤버와 인스턴스를 사용할 수 있음
- Parent Class
  - 부모 클래스 `parent class`
  - 수퍼 클래스 `super class`
  - 기초 클래스 `child class`
- Child Class
  - 자식 클래스 `child class`
  - 서브 클래스 `sub class`
  - 파생 클래스 `derived class`
- EX1의 코드에서는 부모 클래스의 멤버가 private임으로 Child class에서 멤버값을 사용할 수 없다.



- EX2)

  ```
  class Parent {
  	private long money;
  	public long askMoney(long amount){
  		if(amount > 10000){
  			amount = 10000;
  		}
  		money -= amount;
  		return amount;
  	}
  	
  	public long getFinancialCondition(){
  	
  	}
  }
  
  class Child extends Parent {
  	public void useMoney() {
  		long receiveMoney = askMoney(20000);
  	}
  }
  ```

  - private로 멤버가 생성되었기 때문에 아직도 사용하려면, 메서드를 이용해야 한다. 이런 경우 private -> protected로!!











