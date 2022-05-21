# Pharmacy Management System!

It is a project which helps a pharmacy to manage its data like employee data, sellers data, debtors data, inventory etc.It also allows user to print bill.


# Working

It is built on Netbeans in Java swing language. First comes login or signup page. After successful login or signup, the user is shown Medicine page. Here, list of medicine is shown alongwith its information like quantity. price, name, formula etc. The user can select the medicine a customer needs and add it to the cart. After successful buying, quantity of medicine bought willbe subtracted from data. There is a sidebar from where user can go to different pages like agents, selling, customers, Debtors.
Next comes the agents page. It contain information of all the agents from whom user buys information from. It will show amout of medicine bought, its quantity, price etc.
Next is Customers page which shows information of customers like name, number, quantity etc.
The debtors page show information of people who have yet to pay money for the medicine bought.

## Installation

To run this project a number of libraries are required which needs to be installed on netbeans which are as follows.

 - rs2xml.jar
 - jcalendar-1.4.jar
 - derby
etc.

## Database
We can use sql for database and netbeans also provides its own database which can be used for this project.
Following are the imports.

 - import java.sql.Connection;
 - import java.sql.DriverManager;
 - import java.sql.PreparedStatement;
 - import java.sql.SQLException;
 - import java.sql.Statement;
 - import java.sql.ResultSet;
 - import javax.swing.JOptionPane;
 - import javax.swing.table.DefaultTableModel;
 - import net.proteanit.sql.DbUtils;
To make a connection with database we can use the following code.

```
Connection Con = null;
Statement St = null,St1=null;
ResultSet Rs = null,Rs1=null;
@SuppressWarnings("unchecked")
public void SelectMed()
{
    try
    {
     Con = DriverManager.getConnection("jdbc:derby://localhost:1527/project","ali","1234");
     St1=Con.createStatement();
     Rs1=St1.executeQuery("Select * from ali.AGENTTBL");
     AgentTable.setModel(DbUtils.resultSetToTableModel(Rs1));
    }
    catch(SQLException e)
    {
     e.printStackTrace();   
    }
}
```
