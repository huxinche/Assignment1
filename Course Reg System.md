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

### Process of Register a course:

siva.login(loginCredentials)\
info5100 = siva.openCourse()\
info5100.staffs.add(siva)\
siva.startRegister(info5100);


jessi.login(loginCredentials)\
info5100 = jessi.selectCourse(jessi.viewCourses())\
if info5100 is not fully booked\
&emsp;&emsp;if info5100 has no prerequisite or jessi has meet the requirements\
&emsp;&emsp;&emsp;&emsp;jessi.bookCourse(info5100)\
&emsp;&emsp;&emsp;&emsp;info5100.students.Add(jessi)\
&emsp;&emsp;&emsp;&emsp;if jessi changes her mind\
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;if info5100 has not started yet\
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;jessi.cancelCourse(info5100)\
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;jessi.students.remove(jessi)\
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;else\
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;jessi can not cancel\
&emsp;&emsp;else\
&emsp;&emsp;&emsp;&emsp;jessi can not book info5100

siva.endRegister(info5100)


