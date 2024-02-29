1.	Encapsulation is the bundling of data and methods that operate on the data into a single unit, called a class. It hides the internal state of an object from the outside world and only exposes the necessary functionality through well-defined interfaces. 
Create an Employee class having data members' Name, Eid, and Basic_Salary, to calculate the HRA is 20% of Basic Salary and DA is 25% of Basic salary and MA is 300 rupee. implement the following queries:
  a) Display the name and gross salary of an employee whose name starts With 'n'
  b).Display the Eid and gross salary whose Eid is equal to 107.
  c)  Count the total number of employees whose salary more than 20000/-


Answer ==>



public class Employee {
    private String name;
    private int eid;
    private double basicSalary;

    public Employee(String name, int eid, double basicSalary) {
        this.name = name;
        this.eid = eid;
        this.basicSalary = basicSalary;
    }

    public double calculateGrossSalary() {
        double hra = 0.2 * basicSalary;
        double da = 0.25 * basicSalary;
        double ma = 300;
        return basicSalary + hra + da + ma;
    }

    // Getters for name and eid
    public String getName() {
        return name;
    }

    public int getEid() {
        return eid;
    }

    
    public static void main(String[] args) {
        
        Employee[] employees = {
                new Employee("John", 101, 25000),
                new Employee("Nancy", 102, 30000),
                new Employee("David", 103, 18000),
                new Employee("Nora", 104, 22000),
                new Employee("Emma", 105, 28000),
                new Employee("Nick", 106, 21000),
                new Employee("Neil", 107, 24000)
        };

        // a) Display the name and gross salary of an employee whose name starts With 'n'
        System.out.println("Employees whose name starts with 'N':");
        for (Employee emp : employees) {
            if (emp.getName().toLowerCase().startsWith("n")) {
                System.out.println("Name: " + emp.getName() + ", Gross Salary: " + emp.calculateGrossSalary());
            }
        }

        // b) Display the Eid and gross salary whose Eid is equal to 107
        System.out.println("\nEmployee with Eid 107:");
        for (Employee emp : employees) {
            if (emp.getEid() == 107) {
                System.out.println("Eid: " + emp.getEid() + ", Gross Salary: " + emp.calculateGrossSalary());
                break; // Assuming there's only one employee with Eid 107
            }
        }

        // c) Count the total number of employees whose salary more than 20000/-
        int count = 0;
        for (Employee emp : employees) {
            if (emp.basicSalary > 20000) {
                count++;
            }
        }
        System.out.println("\nTotal number of employees with salary more than 20000/-: " + count);
    }
}



