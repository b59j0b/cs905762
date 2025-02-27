java cAssignment 4: Microsoft Access 
The goal of this assignment is to take your Entity Relationship Diagram (ERD) from Assignment 3 and turn it into a Microsoft Access Database for your business and create a database form. application for managing your employees. Please carefully read and complete all the parts and steps listed in this document and then submit the required files to OWL. It is important that you closely follow all of the specifications and requirements given in this document and ensure that your database fulfills them correctly.
You MUST use Microsoft Access for this assignment. If you are using an Apple (macOS) computer you will need to find a way to run Access such as using MyVLab or using a GenLab computer on campus. Before using MyVLab you must have a good understanding of how to transfer files between your computer and the remote computer and backup your database frequently.  
Warning for MyVLab Users 
If you are using MyVLab for this assignment, you MUST save to the H: drive while working on your assignment. The H: drive represents the remote storage on the virtual lab computer. The Z: drive represents your own local computers storage. Saving directly to the Z: drive WILL corrupt your Access database if your internet connection drops. Only copy files to the Z: drive when backing up or submitting your work.
Here is the correct process for saving on MyVLab: 1.   While working on your Access database save to the H: drive.2.   When you want to backup or submit your work first make sure you save your work and then close Access.3.   Using the file explorer tool on MyVLab COPY (do not move) your Access file from the H: drive to a location on your local computer on the Z: drive.4.   Submit your file to OWL using your local computer (MyVLab cannot access a web browser).
Part 1: Correct Your ERD from Assignment 3 
Before we begin translating your ERD into a database, we need to ensure that it is correct. On the next page is the solution to Assignment 3. Use this solution to correct your ERD from assignment 3.
While correcting your ERD, please keep the following notes in mind:·   The ERD shown below is just one example of a correct solution. There are multiple different but correct solutions. For example, you may use different names for the attributes and entities so long as the capitalization scheme is correct. You will also have added a few of your own attributes specific to your business.·   The attribute names do not have to match what is shown in the below ERD exactly. For example, “First”, “EmployeeFirstName”, “NameFirst”, etc. would all be acceptable for the “FirstName” attribute in the EMPLOYEE entity.·   You were required to add additional attributes to your ERD that make sense for your business. The ERD below does not include these, but you should, and these should become part of your database in Part 2. ·   Make sure all your foreign keys and relationship attributes are present and in the correct tables.·   All entity names should be in ALL UPPERCASE, all relationship entity names in all lowercase, and all attribute names in UpperCamelCase (first letter for each word capitalized).
Note that the following attributes are unique: TicketID (in RMA), SIN (in EMPLOYEE), and all primary keys.
Also note that the “involves” relationship between PRODUCT and TICKET is one-to-many (1:N). We accepted solutions for Assignment 3 that had this relationship as many-to-many (N:M) as correct, but for assignment 4, please make sure this relationship is one-to-many (this will be important for Part 4).
The “” and “” attributes are placeholders for the extra attributes you added in assignment 3. Replace these with your attributes and their correct bullet point.
Attribute Names 
While attribute names like “Name” or “Date” are fine in your ERD, Microsoft Access does not allow field names that conflict with its list of reserved words. These are words that Access uses for other functions and can not be used as field names in a table. Take a look at the list here and change any attribute names in your ERD that conflict. For example, “Name” in the PRODUCT and DEPARTMENT entities would need to be changed to “ProductName”, “DepartmentName”, or something similar.
Also remove any spaces in your attribute and entity names. For example, if you had an attribute named “Last Name” change it to “LastName” with the space removed. This will make things easier when we start getting into queries in later weeks.
Submit Updated ERD 
Once you have made the changes to your ERD, save them in a file named:
youraccountname_ERD_updated.dia 
You will be required to submit this file with your assignment. If you find any errors in your ERD while working on Part 2 and 3 or make any changes to the structure of your database while working on these parts, you are required to also make the changes to your ERD. The ERD must match the database you submit.
Part 2: Create a Microsoft Access database 
Using Microsoft Access, create a new database named:
youraccountname_yourbusinessname_A4.accdb 
where youraccountname is your UWO username and yourbusinessname is the name of your business from the past assignments.
You are to create a Microsoft Access database based on your ERD from Part 1. There should be exactly one table in your database for every entity shown in your ERD. In addition to the requirements stated in your ERD, your database must also meet the specifications for each table (listed on the following pages). Note that these specifications do not list all fields that need to be in your table, in some cases you may be required to add and correctly set the properties for foreign keys or for fields that are specific to your ERD design (e.g. for the new entity you created in Part 1). It is expected that you set up these fields correctly such that your relationships and database function as expected.
a)   For the “EMPLOYEE” table use the following specifications:1) Username – set as primary key, maximum 25 characters, no default value. 2) First Name - maximum 25 characters, no default value.3) Last Name - maximum 50 characters, no default value.4) Address – maximum 100 characters, no default value. 5) SIN -  stored as a number, must be formatted as xxx-xxx-xxx where each x is a number (use an input mask). User must input all 9 numbers. You must ensure that no two employees can have the same SIN. This field should have no default value.6) Phone Number – maximum 11 characters, must be formatted as (yyy) xxx-xxxx where each y is an optional number, and each x is a required number (use an input mask). Phone Number is optional and should not have a default value. If the phone number is not provided it should be stored as a null value and not a zero-length string.7) Active – stored as a Yes/No value based on if this is a current employee (i.e. not retired, etc.). The default value should be Yes.b)   For the “PRODUCT” table use the following specifications:
1)    Unique Product ID that acts as the primary key and has a value that is automatically created when a new item is entered. You must format this value such that it starts with your business’s initials and then a number. For example, if your company is named Forest City Ducks, the initials would be “FCD” and your Product IDs should look something like:
FCD1
FCD2
FCD13
FCD134
where the “FCD” are the initials, and the numbers are any unique numbers generated by the database automatically when the product record is created (they do not have to match what is shown above or be in order).
Note that Product ID will also be used as a foreign key in other tables. When it is used as a foreign key it must be of type Long Integer and the values will only be entered as numbers, for example:
the foreign key is 1 where the Product ID is FCD1 
the foreign key is 2 where the Employee ID is FCD2
the foreign key is 13 where the Employee ID is FCD13
the foreign key is 134 where the Employee ID is FCD134 
2) Title - maximum 150 characters
3) Description – stored as text that can be over 255 characters long. There is no
limit to the maximum size.4) Image URL – stored as a hyperlink. If there is no photo, this will be a null value (novalue will be provided). Should not allow zero length strings.
4) Sale Price – stored as currency with 2 decimal places. No default value. In the  
field description, make it clear what currency it is in (dollars, yen, pounds, etc.).
4) Manufacturing Cost – stored as currency with 2 decimal places. No default  
value. In the field description make it clear what currency it is in (dollars, yen, pounds, etc.).5) QuantityInStock – number with no decimal places shown. Default value of zero.6) Additional Fields – Your two additional attributes that you added in Assignment 3. The field properties are up to you but should be appropriate for the attribute and allow data to be input to your代 写Assignment 4: Microsoft AccessSQL
代做程序编程语言 database correctly.
c)   For the “INVOICE” table use the following specifications:
1) Unique Invoice ID that acts as a text based primary key that is NOT automatically created
when a new item is entered.
note: this ID must start with ANY alphabetic character followed by 3 digits:
the letter MUST be a capital letter
examples: K345 
F302 
X000
Y012
note: it will not necessarily be the same letter each time.
Format: LNNN – where N means a number and L means a capital letter
- use an input mask.
NOTE: - very important:
if the Invoice ID is used as a Foreign Key in another table:
- that key must be of type Text (String)
- the value entered will just be the letter and the number:
examples:    Foreign key will be K333 where the Order Number is K333 
L090 where the Order Number is L090
P300 where the Order Number is P300
note: make this a reasonable maximum length (for example, not 255).
5) Coupon Code: text value that is four or five characters in length. A coupon code can only
contain capital letters and numbers and must be exactly four or five
characters in total (you must enforce this with an input mask).
6) Total Price – a currency value with two decimal places. No default value. In the field
description make it clear what currency it is in (dollars, yen, pounds, etc.).
6) Payment Method – stores a text value of “Cash”, “Visa”, “MasterCard”, “PayPal”, “Debit”,  
or “Unpaid”. You do not have to restrict or enforce this field to only
having these values but you should set the character length and
other field properties appropriately.
7) Foreign Key – Properties must be set correctly to support the purchases relationship.  
Must be a data type that will work with the primary key of CUSTOMER.
Should not have a default value.d)   For the “CUSTOMER” table use the following specifications:1)   Must have a unique primary key. If you use a surrogate key such as Customer ID, it must be set up such that the value is automatically created when a new item is entered, and that the new value is guaranteed to be unique. If you use Email as a natural key, it must follow the specification below for the Email field.2) Email - maximum 255 characters. Unique. No default value.3) First Name - maximum 25 characters, no default value.4) Last Name - maximum 50 characters, no default value.5) Home Address - maximum 100 characters, no default value.6) Phone - maximum 11 characters, must be formatted as (yyy) xxx-xxxx where each y is an optional number and each x is a required number (use an input mask). Phone Number is optional and should not have a default value. If the phone number is not provided it should be stored as a null value and not a zero-length string.7) Birthday – date formatted as day-month-year. For example, April 5th, 2024 should be formatted as 05-04-2024. Note that day and month numbers less than 10 should have a leading zero. Hint: You may need to write a custom format pattern for this rather than using a built-in format. 8) Additional Fields – Your two additional attributes that you added in Assignment 3. The field properties are up to you but should be appropriate for the attribute and allow data to be input to your database correctly.e)   For the “TICKET” table use the following specifications:1)   Unique Ticket ID that acts as the primary key for the TICKET table. This ID should be an automatically generated (not input by the user) and stored as a whole number.2) Subject – A short string of text, not longer than 75 characters. Default value of “Unnamed  Ticket”.3) Description - stored as text that can be over 255 characters long. There is no limit to themaximum size and no default value.4) Status – A text value of “open”, “resolved”, “investigating”, “closed”, or “waiting on  customer”. You do not have to restrict or enforce this field to only having thesevalues but you should set the character length and other field properties appropriately.5) Severity – An integer value representing the severity of the issue described in the ticket.  Valid values range from 0 (low severity) to 9 (critical severity). You shouldensure only one digit can be input. The default value is 4.6) Date Created - date formatted as day-month-year (just like Birthday in the CUSTOMER table).
7) Foreign Keys – Properties must be set correctly to support the relationships with the TICKET table.f)   For the “RMA” table use the following specifications:1)   Unique RMA ID that acts as the primary key for the RMA table. This ID should be an automatically generated (not input by the user) whole number and does not require any special formatting.2) Approved – A true or false value. The default value should be false.3) Return Received - A true or false value. The default value should be false.4) Replacement Address - maximum 100 characters, no default value.5) Replacement Sent - A true or false value. The default value should be false.6) Foreign Key – Properties must be set correctly to support the requests relationship.  Must be a data type that will work with the primary key of TICKET.Should not have a default value.g)   For the “includes” table use the following specifications:1)   As this is a junction table (all so called an associative table) that represents the includes relationship, you do not need to set a primary key.2) Quantity – A positive whole number that represents the number of this product involved in the invoice. The default value should be 1.3) Foreign Keys – Properties must be set correctly to support the relationships with the  INVOICE and PRODUCT tables.h) All fields in all tables should have a field description provided that explains what the field is for. For foreign keys, the description should also clearly state that they are foreign keys. You may wish to review Assignment 3 again to see descriptions of what these attributes represent in the ERD.
Unless otherwise stated above, zero length should not be allowed for text-based fields. 
Formatting and input masks are only required if needed to fulfill one or more of the requirements stated above. 
ALSO:·   You MUST include any other fields required to create a working relational database (e.g. foreign keys).·   This database must have the same relationships, cardinality, nullability, uniqueness, participation, and entities as specified in the ERD from Part 1. Ensure you set your field properties to fulfill BOTH the specifications above as well as the requirements from the ERD in Part 1.· Hint: There are 7 entities in the ERD from Part 1, so there should be 7 tables in your database.Part 3: Relationships  Data You must build all the relationships described in your ERD. Use the Relationships Database Tool in Access to enforce the relationships as demonstrated in the Access tutorial videos. Make sure the cardinality shown in the Relationship Database Tool for each relationship is correct and consistent with the ERD from Part 1.Fill each table with example data. You should add at least four (4) records for each and every table (you are free to add more than four if you wish).This example data can be made up/fictional but must be related to your company from Assignment 1.Your name (first and last) must be the name of the first employee in your EMPLOYEE table. The username should be your Western username. Do not input a real SIN, address, or phone number (you can just make these up). There will be a mark penalty if your full name and username is not in the first record of the EMPLOYEE table.You are allowed to make up the names of the other EMPLOYEEs, CUSTOMERs, etc. The PRODUCTS should be created to appear valid and should make sense in the context of your other data and your business. But do not spend too much time thinking up data.You are also not required to provide real URLs for your products photo (can be made up).Hint 1: In some cases, it can be easier to input the data before setting up your relationships. However, you must ensure that the values given for foreign keys match up correctly with the corresponding primary key values or you may get an error when enforcing referential integrity.Hint 2: If you get the error “The database engine could not lock the table..." when trying to enforce referential integrity, you need to close your other table tabs/windows before using the Relationships Database Tool.Hint 3: If you get the error "...can't create this relationship and enforce referential integrity." make sure that the data you have input in your databases make sense in terms of foreign key values. A value given for a foreign key must match the value of a primary key in the related table.Hint 4: Ensure that you check that the relationships shown in the Relationship Database Tool make sense and match your ERD. If a One-to-One relationship is showing up as Many-to-One, you may have set the field properties incorrectly for the foreign key.


         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
