Pet:\
&emsp;Data: species, picture, age, source, requirements.

Adopter:\
&emsp;Data: loginCredentials, petsAdopted, reputation\
&emsp;Behavior: login, viewPets, selectPet, appointAdoption, cancelAppointment

Appointment:\
&emsp;Data: adopter, accepted, startTime, endTime, location, pet.

Manager: \
&emsp;Data: loginCredentials\
&emsp;Behavior: addPet, checkAppointment, acceptAppointment, rejectAppointment, approveAdoption.

 
Pet cat\
Adopter jessi\
Appointment anappointment\
Manager tom **

### Process of Adoption
#### Manager add a new pet:
tom.login(loginCredentials)\
cat = tom.addPet(species, age, source, pictures, requirments)

#### Adopter view pets and make an appointment:
jessi.login(loginCredentials)

cat = jessi.selectPet(jessi.viewPets())\
jessi check cat by viewing cat.species, cat.picture, cat.age, cat.source and cat.requirments\
if jessi is satisfied with cat\
&emsp;anappointment = jessi.appointAdoption()

#### Manager handle appointment:
anappointment = tom.checkAppointment()\
jessi = anappointment.adopter\
tom check jessi by checking jessi.reputation and jessi.petsAdopted\
if tom think jessi is a good candidate \
&emsp;tom.acceptAppointment(anappointment)\
else \
&emsp;tom.rejectAppointment(anappointment)

#### After manager handle the appointment
if anappointment is accepted\
&emsp;if jessi changes her mind\
&emsp;&emsp;essi.cancelAppointment(anappointment)\
&emsp;else if jessi missed appointment time\
&emsp;&emsp;jessi.reputation get worse\
&emsp;else\
&emsp;&emsp;jessi go to the adoption center located at anappointment.location

#### At the Adoption center:
tom.approveAdoption(anappointment)







