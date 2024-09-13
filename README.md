# Survey-management-system
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.ResultSet;
import java.sql.Statement;
import java.util.Scanner;

public class Sample
{
public static void main(String[] args)
    {
	Scanner sc=new Scanner(System.in);
	try
	{
	Class.forName("oracle.jdbc.OracleDriver");
	Connection con;
	String url="jdbc:oracle:thin:@Localhost:****:xe";
	String username="!!!!!";
	String password="********";
	con=DriverManager.getConnection(url,username,password);
	if(con!=null)
	{
	System.out.println("JDBC Connection Established");
	}
	else
	{
	System.out.println("JDBC Connection Not Established");
	}
	System.out.println("Enter the type");
	System.out.println("1:User\t2:Admin");
	int ch=sc.nextInt();
	if(ch==1);
	{
	Statement stmt=con.createStatement();
	//stmt.executeUpdate("create table Tabledata(Name varchar2(25),Email varchar2(25),Answer_1 varchar2(25),Answer_2 varchar2(40),Answer_3 varchar2(40))");
	System.out.println("\t****WELCOME TO THE SURVEY****");
	System.out.println("\nLets start the surver\n");
	System.out.println("Type the answers");
	PreparedStatement ps;
	for(int i=0;i<1;i++)
	{
	ps=con.prepareStatement("insert into Tabledata values(?,?,?,?,?)");
	System.out.println("Enter the name:");
	String name=sc.next();
	ps.setString(1,name);
	System.out.println("Enter the Email:");
	String Email=sc.next();
	ps.setString(2,Email);
	System.out.println("\n *Welcome to Short Survey*");
	System.out.println("\nQuestion 1");
	System.out.println("\nWhat is the most used Socialmedia by you?");
	System.out.println("1>Instagram");
	System.out.println("2>Facebook");
	System.out.println("3>Twitter");
	System.out.println("4>Whatsapp");
	System.out.println("\nEnter the Answer:");
	String Answer1=sc.next();
	ps.setString(3, Answer1);
	System.out.println("\nQuestion 2");
	System.out.println("\nWhat is the most used E-Commerce site by you?");
	System.out.println("1>Amazon");
	System.out.println("2>Flipcart");
	System.out.println("3>Snapdeal");
	System.out.println("4>Meesho");
	System.out.println("\nEnter the Answer:");
	String Answer2=sc.next();
	ps.setString(4, Answer2);
	System.out.println("\nQuestion 3");
	System.out.println("\nWhat is the most used SearchEngine by you?");
	System.out.println("1>Google");
	System.out.println("2>Microsoft Edge");
	System.out.println("3>FireFox");
	System.out.println("4>Yahoo");
	System.out.println("\nEnter the Answer");
	String Answer3=sc.next();
	ps.setString(5, Answer3);
	System.out.println("\n\t*-* THANKYOU FOR YOUR SURVEY *-*\n");
	ps.executeUpdate();
	}
	}
	if(ch==2)
	{
		System.out.println("Welcome ADMIN");
		System.out.println("Enter the username");
		String user_name=sc.next();
		System.out.println("Enter the password");
		String pswd=sc.next();
	con=DriverManager.getConnection(url,username,password);
	Statement stmt=con.createStatement();
	ResultSet rs;
	rs=stmt.executeQuery("select * from Tabledata");
	while(rs.next())
	{
	System.out.println(rs.getString(1));
	System.out.println(rs.getString(2));
	System.out.println(rs.getString(3));
	System.out.println(rs.getString(4));
	System.out.println(rs.getString(5));
	}
	}
	}
	catch (Exception e)
	{
	System.out.println("Exception");
	}
	}

}
