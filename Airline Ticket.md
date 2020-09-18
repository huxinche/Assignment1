Flight:\
&emsp;Data: seats\
&emsp;Behavior: checkSeats, bookSeat, cancelBook

Ticket:\
&emsp;Data: passenger, flight, seat

Passenger:\
&emsp;Data: loginCredentials\
&emsp;Behavior: searchFlight, selectFlight, placeOrder, makePayment, cancelOrder

Order:\
&emsp;Data: passenger, flight, seat, paymentStatus\
&emsp;Behavior: confirm, invalid

 
Passenger jessi\
Order anorder\
Ticket aticket\
(Flight is determined in runtime.)

### Process of buying a ticket:

jessi.login(loginCredentials)\

flight = jessi.selectFlight(jessi.searchFlight(from, to, noEarlierThan, noLaterThan))\

while flight.checkSeats() == false\
&emsp;&emsp;flight = jessi.selectFlight(jessi.searchFlight(from, to, noEarlierThan, noLaterThan))


anorder = flight.bookSeat(jessi)\
if jessi changes her mind\
&emsp;&emsp;jessi.cancelOrder(anorder)\
&emsp;&emsp;flight.cancelBook(jessi)\
else if anorder is not payed within 30 minutes\
&emsp;&emsp;flight.cancelBook(jessi)\
&emsp;&emsp;anorder.invalid()\
else\
&emsp;&emsp;success = jessi.makePayment(anorder)\
&emsp;&emsp;while success == false\
&emsp;&emsp;&emsp;&emsp;success =  jessi.makePayment(anorder)\
&emsp;&emsp;aticket = anorder.confirm(anorder.passenger, anorder.flight, anorder.seat)









