# π«The Classπ«

<hr />

### μΌλ°ν  `generalization`

- νΉμν κ²μμ μΌλ°μ μ΄λ©° κ³΅ν΅μ μΈ κ²μ λμ΄λΈλ€λ κ²
- `Aλ Bμ μΌμ’μ΄λ€`
- νΉμν κ°λ -> μΌλ°μ μΈ κ°λ



### νΉμν `specialization`

- μΌλ°μ μ΄κ³  κ³΅ν΅μ μΈ κ²μμ μ’ λ νΉμν κ²μ λμ΄λ΄λ κ²



### μμ `inheritance`

- μΌλ°μ μΈ κ°λ -> νΉμν κ°λ
- μΌλ°νμ νΉμν κ΄κ³λ₯Ό κ΅¬ννλ λ°©λ²



### μμμ μ’λ₯

- κ΅¬ν μμ `implementation inheritance`
  - μμ ν΄λμ€λ λΆλͺ¨ ν΄λμ€κ° κ΅¬νν νΉμ±μ΄λ λ©μλλ₯Ό μμ λ°μ
- μΈν°νμ΄μ€ μμ `interface inheritance`
  - λΆλͺ¨ ν΄λμ€κ° μΈν°νμ΄μ€μΈ κ²½μ°, μμ ν΄λμ€λ λΆλͺ¨ ν΄λμ€λ‘λΆν° κ΅¬ν μ½λλ₯Ό μμ λ°λ κ²μ΄ μλ, λΆλͺ¨ ν΄λμ€μμ μ μν μΌμ’μ κ³μ½ μ¬ν­λ§μ μμ λ°μ μν --> μ€ν `realization`



### μ μ€νΈ μμ

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

- Child ν΄λμ€λ Parent ν΄λμ€μ λ©€λ²μ μΈμ€ν΄μ€λ₯Ό μ¬μ©ν  μ μμ
- Parent Class
  - λΆλͺ¨ ν΄λμ€ `parent class`
  - μνΌ ν΄λμ€ `super class`
  - κΈ°μ΄ ν΄λμ€ `child class`
- Child Class
  - μμ ν΄λμ€ `child class`
  - μλΈ ν΄λμ€ `sub class`
  - νμ ν΄λμ€ `derived class`
- EX1μ μ½λμμλ λΆλͺ¨ ν΄λμ€μ λ©€λ²κ° privateμμΌλ‘ Child classμμ λ©€λ²κ°μ μ¬μ©ν  μ μλ€.



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

  - privateλ‘ λ©€λ²κ° μμ±λμκΈ° λλ¬Έμ μμ§λ μ¬μ©νλ €λ©΄, λ©μλλ₯Ό μ΄μ©ν΄μΌ νλ€. μ΄λ° κ²½μ° private -> protectedλ‘!!











