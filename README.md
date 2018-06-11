# Descartes_Institus_IPayable
Academic exercise with Java, concepts of aggregation, inheritance and polymorphism

//++++++++++++++++++++++++++++++++++++++++bus
//++++++++++++++++++++++++++++++++++++++++Class Member (abstract)
package bus;

public abstract class Member implements IPayable
{
	private int id;
	private String fn;
	private String ln;
	private String ssn;
	private Date reg_hireDate;
	private Date birthDate;
	private Address memberAddress;
	private EnumMemberType type;
	private EnumStatusType status;
	
	public int getId()
	{
		return this.id;
	}
	public void setId(int id)
	{
		this.id = id;
	}
	public String getFn() {
		return fn;
	}
	public void setFn(String fn) {
		this.fn = fn;
	}
	public String getLn() {
		return ln;
	}
	public void setLn(String ln) {
		this.ln = ln;
	}
	public String getSsn() {
		return ssn;
	}
	public void setSsn(String ssn) {
		this.ssn = ssn;
	}
	public Date getReg_HireDate()
	{
		return this.reg_hireDate;
	}
	public void setReg_HireDate (Date regDate)
	{
		this.reg_hireDate = regDate;
	}
	public Date getBirthDate()
	{
		return this.birthDate;
	}
	public void setBirthDate (Date birthDate)
	{
		this.birthDate = birthDate;
	}
	public Address getMemberAddress()
	{
		return this.memberAddress;
	}
	public void setMemberAddress( Address memberAddress)
	{
		this.memberAddress = memberAddress;
	}
	public EnumMemberType getType() 
	{
		return type;
	}
	public void setType(EnumMemberType type) 
	{
		this.type = type;
	}
	public EnumStatusType getStatus() {
		return status;
	}
	public void setStatus(EnumStatusType status) {
		this.status = status;
	}
	
	public Member()
	{
		this.id = 0000;
		this.fn = "unknown";
		this.ln = "unknown";
		this.ssn = "unknown";
		this.reg_hireDate = new Date();
		this.birthDate = new Date();
		this.memberAddress = new Address();
		this.type = EnumMemberType.unknown;
		this.status = EnumStatusType.unknown;
		
	}
	public Member (int id, String fn, String ln, String ssn)
	{
		this.id = id;
		this.fn = fn;
		this.ln = ln;
		this.ssn = ssn;
	}
	public Member (int id, String fn, String ln, String ssn,  Date reg_hireDate, Date birthDate, Address memberAddress)
	{
		this.id = id;
		this.fn = fn;
		this.ln = ln;
		this.ssn = ssn;
		this.reg_hireDate = reg_hireDate;
		this.birthDate = birthDate;
		this.memberAddress = memberAddress;
	}
	public Member (int id, String fn, String ln, String ssn,  Date reg_hireDate, Date birthDate, Address memberAddress, EnumMemberType type)
	{
		this.id = id;
		this.fn = fn;
		this.ln = ln;
		this.ssn = ssn;
		this.reg_hireDate = reg_hireDate;
		this.birthDate = birthDate;
		this.memberAddress = memberAddress;
		this.type = type;
	}
	public Member (int id, String fn, String ln, String ssn,  Date reg_hireDate, Date birthDate, Address memberAddress, EnumMemberType type, EnumStatusType status)
	{
		this.id = id;
		this.fn = fn;
		this.ln = ln;
		this.ssn = ssn;
		this.reg_hireDate = reg_hireDate;
		this.birthDate = birthDate;
		this.memberAddress = memberAddress;
		this.type = type;
		this.status = status;
	}
	
	public String toString()
	{
		return 	this.id + " - " +
				this.fn + " - " +
				this.ln + " - " +
				this.ssn + " - " +
				this.reg_hireDate + " - " +
				this.birthDate + " - " +
				this.memberAddress + " - " +
				this.type + " - " +
				this.status;
	}
	
}

//++++++++++++++++++++++++++++++++++++++++Class Student is a Member
public class Student extends Member 
{
	private double firstFees;

	public double getFirstFees() {
		return firstFees;
	}

	public void setFirstFees(double firstFees) {
		this.firstFees = firstFees;
	}
	
	public Student()
	{
		super();
		this.firstFees = 0.00;
	}
	public Student (int id, String fn, String ln, String ssn, double firstFees)
	{
		super(id, fn, ln, ssn);
		this.firstFees = firstFees;
	}
	public Student (int id, String fn, String ln, String ssn, Date reg_hireDate, Date birthDate, Address memberAddress, double firstFees)
	{
		super(id, fn, ln, ssn, reg_hireDate, birthDate, memberAddress);
		this.firstFees = firstFees;
	}
	public Student (int id, String fn, String ln, String ssn, Date reg_hireDate, Date birthDate, Address memberAddress, double firstFees, EnumMemberType type)
	{
		super(id, fn, ln, ssn, reg_hireDate, birthDate, memberAddress, type);
		this.firstFees = firstFees;
	}
	
