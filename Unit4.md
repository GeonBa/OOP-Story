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
