Download Link: https://assignmentchef.com/product/solved-cs348-project1
<br>
Given the following entities, provide the SQL queries corresponding to the questions below:




Note:

<ol>

 <li>The schema definition of these tables and sample test data are provided in <strong>sql</strong> and <strong>data.sql</strong>, respectively<strong>.</strong></li>

 <li>You should finish all your work in <strong>sql</strong>.</li>

 <li>We provide <strong>sh</strong> script to test your sql queries on sample test data, but we will use different data when grading. Feel free to modify/add your sample test data in order to polish your queries. (You need to verify your answer by yourselves<u> if you change the</u> <u>sample test data</u>. In this case, test.sh may not work.)</li>

 <li>How to use <strong>sh</strong>. First, set the variables “username” and “pword” in the script with your oracle account with “@csora” and your password. Second, execute the <strong>tables.sql</strong> and <strong>data.sql</strong>. Then

  <ol>

   <li>“./test.sh” test all 10 queries;</li>

   <li>“./test.sh $(Query_number)” test one specific query. For example, “./test.sh 1”</li>

  </ol></li>

 <li>Submit your answers via Blackboard.</li>

 <li><strong><u>Do not use PL/SQL for this homework</u>, just a main SQL select statement per question (subqueries, i.e., nested queries, are allowed).</strong></li>

 <li>DO NOT delete/change the “– Query[0-9]*” comment in the <strong>sql</strong> file.</li>

 <li>Grading: We will use script to grade your projects. There will be <strong>no</strong> partial credit for each query.</li>

 <li>For those “select top X” problems, assume that there is no tie condition that will influence the result. That is, the values in the column that may affect the result of selecting top X are distinct.</li>

</ol>




<strong>Write SQL queries for questions 1-10 using the following University schema.</strong>

<strong> </strong>

<em>Classroom(<u>building</u>, <u>room_number</u>, capacity)</em>

<em>Department(<u>dept_name</u>, building, budget)</em>

<em>Course(<u>course_id</u>, title, dept_name, credits)</em>

<em>Instructor(<u>i_id</u>, name, dept_name, salary) </em>

<em>Section(<u>course_id</u>, <u>sec_id</u>, <u>semester</u>, <u>year</u>, building, room_number, time_slot_id)</em>

<em>Teaches(<u>i_id</u>, <u>course_id</u>, <u>sec_id</u>, <u>semester</u>, <u>year</u>)</em>

<em>Student(<u>s_id</u>, name, dept_name, tot_cred)</em>

<em>Takes(<u>s_id</u>, <u>course_id</u>, <u>sec_id</u>, <u>semester</u>, <u>year</u>, grade)</em> <em>Advisor(<u>s_id</u>, i_id)</em>

<em>Time_slot(<u>time_slot_id</u>, <u>day</u>, <u>start_hr</u>, <u>start_min</u>, end_hr, end_min)</em>

<em>Prereq(<u>course_id</u>, <u>prereq_id</u>)</em>

<em>Grade_points(<u>grade</u>, points)</em>

<ol>

 <li>(10 points) Find the s_ids and names of all students who were taught by an instructor named ‘Katz’.</li>

</ol>

<sub>            </sub>Output columns: <em>Name</em>

Sort by: <em>Name</em> in ascending order




<table width="387">

 <tbody>

  <tr>

   <td width="192"><em>S_ID</em></td>

   <td width="195"><em>Name</em></td>

  </tr>

 </tbody>

</table>




<ol start="2">

 <li>(10 points) Calculate the <em>grade-point average </em>of every student.</li>

</ol>

Output columns: <em>S_ID, </em> <em>GradePointAverage</em>

Sort by: <em>GradePointAverage</em> in descending order

Note: The GradePointAverage should round up to 2 digits after decimal point.

<sub>            </sub>(e.g. 3.42857 should be shown as 3.43)




<table width="387">

 <tbody>

  <tr>

   <td width="192"><em>S_ID</em></td>

   <td width="195"><em>GradePointAverage</em></td>

  </tr>

 </tbody>

</table>




<ol start="3">

 <li>(10 pts) Find the enrollment of each section that was offered in the Fall of 2009. Display the <em>Course_id, sec_id </em>and the <em>count</em> (which is the number of students enrolled in this section.)</li>

</ol>




Output columns: <em>Course_id, sec_id, Count</em>

