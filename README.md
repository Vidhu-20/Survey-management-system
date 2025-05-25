# Survey Management System

## Project Description
The **Survey Management System** is a Java-based application that allows users to participate in a short survey while administrators can manage and review the collected responses. The system is designed to store user input securely in an **Oracle database** using **JDBC**.

### Roles & Functionality:
- **User Role** – Participants can answer survey questions about commonly used platforms such as social media, e-commerce sites, and search engines. Their responses are stored in the database.
- **Admin Role** – Administrators can log in, retrieve survey responses, and analyze user preferences.

### Technologies Used:
- **Java**
- **JDBC**
- **Oracle Database**
- **PreparedStatement** for secure data insertion
- **ResultSet** for fetching stored records

## Setup Instructions
1. **Install Oracle Database** and create the required table:
   ```sql
   CREATE TABLE Tabledata (
       Name VARCHAR2(25),
       Email VARCHAR2(25),
       Answer_1 VARCHAR2(25),
       Answer_2 VARCHAR2(40),
       Answer_3 VARCHAR2(40)
   );
   ```
2. **Clone the Repository**
```sh
git clone https://github.com/YOUR_USERNAME/Survey-Management-System.git
cd Survey-Management-System
```
3. **Configure Database Connection**
Modify the connection string in Sample.java:
```sql
String url = "jdbc:oracle:thin:@Localhost:****:xe";
String username = "!!!!!";
String password = "********";
```
4. **Compile and Run the Program**
```sh
javac Sample.java
java Sample
```



