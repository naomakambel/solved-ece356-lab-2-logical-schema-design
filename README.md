Download Link: https://assignmentchef.com/product/solved-ece356-lab-2-logical-schema-design
<br>
<h1>Overview of Employee Database</h1>

In Lab 1, you worked with the Employee database. The schema for Lab 1 had four tables: Employee, Project, Assigned and Department. For Lab 2, we provide a modified version of the Lab 1 schema in the starter code file <em>part1.sql</em>. The highlights of the new data model are as follows:

The Employee name is a compound attribute comprising a first name (emp fname), last name (emp lname), and initials (emp initials).

The Department location is a single attribute comprising the street number (streetNum), street name (streetName), city name (cityName), province (province), and postal code (postalcode).

The Assigned table has additional columns: roleID, start date, end date, assigned status, and role level.

The tables in the Lab 2 model are illustrated in Figure 1. The primary and foreign keys are missing in this figure because adding them is a requirement of this lab.

Figure 1: Initial schema for Lab 2.

Table 2 describes the functional dependencies that you should consider for this lab.

<table width="637">

 <tbody>

  <tr>

   <td width="97"><strong>Table Name</strong></td>

   <td width="539"><strong>Functional dependencies</strong></td>

  </tr>

  <tr>

   <td width="97"><em>Department</em></td>

   <td width="539">deptID → deptName, location</td>

  </tr>

  <tr>

   <td width="97"><em>Project</em></td>

   <td width="539">projID → title, phase, budget, funds</td>

  </tr>

  <tr>

   <td width="97"><em>Employee</em></td>

   <td width="539">empID → emp fname, emp initials, emp lname, job, deptID, salary</td>

  </tr>

  <tr>

   <td width="97"><em>Assigned</em></td>

   <td width="539">empID, projID, roleID → role description, role level, start date, end date, assigned status roleID → role description, role level</td>

  </tr>

 </tbody>

</table>

Table 2: Functional dependencies for the schema in Figure 1.

<h1>Part 1: Adding Primary Key and Foreign Key Constrains</h1>

Add to the database schema all the relevant primary key constrains and foreign key constrains, as determined using the information provided below:

<ul>

 <li>The empID uniquely identifies one employee.</li>

 <li>The deptID uniquely identifies one department.</li>

 <li>The projID uniquely identifies one project.</li>

 <li>An employee may be assigned to any number (including zero) of projects.</li>

 <li>An employee <strong>must </strong>be assigned to at least one role in a project.</li>

</ul>

Using the provided <em>part1.sql </em>file as the starting point, modify the SQL DDL statements to incorporate the required constraints. Do not add or remove any tables or columns in this part of the lab. Also, please preserve the drop table statements at the top of the <em>part1.sql </em>file so that the script can be run repeatedly without raising errors.

<strong>Submission instructions: </strong>For this part of the lab, the deliverable is your modified version of the provided <em>part1.sql </em>file with the appropriate primary and foreign key constraints added. This is one of several files you will submit for Lab 2.

<h1>Part 2: Normalization to 1NF, 3NF, BCNF</h1>

In this part of the lab, the starting point is your modified schema from Part 1, which includes the primary keys and foreign keys you added. You will transform this schema by applying different normalization procedures. For each of the questions below (A, B1, and B2), you will need to:

Decide if the schema already satisfies the required normal form.

If not, apply the techniques taught in lecture to transform the schema so that it satisfies the required normal form.

Draw a relational schema diagram, similar to Figure 1 but showing primary and foreign keys, representing your normalized schema.

<ol>

 <li>A) What modifications to your schema from Part 1, if any, are needed to ensure that it is in 1NF? (10%)</li>

</ol>

B1) What modifications to your 1NF schema from (A), if any, are needed to ensure that it is in 3NF? (35%)

B2) What modifications to your 1NF schema from (A), if any, are needed to ensure that it is in BCNF? (35%)

<strong>Note 1: </strong>For A, if you find that the schema is not in 1NF then address the problem <strong>without adding any tables to the schema</strong>.

<strong>Note 2: </strong>For B1 and B2, please show all your work including the 3NF and BCNF test discussed in lecture, as well as the steps of any decomposition, if applicable. The grader will deduct marks for missing details. If you are using the simplified 3NF or BCNF test, please justify why such a test is applicable.

<strong>Note 3: </strong>B1 and B2 both build on A, which builds on your schema from Part 1. Do <strong>not </strong>use the schema from B1 as the starting point for B2, or vice versa. (I.e., do not simply use the argument that a BCNF schema also satisfies 3NF.)

<strong>Note 4: </strong>When analyzing the schema for different normal forms, you may ignore any redundancy (e.g., due to non-atomic value domains or due to functional dependencies) related to postal codes.

<strong>Submission instructions: </strong>For this part of the lab, please write a report and save it as a PDF file named <em>part2.pdf</em>. This document will be graded manually, so please <strong>include the names and student IDs </strong>of all group members on the title page. The document should be submitted to the same dropbox as your SQL script from Part 1. The dropbox will be configured to accept multiple files per submission.

<h1>Part 3: SQL DDL for BCNF</h1>

Write SQL DDL code for the BCNF schema you created in Part 2 question B2. Use your modified <em>part1.sql </em>file from Part 1 as the starting point, and save the new script in a file named <em>part3.sql</em>. Note that the script contains several INSERT INTO statements, which must be modified to accommodate any changes you have made to the schema.