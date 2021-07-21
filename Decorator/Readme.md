<h1>Decorator</h1>

O padrāo decorator é utilizado quando precisamos implementar comportamentos extras a objetos dinamicamente durante a execuçao.
O decorator permite voce estruturar sua logica de negocio em camadas com enfase em composiçāo ao em vez de multiplas heranças.


<h2>Exemplo</h2>

 ![Decorator](https://user-images.githubusercontent.com/55807714/126417750-fd1d98a7-fd22-4d3b-a7d6-4a96703e2d8e.png)

  
  
  
  
  <h3>Classe AlugarCarro</h3>
  
  ```Java
  public abstract class AlugarCarro (Componente){
	String descricao = "Carro desconhecido";
	
	public String getDescricao() {
		return descricao;
	}
	
	public abstract int calcularPreco();
}

  
  ```
  
  <h3>Classe AlugarFerrari (ComponenteConcreto)</h3>
  
  
  ```Java
  public class AlugarFerrari extends AlugarCarro{

	public AlugarFerrari() {
		this.descricao = "Carro Ferrari";
	}
	
	public int calcularPreco() {
		
		return 400000;
	}
	
}
  
  ```
  
   <h3>Classe AdicionaisOpcionais (Decorator)</h3> 
  
  ```Java
  
  public abstract class AdicionaisOpcionais extends AlugarCarro {
	public abstract String getDescricao();
}


  ```
  
  <h3>Classe AddSeguro (Decorator Concreto)</h3>
  
  ``` Java
  public class AddSeguro extends AdicionaisOpcionais{
	
	AlugarCarro carro;
	
	public AddSeguro(AlugarCarro carro) {
		this.carro = carro;
	}
	
	public String getDescricao() {
		return carro.getDescricao() + ", incluindo seguro";
	}
	
	public int calcularPreco() {
		return carro.calcularPreco() + 70000;
	}
	
}
  
  ```
  
  <h3>Classe AddGPS (Decorator Concreto)</h3>
  
  ```Java
  public class AddGPS extends AdicionaisOpcionais{
	
	AlugarCarro carro;
	
	public AddGPS(AlugarCarro carro) {
		this.carro = carro;
	}
	
	public String getDescricao() {
		return carro.getDescricao() + ", incluindo GPS";
	}
	
	public int calcularPreco() {
		return carro.calcularPreco() + 10000;
	}
	
}
  ```
  
  
  <h3>Classe AddCadeirinhaBebe (Decorator Concreto)</h3>
  
  ```Java
  public class AddCadeirinhaBebe extends AdicionaisOpcionais{
	
	AlugarCarro carro;
	
	public AddCadeirinhaBebe(AlugarCarro carro) {
		this.carro = carro;
	}
	
	public String getDescricao() {
		return carro.getDescricao() + ", incluindo Cadeirinha para Bebe";
	}
	
	public int calcularPreco() {
		return carro.calcularPreco() + 30000;
	}
	
}

  ```
  
