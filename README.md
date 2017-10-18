# corejava
package example;

public class Employee {
	private String name;
	private double salary;
	
	public Employee(String name, double salary) {
		super();
		this.name = name;
		this.salary = salary;
	}
	public String getName() {
		return name;
	}
	public void setName(String name) {
		this.name = name;
	}
	public double getSalary() {
		return salary;
	}
	public void setSalary(double salary) {
		this.salary = salary;
	}
	public void raiseSalary(double percent)
	{
		double raise = salary*percent/100;
		salary=salary+raise;
	}
	public double dummyMethod()
	{
		System.out.println("Hi from Employee");
		return 10000;
	}
	
}
package example;

public class Manager extends Employee {
	private double bonus;

	public double getBonus() {
		return bonus;
	}

	public void setBonus(double bonus) {
		this.bonus = bonus;
	}

	public Manager(String name, double salary) {
		super(name, salary);
		// TODO Auto-generated constructor stub
		bonus=0;
	}
	public double getSalary()
	{
		double baseSalary = super.getSalary();
		System.out.println("hi in manager");
		return baseSalary + bonus;
		
	}
	public double dummyMethod()
	{
		System.out.println("hi from manager");
		return 20000;
	}
	
}
package example;
public class ManagerTest {
	public static void main(String[] args)
	{
		Manager m=new Manager("Ram", 50000);
		m.setBonus(10000);
		Employee[] e=new Employee[3];
		e[0]=m;
		e[1]= new Employee("Kavitha",20000);
		e[2]= new Employee("Satya",20000);
		for(Employee e1:e)
		{
			System.out.println("salary of "+e1.getName()+"is>>>  "+e1.getSalary());
		}
		Employee e2=new Manager("kalyan",200000);
		System.out.println(((Employee)e2).dummyMethod());
	}
}
