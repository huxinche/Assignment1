User:\
Data: loginCredentials, address\
Behavior: getRecommendation, selectRestaurant, selectMeal, makeOrder, cancelOrder, confirmOrder, reorder, vewHistoryOrders, selectHistoryOrder, placeDelivery, cancelDelivery.

OrderStatus(enumeration type):\
NotAccepted, Refused, Uncooked, Cooking, Cooked, Delivering, Finished

Delivery:\
Data: from, to, commission.

Order:\
Data: restaurant, foodList, orderStatus, delivery

Restaurant:\
Data: loginCredentials\
Behavior: checkOrder, updateOrderStatus

Courier:\
Data: loginCredentials\
Behavior: checkDelivery, acceptDelivery
 
User: jessi\
Order: anorder\
Delivery: adelivery\
Restaurant: kfc\
Courier: jeff

Process of order a meal:\
jessi.login(loginCredentials)\
if jessi want to eat something she has ordered before\
anorder = jessi.reorder(jessi.selectHistoryOrder(jessi.viewHistoryOrders()))\
else\
kfc = jessi.selectRestaurant(jessi.getRecommendations())\
adelivery = jessi.placeDelivery(kfc, jessi, timeLimitation, commision)\
while adelivery is not accepted:\
jessi increase commision\
adelivery= jessi.placeDelivery(kfc, jessi, timeLimitation, commision)\
anorder = jessi.placeOrder(adelivery, kfc)\
if jessi changes her mind\
if anorder.orderStatus < Cooking\
jessi.cancelOrder(anorder)\
jessi.cancelDelivery(adelivery) // commission partly or fully given


jeff.login(loginCredentials)\
adelivery = jeff.checkDelivery();\
if jeff think adelivery.commission is fair\
jeff.acceptDelivery(adelivery)\
else\
delivery pass to other couriers\

kfc.login(loginCredentials)\
anorder = kfc.checkOrder()\
if all food on anorder.foodList is avalaible\
kfc.updateOrderStatus(anorder, Uncooked)\
else\
kfc.updateOrderStatus(anorder, Rejected)\
if food start cooking\
kfc.updateOrderStatus(anorder, Cooking)\
if food cooked\
kfc.updateOrderStatus(anorder, Cooked)\
if courier has come\
kfc package food and give to courier\
kfc.updateOrderStatus(anorder, Delivering)














