Student:\
&emsp;Data: loginCredentials\
&emsp;Behavior: login, viiewCourses, selectCourse, registerCourse, cancelCourse.

Course:\
&emsp;Data: Name, Description, prerequisite, startTime, endTime, staffs, students.

Staff:\
&emsp;Data: loginCredentials\
&emsp;Behavior: login, openCourse, startRegister, endRegister

 
Student jessi\
Course info5100\
Staff siva

Process of Register a course:

siva.login(loginCredentials)\
info5100 = siva.openCourse()\
info5100.staffs.add(siva)\
siva.startRegister(info5100);


jessi.login(loginCredentials)\
info5100 = jessi.selectCourse(jessi.viewCourses())\
if info5100 is not fully booked\
if info5100 has no prerequisite or jessi has meet the requirements\
jessi.bookCourse(info5100)\
info5100.students.Add(jessi)\
if jessi changes her mind\
if info5100 has not started yet\
jessi.cancelCourse(info5100)\
jessi.students.remove(jessi)\
else\
jessi can not cancel\
else\
jessi can not book info5100

siva.endRegister(info5100)


