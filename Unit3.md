# 🏫The Class🏫

<hr />



### 객체

- 캡슐화라고 하는 객체지향의 원리를 구체화한 것
- 클래스의 인스턴스
- 클래스에 정의된 사항을 모두 충족하는 하나의 경우



### 추상화 `abstraction`

> 중요하고 필수적인 사항을 중심으로 그 이미지나 관념을 표현 하는 것

### 클래스

> 객체에 대한 추상화 작업의 결과, 객체의 추상화

```
class Car {
	private int body;
	private int engine;
	private int steering;
	private int transmission;
	private int wheel;
	
	public void start(){
	
	}
	
	public void stop(){
	
	}
	
	public accelerate(){
	
	}
	
	public slowDown(){
	
	}
	
	public turnLeft(){
	
	}
	
	public turnRight(){
	
	}
}

// Field = 특성
// Method = 행위
```



- new
  - 자바 언어에서 클래스의 인스턴스를 생성할 때 `new` 키워드를 사용
    - 참조 `reference` 정보를 반환
    - 참조 `reference` == 별명 `alias`
  - 객체를 생성할 때 해당 객체에 대하여 메모리 자동 할당
    - 할당된 메모리 위치 정보에 `alias`를 붙여서 사용
  - `new`는 참조 정보를 반환
    - 참조 변수에 반환된 참조 정보를 저장한 후에 해당 인스턴스를 접근할 수 있음
  - 변수에는 객체에 할당된메모리 위치 정보가 저장



- 인스턴스의 소명
  - gc `garbage collector`를 통해 인스턴스를 수거
    - JVM에 의해 자동으로 수행



- 초기화와 생성자

  - 클래스의 인스턴스가 생성되면 해당 객체의 특성 정보는 유효한 값으로 초기화되어야 함!!

  - 원하는 값으로 멤버를 초기화할 수 있도록 생성자 `constructor` 정의 가능

    - 클래스의 인스턴스가 생성될 때 자동적으로 호출되어 특성을 초기화하는 기능을 수행하는 특수한 멤버 함수 또는 메서드

  - 디폴트 생성자

    - 클래스에 생성자를 정의하지 않았을 때 각 언어에서 기본적으로 제공해주는 생성자

    ```
    Date (int yy, int mm, int dd){
    	year = yy;
    	month = mm;
    	day = dd;
    }
    
    Date myDate = new Date(2001, 12, 8);
    ```

    

- 소멸자 `destructor`

  - 인스턴스가 소멸될 떄 뒷정리를 하는 역할

  ```
  protected void finalize() throws Throwable {
  	super.finalize();
  }
  ```

  

- 인스턴스 데이터 `instance data`

  - 인스턴스의 데이터 멤버 또는 필드에 각각 서로 다른 데이터가 저장

  ```
  Date myDate = new Date(2001, 12, 8);
  Date yourDate = new Date(2003, 11, 7);
  ```

  

- 인스턴스를 구별하는 것

  - `this`
  - 해당 메서드가 호출한 인스턴스가 자신을 호출했는지 알기 위해 `this` 키워드 사용

  ```
  Date (int yy, int mm, int dd){
  	this.year = yy;
  	this.month = mm;
  	this.day = dd;
  }
  ```

  

- 공유되는 인스턴스를 관리하는 법

  - 공유 멤버 `shared member`
  - 정적 멤버 `static member`
  - 클래스의 어떤 하나의 인스턴스에만 속해있는 것이 아니라, 전체로서 클래스에 속하여 해당 클래스의 모든 인스턴스에 공유되는 멤버

  ```
  class SavingAccount {
  	private char name[20];
  	private double amount;
  	private static double interestRate;
  }
  ```

  - 정적 멤버의 선언과 함께 초기 값을 지정

    ```
    private static double interestRate = 0.01;
    ```

  - 정적 코드 블럭

    ```
    class SavingAccount {
    	private char name[20];
    	private double amount;
    	private static double interestRate;
    	static {
    		interestRate = 0.01;
    	}
    }
    ```

  

  ### 객체 사이의 관계

  > 하나의 소프트웨어 시스템은 여러 클래스의 여러 인스턴스들 사이의 상호 관계로 구성

  

  - 메시지 보내기 `sending message`

    - 객체지향 언어에서 메서드 호출로 구현

    - 어떤 객체가 상대 객체에게 메시지를 보내기 위해서 상대 객체가 어떤 메시지를 받을 수 있는 알아야 함

      - 상대 객체는 자신이 받을 수 있는 메시지를 결정할 수 있음

    - 외부에 공개되는 메서드를 통해서만 해당 객체에게 메시지를 보낼 수 있음

      - 접근 지정자 `access specifier`를 통해 메서드를 외부에 공개시킬 것인지 결정

        ```
        class Car {
        	private int body;
        	private int engine;
        	private int steering;
        	private int transmission;
        	private int wheel;
        	
        	public void start(){
        	
        	}
        	
        	public void stop(){
        	
        	}
        	
        	public accelerate(){
        	
        	}
        	
        	public slowDown(){
        	
        	}
        	
        	public turnLeft(){
        	
        	}
        	
        	public turnRight(){
        	
        	}
        }
        
        // Field = 특성
        // Method = 행위
        ```

  - 인스턴스의 범위

    - 인스턴스에 저장되는 데이터가 우리가 생각했던 범위보다 높거나, 적으면 어떻게 해야 될까?

      ```
      Date myDate;
      myDate.month = 13;
      ```

      - 비공개 멤버로 지정하여, 데이터를 보호

        

        ```
        myDate.setMonth = 13;
        ```

        

        





















