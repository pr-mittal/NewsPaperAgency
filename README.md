

# NewsPaperAgency

Java Project for News Paper Agency , Records Handling

Features :

- Organized sql and java based application for day to day record handling
- Table view of data and automatic bill calculation and upload and download of  images
- Send sms to unpaid customers 
- Import/ Export data from excel sheet

Interface :

1. DashBoard

   ![image](https://user-images.githubusercontent.com/56964828/127981297-4271d26a-b2d1-4af3-a652-0e13691398af.png)

   - Open other windows

2. Customer

   ![image](https://user-images.githubusercontent.com/56964828/127981146-115f0703-cc84-42b1-9bbf-fe35052ba7bd.png)

   - Add a new customer 
   - search for unique mobile number in database and fetch database if it exists
   - The info about paper,select area is derived based on available hawker
   - usual SQL queries like  store(insert) ,update ,delete

3. Hawker Display

   ![image](https://user-images.githubusercontent.com/56964828/127981162-9ea8de66-c683-48ea-a2fc-faf28a415727.png)

   - Display data of all hawkers in form of table
   - Open respective image by clicking on link 

4. Hawker Control

   ![image](https://user-images.githubusercontent.com/56964828/127981176-2c9bc099-d3f9-4b6d-993b-6cd7085ae4a0.png)

   - Add a new hawker(data automatically fetched if same hawker name exists)
   - write data and upload image to images/ library 
   - simple SQL queried like new(insert) , update , remove (delete)

5. Costumer Display
6. ![image](https://user-images.githubusercontent.com/56964828/127981185-ef5c219a-8d3a-42e7-98ba-6dc9b18bbc79.png)
   - fetch or sort(based on paper name) customer data and display in form of table
   - export data to excel sheet and  import data from excel sheet to table

6. Paper Master

   ![image](https://user-images.githubusercontent.com/56964828/127981255-20f743a7-334b-476c-b84c-3f3c6c150350.png)

   - Insert  paper and or update its values
   - SQL queried new(insert),clear(delete),update,remove(delete)

7. Bill History

   ![image](https://user-images.githubusercontent.com/56964828/127981266-6a22511c-d886-49bf-abc8-bfc6c6ab3471.png)

   - Bill history of customers fetched via mobile numbers (primary key) and sorted paid or unpaid 

9. Bill Generator

   ![image](https://user-images.githubusercontent.com/56964828/127981279-179c424a-5e4b-4b8b-95a7-332c3f44d606.png)

   - Generate bill of customer by subtracting current date from date when last bill was calculated
   - And displaying the total amount to be paid
   - Generate All : to generate bill for all customers
   - Sending sms for respective bill amount  

10. Bill Collector

    ![image](https://user-images.githubusercontent.com/56964828/127981284-17a35f95-6698-4d4c-8adb-b797c843fb90.png)

    - fetch all bills based on the mobile number and select them as paid 

Installation :

1. Ensure you java jre + jdk is installed in pc. Also add C:/Program Files/Java/jdk_x/bin is added to path.
2. Install Eclipse and open this repo as a  project . 
3. To install javafx open help>eclipse marketplace>search(javafx) or [link](https://o7planning.org/10619/install-efxclipse-for-eclipse)
4. Or add extenal jars of javafx(Download from gluon) and poi to your project (Properties>Java Build Path>Libraries)
5. error : javafx-runtime-components-are-missing-and-are-required-to-run-this-application [link](https://stackoverflow.com/questions/52144931/how-to-add-javafx-runtime-to-eclipse-in-java-11)
6. Add library poi in referenced libraries. Project>Properties>Libraries>Add Exter Jars. Select all jar files from "lib\poi-4.1.2" and "lib\poi-4.1.2\lib"
7. Add library sql-connector in referenced libraries.  Project>Properties>Libraries>Add Exter Jars. Select all jar files from "lib\mysql-connector-java-8.0.26"

Database (or import from sql/newsagency.sql) :

1. Create a database name "newsagency"

2. Table: **papers**

   | **paper**           | **price  ** |
   | ------------------- | ----------- |
   | varchar-primary key | float       |

   Java : paperMaster/paperMasterController.java

3. Table : **hawkers**

   | name  | mobile | address | areas | aadharpic | salary | doj  |
   | ----- | ------ | ------- | ----- | --------- | ------ | ---- |
   | pk-vc | vc     | vc      | vc    | vc        | int    | date |

   Java : hawkerControl/HawkerControlController.java 

4. **Table : customers**

   | **name** | **mobile** | address | papers | hawker | curdate |
   | -------- | ---------- | ------- | ------ | ------ | ------- |
   | vc       | vc         | vc      | vc     | vc     | date    |

   Java : customer/CustomerController.java

5. **Table:- billing**

   | billid                | cust_mobile | noofdays | date_of_billing | amount | status        |
   | --------------------- | ----------- | -------- | --------------- | ------ | ------------- |
   | int-pk-auto increment | vc          | int      | date            | float  | int-default:0 |

   Java : billGenerator/BillGeneratorController.java

   

Software used :

Java 11,Eclipse 2020-6 (JavaFx installed), SceneBuilder (gluon) 11.0.2 , xampp 

Libraries used :

poi (convert database to excel) , sql , openjavafx_sdk

