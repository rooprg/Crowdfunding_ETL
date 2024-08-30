**CROWDFUNDING EXTRACT, TRANSFORM, AND LOAD [ETL]**


**(1) Project Overview and Purpose:**


The purpose of this exercise is to build an Extract/Transform/Load [ETL] pipeline using Python, Pandas, and either Python dictionary methods or regular expressions to extract and transform the data. 

Working with a partner, the data is transformed, four .csv files are created, whose data will be used to create an ERD and a table schema. Finally, the CSV file data will be uploaded into a Postgres database.


**(2) Dataset Description:**

One of the initial datasets used for this exercise is a MicroSoft Excel file titled "crowdfunding.xlsx". This Excel file contains information on Crowdfunding efforts (cf_id; contact_id; company_name; blurb; goal; pledged; outcome; backers_count; country; current; launched at; deadline; staff_pick; spotlight; and category & sub-category.


A second Excel file titled "contacts.xlsx" was also used. It contains information on people involved in the crowdfunding, specifically their contact_id; name; and email.


**(3) Data Cleaning and Preprocessing:**


The following steps were undertaken with the dataset to make the information more useable for an end user-


**(a) Create the Category and Subcategory DataFrames:**
     (i) Read the "crowdfunding.xlsx" data into a Pandas DataFrame


     (ii) Create the Category and Subcategory DataFrames
     
        (1) Extract and transform the crowdfunding.xlsx Excel data to create a category DataFrame that has the following columns-

        (2) A "category_id" column that has entries going sequentially from "cat1" to "catn", where n is the number of unique categories

        (3) A "category" column that contains only the category titles


     (iii) Export the category DataFrame as category.csv and save it to your GitHub repository.


     (iv) Extract and transform the crowdfunding.xlsx Excel data to create a subcategory DataFrame that has the following columns-

        (1) A "subcategory_id" column that has entries going sequentially from "subcat1" to "subcatn", where n is the number of unique subcategories

        (2) A "subcategory" column that contains only the subcategory titles

     
     (v) Export the subcategory DataFrame as subcategory.csv and save it to your GitHub repository


**(b) Create the Campaign DataFrame:**


     (i) Extract and transform the crowdfunding.xlsx Excel data to create a campaign DataFrame has the following columns-

        (1)The "cf_id" column

        (2) The "contact_id" column

        (3) The "company_name" column

        (4) The "blurb" column, renamed to "description"

        (5) The "goal" column, converted to the float data type

        (6) The "pledged" column, converted to the float data type

        (7) The "outcome" column

        (8) The "backers_count" column

        (9) The "country" column

        (10) The "currency" column

        (11) The "launched_at" column, renamed to "launch_date" and with the UTC times converted to the datetime format

        (12)The "deadline" column, renamed to "end_date" and with the UTC times converted to the datetime format

        (13) The "category_id" column, with unique identification numbers matching those in the "category_id" column of the category DataFrame

        (14) The "subcategory_id" column, with the unique identification numbers matching those in the "subcategory_id" column of the subcategory DataFrame


     (ii) Export the campaign DataFrame as "campaign.csv" and save it to your GitHub repository


**(c) Create the Contacts DataFrame:**


     (i) Use Python dictionary methods for extracting and transforming the data from the contacts.xlsx file-

        (1) Import the contacts.xlsx file into a DataFrame
     
        (2) Iterate through the DataFrame, converting each row to a dictionary

        (3) Iterate through each dictionary, doing the following:
     
           - Extract the dictionary values from the keys by using a Python list comprehension
        
           - Add the values for each row to a new list

           - Create a new DataFrame that contains the extracted data

           - Split each "name" column value into a first and last name, and place each in a new column

           - Clean and export the DataFrame as "contacts.csv" and save it to your GitHub repository


**(d) Create the Crowdfunding Database:**

     (i) Inspect the four CSV files, and then sketch an ERD of the tables

     (ii) Use the information from the ERD to create a table schema for each CSV file

     (iii) Save the database schema as a Postgres file named crowdfunding_db_schema.sql, and save it to your GitHub repository

     (iv) Create a new Postgres database, named crowdfunding_db

     (v) Using the database schema, create the tables in the correct order to handle the foreign keys.

     (vi) Verify the table creation by running a SELECT statement for each table.

     (vii) Import each CSV file into its corresponding SQL table.

     (viii) Verify that each table has the correct data by running a SELECT statement for each.


**(4) Data Visualization Techniques:**


The ERD and DataFrames are the only data visualization outputs from this ETL pipeline.


**(5) Results and Analysis:**


The Crowdfunding Database is available for any SQL-related queries that the company wants to use to review and visualize their crowdfunding data.


**(6) Ethical Considerations:**


The initial datasets contain financial and contact information and thus, likely should be considered sensitive and stored with safeguards to allow for data theft. Restricting access to the data is also a viable mitigation to avoid data theft.


**(7) Instructions for Interacting with the Project:**


(a) Files stored in the **Resources** folder

     (i) Two original datasets "crowdfunding.xlsx" and "contacts.xlsx" 

     (ii) Four new .csv files ("campaign.csv"; "category.csv"; "contacts.csv"; and "subcategory.csv")


(b) The SQL file and ERD picture are filed in the **ERD** folder


(c) There are several .ipynb files in the main folder. The final code is located in the file titled "ETL_Mini_Project_rroop_calbertini.ipynb". Two .ipynb code files capture the individual work of each partner.


**(8) Citations:**


(a) Richard used the Xpert Learning Assistant and Office Hours with Instructor to code the 'for loop' in the contacts_df build

(b) Instructor assisted with SQL question during class

