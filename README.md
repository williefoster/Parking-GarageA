# Parking-GarageA
The real project
import java.util.*;
import java.text.DecimalFormat;

public class Employee {

DecimalFormat f = new DecimalFormat("#,###.00");
private String lastName, firstName;
private String jobTitle, id;
private String license;
private List<String> licensePlates = new ArrayList<>();
private double salary, hourlyWage, hours;

public Employee(String lName, String fName, String job, String identification) {

lastName = lName;
firstName = fName;
jobTitle = job;
id = identification;
}

public String getEmployeeInfo() {

return "Name: " + lastName + ", " + firstName + "\nOccupation: " + jobTitle;
}

public void setLicense(String lPlate) {

license = lPlate;
licensePlates.add(license);
}

public String getLicense(){

return license;
}

public String[] getLicencePlates() {

String[] temp;
temp = new String[licensePlates.size()];
licensePlates.toArray(temp);
return temp;
}

public void printPlates() {

System.out.println("License Plates: " + licensePlates);
}

public void getPaymentType() {

if (jobTitle.equalsIgnoreCase("Valet")) {
	hourlyWage = 15.00;
        System.out.println("Hourly Rate: " + f.format(hourlyWage));
} else if (jobTitle.equalsIgnoreCase("Store Associate")) {
            hourlyWage = 12.50;
            System.out.println("Hourly Rate: " + f.format(hourlyWage));
} else if (jobTitle.equalsIgnoreCase("Booth Sitter")) {
            hourlyWage = 18.00;
            System.out.println("Hourly Rate: " + f.format(hourlyWage));
} else if (jobTitle.equalsIgnoreCase("Store Manager")) {
            salary = 42000;
            System.out.println("Salary: " + f.format(salary));
} else if (jobTitle.equalsIgnoreCase("Garage Manager")) {
            salary = 72000;
            System.out.println("Salaray: " + f.format(salary));
} else {
         System.out.println("The job description you are looking for is no longer available here at Chip&Dales Garage. Sorry for the inconvenience.");
                            
 }
}

public void setHours(double h) {

hours = h;
}

public double getHours() {

return hours;
}

public void printPayCheck() {

if (jobTitle.equalsIgnoreCase("Valet")){
	System.out.println("PayCheck: " + f.format(hourlyWage * hours));
} else if (jobTitle.equalsIgnoreCase("Store Associate")){
	System.out.println("PayCheck: " + f.format(hourlyWage * hours));
} else if (jobTitle.equalsIgnoreCase("Booth Sitter")) {
	System.out.println("PayCheck: " + f.format(hourlyWage * hours));
} else if (jobTitle.equalsIgnoreCase("Store Manager")) {
	System.out.println("PayCheck: " + f.format(salary / 26));
} else if (jobTitle.equalsIgnoreCase("Garage Manager")) {
	System.out.println("Salaray: " + f.format(salary / 26));
} else {
	System.out.println("No paycheck to be calculated");
}

}

public String getLastName(){

return lastName;
}

public String getFirstName(){

return firstName;
}

public String getOccupation(){

return jobTitle;
}

public String getID(){

return id;
}



public static void main(String[] args) {

Employee a = new Employee("kuchki","Rukia","Store Manager","ijcuhw90");
a.setLicense("rmx-102");
a.setLicense("pol-647");
a.setLicense("demo-101");

System.out.println(a.getEmployeeInfo());
a.printPlates();
a.getPaymentType();
a.printPayCheck();

}

}

public class Security {

// id scanner for payment
// leaving gate accessed by certain employees 
// after payment fulfilled gate should open then after 30 seconds gate should close

private Employee empOnDuty;
private String gate;
private boolean isOpen;


public Security(String gateLocation, boolean state){

gate = gateLocation;
isOpen = state;
}

public boolean setState(boolean state){

return isOpen = state;
}

// ternary operator, result = testCondition ? value1 : value2
public String state() {

return isOpen ? "open" : "closed"; 
}

// set employee on duty
public void setEmpOnDuty(Employee duty){

empOnDuty = duty;
}

// get employe on duty
public String getEmpOnDuty() {

return empOnDuty.getEmployeeInfo();
}

public static void main(String[] args){

Security main = new Security("Main Gate", false);
Employee e = new Employee("hanks","Tom","booth sitter");
Customer c1 = new Customer("wolf","lone","loneWolf@gmail.com","rxm786");
main.setEmpOnDuty(e);
System.out.println(main.getEmpOnDuty());
//main.setEmpOnDuty(c1);

}


}

// Customer class in which a customers attributes are recorded for the database

import java.util.*;

public class Customer {

private String lastName, firstName;
private String emailAddress;
private String licensePlate;
private List<String> licensePlates = new ArrayList<>();
private List<String> raffleTickets = new ArrayList<>();

public Customer(String lastN, String firstN, String email, String license) {

lastName = lastN;
firstName = firstN;
emailAddress = email;
licensePlate = license;
licensePlates.add(licensePlate);


}

public  boolean addLicense(String license) {
return licensePlates.add(license);
}

public  boolean removeLicense(String license) {
if (!licensePlates.contains(license)) {
	return false;
} else {
	return licensePlates.remove(license);
}

}

public String getName() {
return lastName + ", " + firstName;
}

public String getFirstName() {

return firstName;
}

public String getLastName() {

return lastName;
}

public String getEmail() {
return emailAddress;
}

public String getLicense() {
return licensePlate;
}

public List<String> printPlates() {

return licensePlates;
}


public String getCustomer() {

return "Last Name: " + lastName + " First Name: " + firstName +
		    "\nEmail Address: " + emailAddress +
	            "\nPlates on File: " + licensePlates.toString();
}

public static void main(String[] args) {
Customer c1 = new Customer("wolf", "lone", "loneWolf@gmail.com", "rxm10937pol");
System.out.println(c1.getName());
System.out.println(c1.getEmail());
System.out.println(c1.getLicense());

c1.addLicense("deck-9op0");
c1.addLicense("call-98yu");
c1.addLicense("mash-45p9");
c1.addLicense("palr-32yt");

System.out.println(c1.getCustomer());
System.out.println(c1.printPlates());
}

}