Sort by: <em>Count </em>in descending order







<table width="262">

 <tbody>

  <tr>

   <td width="107"><em>Course_id</em></td>

   <td width="77"><em>sec_id</em></td>

   <td width="78"><em>Count</em></td>

  </tr>

 </tbody>

</table>




<ol start="4">

 <li>(10 pts) Find the sections that had the maximum enrollment in the Fall of 2009.</li>

</ol>

(There could be more than one course section which has the maximum enrollment.) Output columns: <em>Course_id, sec_id </em>

Sort by: <em>Course_id</em> in ascending order




<table width="364">

 <tbody>

  <tr>

   <td width="226"><em>Course_id</em></td>

   <td width="137"><em>sec_id</em></td>

  </tr>

 </tbody>

</table>




<ol start="5">

 <li>(10 pts) Find the names of the <u>top 4 instructors</u> who have taught the most number of distinct courses. Display also the total number of courses taught.</li>

</ol>

Output columns: <em>InstructorName, NumberOfCoursesTaught</em>

Sort by: <em>NumberOfCoursesTaught</em><em>  </em>in descending order (in case of ties order by the <em>InstructorName</em>)







<table width="306">

 <tbody>

  <tr>

   <td width="120"><em>InstructorName</em></td>

   <td width="186"><em>NumberOfCoursesTaught</em></td>

  </tr>

 </tbody>

</table>




<ol start="6">

 <li>(10 pts) Find the top 3 semesters in which the most number of courses were offered.</li>

</ol>

(Treat Spring of 2009 and Spring of 2010 as two different semesters)

Output columns: <em>Semester, Year, NumberOfCourses</em>

<em>   </em>Sort by: <em>NumberOfCourses in descending order</em>




<table width="338">

 <tbody>

  <tr>

   <td width="108"><em>Semester</em></td>

   <td width="84"><em>Year</em></td>

   <td width="147"><em>NumberOfCourses</em></td>

  </tr>

 </tbody>

</table>




<ol start="7">

 <li>(10 pts) Find the top 2 students who have taken the most number of courses.</li>

</ol>

Output columns: <em>S_ID, StudentName, NumberOfCourses</em>

Sort by: <em>NumberOfCourses in descending order</em>




<table width="328">

 <tbody>

  <tr>

   <td width="72"><em>S_ID</em></td>

   <td width="114"><em>StudentName</em></td>

   <td width="142"><em>NumberOfCourses</em></td>

  </tr>

 </tbody>

</table>




<ol start="8">

 <li>(10 pts) Find the top 4 instructors whose courses have the maximum enrollment in all of their courses combined.</li>

</ol>

Output columns: <em>InstructorName, TotalEnrollment</em>

<em>      Sort by: TotalEnrollment in descending order</em>




<table width="309">

 <tbody>

  <tr>

   <td width="156"><em>InstructorName</em></td>

   <td width="153"><em>TotalEnrollment</em></td>

  </tr>

 </tbody>

</table>




<ol start="9">

 <li>(10 pts) List all the courses offered by the departments ‘Comp. Sci.’ and ‘History’.</li>

</ol>

Output should not contain any duplicates.  Output columns: <em>DepartmentName, CourseID</em> Sort by: <em>CourseID </em>in ascending order.




<table width="309">

 <tbody>

  <tr>

   <td width="192"><em>DepartmentName</em></td>

   <td width="117"><em>CourseID</em></td>

  </tr>

 </tbody>

</table>




<ol start="10">

 <li>(10 pts) List all the courses that have prerequisites offered by a different department.</li>

</ol>

Output columns: <em>Course_id, Course_department, Prereq_id, Prereq_department</em>

Sort by: <em>Course_id in ascending order</em>

<em> </em>

<table width="401">

 <tbody>

  <tr>

   <td width="102"><em>Course_id</em></td>

   <td width="102"><em>Course_dept</em></td>

   <td width="96"><em>Prereq_id</em></td>

   <td width="101"><em>Prereq_dept</em></td>

  </tr>

 </tbody>

</table>

<em>                  </em>




<strong>Submission instructions:</strong>

<strong> </strong>

Please submit via Blackboard the following:




Your SQL script (<strong>answer.sql</strong>). It should contain the 10 SQL queries and look like the <sub>            </sub>following:

-‐Query1

Select…….

………

— Query10

Select……..





