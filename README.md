# Crime Reporting and Management System

This is the backend of the Crime Reporting and Management System.

## **DB Schema**

### **Users**

This is the information stored in the database for every user created

- user_id (PK)
- name
- username/email (Unique Identifier)
- profile_picture
- address
- password
- is_active
- user_type (**ENUM**: USER, STAFF, ADMIN)

### **Crimes**

This is the information stored in the database for every crime reported

- crime_id (PK)
- crime_type
- reporter (**FK**: Users - **_user_id_**)
- details
- status (**ENUM**: PENDING, CLOSED)
- assignee (**FK**: Users - **_user_id_**)

### **Files**

This is the information stored for every uploaded file

- file_id (PK)
- download_link
- crime (**FK**: Crime - **_crime_id_**)

## **Privileges**

### **Everybody's Privileges**

These are priveleges that everyone has

- Would be able to create and edit their profile (_Will not be able to create an account as a staff or an admin_)

### **User Privileges**

These are privileges that applies to users with the user_type **USERS**

- Would be able to report crimes
- Would be able to view all of the crimes they have reported

### **Staff Privileges**

These are privileges that applies to users with the user_type **STAFF**

- Would be able to view assigned crimes
- Would be able to update the status of an assigned crime

### **Admin Privileges**

These are privileges that applies to users with the user_type **ADMIN**

- Would be able to view reported crime details
- Would be able to view the profile of the user that reported a crime
- Would be able to create and delete a staff login
- Would be able to assign a crime to a specific staff
- Would have no restriction
