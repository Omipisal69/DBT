package DemoDateBase;
import java.sql.*;
import java.util.Scanner;

public class Ass1 {
	public static void main(String[] args) {
		Connection con=null;
		Statement smt=null;
		PreparedStatement psmt=null;
		try
		{
			Class.forName("oracle.jdbc.driver.OracleDriver");
			String url="jdbc:oracle:thin:@localhost:1521:XE";
			con=DriverManager.getConnection(url,"system","system");
			
		
		
				
		int ch=0;
		do
		{
			System.out.println("1. Insert Record"
					+ "         2. Display All Records"
					+ "         3. Update name"
					+ "         4. Delete"
					+ "         0. Exit"
					+ "      Enter your Choice ");
			Scanner sc=new Scanner(System.in);
			ch=sc.nextInt();
			switch(ch)
			{
			case 1:int rno;String name;double avg;
			System.out.println(" Enter Rno Name And Avg ");
			rno=sc.nextInt();
			name=sc.next();
			
			psmt=con.prepareStatement("insert into student values (?,?)");
			psmt.setInt(1, rno);
			psmt.setString(2, name);
			int no=psmt.executeUpdate();
			System.out.println(no +" REcords Inserted ");
			break;
			case 2:
				
			}
		}while(ch!=0);
			
		}	
		catch(ClassNotFoundException | SQLException e)
		{
			System.out.println(e);
		}
			
		
	}

}