	public String toString()
	{
		return super.toString() + " - " + this.firstFees + " - " + "Payment: " + calculPayment() + "\n" ;
	}
	public double calculPayment() 
	{
		return this.firstFees;
	}
	
}
//++++++++++++++++++++++++++++++++++++++++Class Teacher is a Member
public class Teacher extends Member
{
	private double hoursPerWeek;
	private double hourlyRate;
	
	
	public double getHoursPerWeek() {
		return hoursPerWeek;
	}
	public void setHoursPerWeek(double hoursPerWeek) {
		this.hoursPerWeek = hoursPerWeek;
	}
	public double getHourlyRate() {
		return hourlyRate;
	}
	public void setHourlyRate(double hourlyRate) {
		this.hourlyRate = hourlyRate;
	}
	public Teacher()
	{
		super();
		this.hoursPerWeek = 0.00;
		this.hourlyRate = 0.00;
	}
	public Teacher (int id, String fn, String ln, String ssn, double hoursPerWeek, double hourlyRate)
	{
		super(id, fn, ln, ssn);
		this.hoursPerWeek = hoursPerWeek;
		this.hourlyRate = hourlyRate;
	}
	public Teacher (int id, String fn, String ln, String ssn, Date reg_hireDate, Date birthDate, Address memberAddress, double hoursPerWeek, double hourlyRate)
	{
		super(id, fn, ln, ssn, reg_hireDate, birthDate, memberAddress);
		this.hoursPerWeek = hoursPerWeek;
		this.hourlyRate = hourlyRate;
	}
	public Teacher (int id, String fn, String ln, String ssn, Date reg_hireDate, Date birthDate, Address memberAddress, double hoursPerWeek, double hourlyRate, EnumMemberType type)
	{
		super(id, fn, ln, ssn, reg_hireDate, birthDate, memberAddress, type);
		this.hoursPerWeek = hoursPerWeek;
		this.hourlyRate = hourlyRate;
	}
	
	public String toString()
	{
		return super.toString() + " - " + this.hoursPerWeek + " - " + this.hourlyRate + " - " +  "Weekly Payment: " + calculPayment() + "\n";
	}
	public double calculPayment()
	{
		return this.hoursPerWeek * this.hourlyRate;
	}

}
//Class Address
//Member has an Address
public class Address 
{
	private int strNum;
	private String strName;
	private int aptNum;
	private String city;
	private String province;
	private String zipCode;
	private String country;
	
	
	public int getStrNum()
	{
		return this.strNum;
	}
	public void setStrNum(int strNum)
	{
		this.strNum = strNum;
	}
	public String getStrName()
	{
		return this.strName;
	}
	public void setStrName(String strName)
	{
		this.strName = strName;
	}
	public int getAptNum()
	{
		return this.aptNum;
	}
	public void setAptNum(int aptNum)
	{
		this.aptNum = aptNum;
	}
	public String getCity()
	{
		return this.city;
	}
	public void setCity(String city)
	{
		this.city = city;
	}
	public String getProvince()
	{
		return this.province;
	}
	public void setProvince(String province)
	{
		this.province = province;
	}
	public String getZipCode()
	{
		return this.zipCode;
	}
	public void setZipCode(String zipCode)
	{
		this.zipCode = zipCode;
	}
	public String getCountry()
	{
		return this.country;
	}
	public void setCountry(String country)
	{
		this.country = country;
	}
	
	public Address()
	{
		this.strNum = 0000;
		this.strName = "unknown";
		this.aptNum = 0000;
		this.city = "unknown";
		this.province = "unknown";
		this.zipCode = "unknown";
		this.country = "unknown";
		
	}
	
	public Address (int strNum, String strName, int aptNum, String city, String province, String zipCode, String country)
	{
		this.strNum = strNum;
		this.strName = strName;
		this.aptNum = aptNum;
		this.city = city;
		this.province = province;
		this.zipCode = zipCode;
		this.country = country;
	}
	
	public String toString()
	{
		return 	this.strNum + " " + 
				this.strName + " " + 
				this.aptNum + " " + 
				this.city + " " + 
				this.province + " " + 
				this.zipCode + " " + 
				this.country;
	}
}
//Class Date
//Member has a Date
public class Date 
{
	private int day;
	private int month;
	private int year;
	
	public Date()
	{
		this.day = 00;
		this.month = 00;
		this.year = 0000;
	}
	public Date(int day, int month, int year)
	{
		this.day = day;
		this.month = month;
		this.year = year;
	}
	public int getDay()
	{
		return this.day;
	}
	public void setDay (int day)
	{
		this.day = day;
	}
	public int getMonth()
	{
		return this.month;
	}
	public void setMonth (int month)
	{
		this.month = month;
	}
	public int getYear()
	{
		return this.year;
	}
	public void setYear (int year)
	{
		this.year = year;
	}
	
	public String toString()
	{
		return 	this.day + " / " +
				this.month + " / " +
				this.year;
	}
}
//+++++++++++++++++++++++++++++++Enum type 1
public enum EnumMemberType {
	
	unknown, teacher, student

}
//+++++++++++++++++++++++++++++++Enum type 2
public enum EnumStatusType 
{
	unknown, part_time, full_time  
}

//+++++++++++++++++++++++++++++++Interface IPayable
public interface IPayable 
{
	double calculPayment();
	double BONUS_RATE = 0.02;
}

