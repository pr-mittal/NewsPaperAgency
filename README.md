# NewsPaperAgency
Java Project for News Paper Agency , Records Handling

Features :

- Organized sql and java based application for day to day record handling
- Table view of data and automatic bill calculation and upload and download of  images
- Send sms to unpaid customers 
- Import/ Export data from excel sheet

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

Eclipse , SceneBuilder (gluon) , xampp

Libraries used :

poi (convert database to excel) , sql 
