Student:\
&emsp;Data: Email, loginCredentials, major\
&emsp;Behavior: login, viewCourses, selectCourse, viewAssignments, selectAssignment, submitAssignment, updateSubmission\

Course:\
&emsp;Data: assignments

Assignment:\
&emsp;Data: deadline, submitLimitation

Submission:\
&emsp;Data: student, assignment, materials, timeSubmitted

Staff:\
&emsp;Data: loginCredentials\
&emsp;Behavior: login, viewCourses, selectCourse, addAssignment, updateAssignment, startSubmitting.

Student jessi\
Course info5100\
Assignment assignment1\
Submission asubmission\
Staff siva

Process of adding an assignment to course:\
siva.login(loginCredentials)\
info5100 = siva.selectCourse(siva.viewCourses())\
assignment1 = siva.addAssignment(info5100)\
if siva want to update this assignment\
&emsp;&emsp;siva.updateAssignment(assignment1)\
siva.startSubmitting(assignment1)

Process of student submitting assignment:\
info5100 = jessi.selectCourse(jessi.viewCourses())\
assignment1 = jessi.selectAssignment(jessi.viewAssignments(info5100))\
if submission deadline not reached\
&emsp;&emsp;asubmission = jessi.submitAssignment(assignment1, materials)\
&emsp;&emsp;asubmission.timeSubmitted = 1\
else\
&emsp;&emsp;jessi can not submit \
if jessi want to update asubmission\
&emsp;&emsp;if asubmission.deadline not reached\
&emsp;&emsp;&emsp;&emsp;if asubmission.timeSubmitted < assignment1.submitLimitation\
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;jessi.updateSubmission(asubmission, materials)\
&emsp;&emsp;&emsp;&emsp;else\
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;jessi can not update\
&emsp;&emsp;else\
&emsp;&emsp;&emsp;&emsp;jessi can not update
    



