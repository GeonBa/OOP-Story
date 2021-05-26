# 🏫The Class🏫

<hr />



### 주요 키워드!!

> 객체는 혼자서 사용될 수 없습니다!, 객체는 객체를 사용할 다른 객체와의 관계를 맺음으로서 가치가 있는 겁니다!!



### 종속 관계 `dependency`

- 객체가 다른 객체를 일방적으로 사용함!!

- 하나의 객체의 사용이 변경되면 그것을 사용하는 다른 객체에 영향을 미치는 상태를 나타내는 관계

  ```
  class RepairMan {
  	public void Repair(Car repairCar){
  	
  	}
  }
  ```

- 메서드 내부에서만 살아있는 개체를 사용하는 경우에도 종속관계가 성립될 수 있다!!

  ```
  class OwnerDriver {
  	private Car myCar;
  	public void Repair() {
  	
  	}
  }
  ```

  



### 연관 관계 `association`

- 객체가 다른 객체를 소유할 수도 있고, 소유하지 않을 수도 있는 관계

  ```
  class Driver {
  	private Car myCar;
  	public void ChangeCar(Car newCar){
  		mycar = newCar;
  	}
  }
  ```

- 연관 관계는 일반적으로 단방향일 수 있지만, 대게는 양방향성을 갖는다.

  ```
  class Car {
  	private Driver myOwner;
  	public ChangeOwner(Drive owner){
  		myOwner = owner;
  	}
  }
  
  class Driver {
  	private Car myCar;
  	public void ChangeCar(Car newCar){
  		myCar = newCar;
  		myCar.ChangeOwner(this);
  	}
  }
  ```

  - 각 class에서 상대 클래스를 참조할 수 있는 메서드가 존재!!

  - 다수성 `multiplicity`

    ```
    import java.util.*;
    
    class Deiver {
    	private Vector myCars = new Vector();
    	public void AddNewCar(Car newCar){
    		myCars.add(newCar);
    		newCar.ChangeOwner(this);
    	}
    	
    	public void RemoveCar(Car oldCar){
    		myCars.remove(oldCar);
    	}
    }
    ```

    - 하나의 객체가 다른 객체를 다수 가질 수 있습니당!!



### 일반화 관계 `generalization`

- 특수한 것에서 일반적이고 공통적인 개념을 이끌어낼 수 있는 관계



### 특수화 관계 `specialization` == 상속 관계 `inheritance`

- 일반적이고 공통적인 관계에서 특수한 것을 이끌어낼 수 있는 관계



### 관계란?

> 객체 사이의 연결



### 전체-부분 관계 `whole-part` 

- 집합 `aggregation`

  ```
  class Car {
  	private Tire [4] tires;
  	public void FixNewTire(int index, Tire newTire) {
  		if( index < 0 || index > 3 ){
  			return;
  		} 
  		
  		tires[index] = newTire;
  	}
  }
  ```

  - 객체가 다른 객체의 일부분을 구성

### 복합 관계 `composition`

- 더 많은 제한이 있는 집합 관계의 특별한 경우

- 전체는 부분을 확고하게 소유

  - 전체 객체가 복사되거나 삭제되면 부분도 복사되거나 삭제
  - 전체에서 부분으로 방향성을 가져야함!!ㄴ

  ```
  class Car {
  	private Engine theEngine;
  	public Car(Engine new Engine) {
  		if (newEngine == null){
  			newEngine = newEngine();
  		}
  		theEngine = newEngine;
  	}
  	
  	public void ChangeEngine(Engine newEngine) {
  		theEngine = newEngine;
  	}
  	
  	public void fixEngine() {
  	
  	}
  }
  ```

  - 자바에서는 객체가 소멸되도 GC에 의해 자동으로 수거됨!!



### 참조란?

> 참조는 별명 `alias`입니다. 자바언어에서도 객체가 생성되면 메모리가 할당됩니다. 그 메모리의 시작 주소가 참조 변수가 저장되는 것이 아니라, 할당된 메모리 위치 정보에 다른 이름(별명)을 붙여서 사용합니다. new 키워드는 참조 정보를 반환하고, 참조 변수에 반환된 참조 정보를 저장한 후에 이 변수를 통해 해당 인스턴스(=객체)에 접근할 수 있게 합니다. 결국 참조 변수에는 객체에 할당된 메모리 위치 정보가 저장됩니다.

- new 키워드를 사용하여 객체를 생성
  - 객체의 인스턴스 데이터를 저장할 수 있는 메모리 필요
    - 클래스에 정의된 크기 만큼의 메모리를 할당



### 레퍼런스 `reference`

- 포인트 변수와 같이 다른 변수나 클래스 인스턴스의 시작 주소를 저장하지만, 포인터 연산을 하지 않는 편리함을 제공

- 일종의 `alias`

- 초기화된 변수나 클래스의 인스턴스와 영원한 관련성을 맺음

  - 원래의 변수나 클래스의 인스턴스가 소멸될 때까지
  - 레퍼런스는 항상 초기화되어야 함!!

- 참조변수를 사용

  ```
  Car myCar;
  myCar = new Car();
  ```

- 레퍼런스!!

  ```
  Car myCar = new Car();
  ```

  

### 메서드 호출에서 인수 전달 방법

- 메서드가 작동할 때 필요한 정보를 전달해야 함

  - 매개변수 파라미터 `parameter`를 통해 인수`argument`로 메서드에게 넘김

- 값으로 호출 `call by value`

  - 메서드를 호출한 측의 변수나 클래스 인스턴스, 객체의 복사본이 인수로 메서드에 전달 
    - 복사본 인수의 값을 변경시키더라도 메서드를 호출한 측의 변수나 클래스 인스턴스에는 아무런 영향이 없음

- 참조로 호출 `call by referebce`

  - 메서드를 호출한 측의 변수나 객체의 레퍼런스 또는 참조 정보가 인수로 메서드에 전달
    - 참조 정보 인수의 값을 변경시키면 참조되는 변수나 클래스 인스턴스가 변경되므로 메서드를 호출한 측의 변수나 클래스 인스턴스에 영향을 미침

  

### 스택 메모리

- 메서드에 전달되는 인수는 스택 메모리에 저장
  - 메서드의 인수 뿐만 아니라 지역 변수도 저장



### 자바의 호출 방식

- 참조로 호출 방식을 제공하지 않음

- 모든 인수는 값으로 호출 방식으로 전달

  - 호출 측의 클래스 인스턴스의 참조 값 그 자체는 값으로 호출 방식으로 메서드에 전달

- 메서드의 인수가 참조 데이터 타입 

  ```
  class Car {
  	public int number;
  	public Car() {
  		number = 0;
  	}
  	
  	class Test {
  		public void Method(Car r){
  			r.number = 100;
  		}
  	}
  	public void Foo() {
  		Car myCar = new Car();
  		Method(myCar);
  		System.out.println(myCar.number);
  	}
  }
  ```

  - Method()의 매개변수인 참조 변수 r에는 값으로 호출 방식으로 myCar 참조 변수 값이 인수로 전달되는 것

- 참조 정보 변경

  ```
  public void Method(Car r){
  	r = new Car();
  	r.number = 100;
  }
  ```



### JAVA의 인수 전달 방법

> 값으로 호출하면서, 클래스 타입을 갖는다. 더불어 새 참조는 불가능하지만, 멤버 변경은 가능하다.!!



































