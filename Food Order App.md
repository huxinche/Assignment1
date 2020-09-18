User:\
&emsp;Data: loginCredentials, address\
&emsp;Behavior: getRecommendation, selectRestaurant, selectMeal, makeOrder, cancelOrder, confirmOrder, reorder, vewHistoryOrders, selectHistoryOrder, placeDelivery, cancelDelivery.

OrderStatus(enumeration type):\
&emsp;NotAccepted, Refused, Uncooked, Cooking, Cooked, Delivering, Finished

Delivery:\
&emsp;Data: from, to, commission.

Order:\
&emsp;Data: restaurant, foodList, orderStatus, delivery

Restaurant:\
&emsp;Data: loginCredentials\
&emsp;Behavior: checkOrder, updateOrderStatus

Courier:\
&emsp;Data: loginCredentials\
&emsp;Behavior: checkDelivery, acceptDelivery

User jessi\
Order anorder\
Delivery adelivery\
Restaurant kfc\
Courier jeff

### Process of order a meal:
jessi.login(loginCredentials)\
if jessi want to eat something she has ordered before\
&emsp;&emsp;anorder = jessi.reorder(jessi.selectHistoryOrder(jessi.viewHistoryOrders()))\
else\
&emsp;&emsp;kfc = jessi.selectRestaurant(jessi.getRecommendations())\
&emsp;&emsp;adelivery = jessi.placeDelivery(kfc, jessi, timeLimitation, commision)\
&emsp;&emsp;while adelivery is not accepted:\
&emsp;&emsp;&emsp;&emsp;jessi increase commision\
&emsp;&emsp;&emsp;&emsp;adelivery= jessi.placeDelivery(kfc, jessi, timeLimitation, commision)\
&emsp;&emsp;anorder = jessi.placeOrder(adelivery, kfc)\
if jessi changes her mind\
&emsp;&emsp;if anorder.orderStatus < Cooking\
&emsp;&emsp;&emsp;&emsp;jessi.cancelOrder(anorder)\
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;jessi.cancelDelivery(adelivery) // commission partly or fully given


jeff.login(loginCredentials)\
adelivery = jeff.checkDelivery();\
if jeff think adelivery.commission is fair\
&emsp;&emsp;jeff.acceptDelivery(adelivery)\
else\
&emsp;&emsp;delivery pass to other couriers\

kfc.login(loginCredentials)\
anorder = kfc.checkOrder()\
if all food on anorder.foodList is avalaible\
&emsp;&emsp;kfc.updateOrderStatus(anorder, Uncooked)\
else\
&emsp;&emsp;kfc.updateOrderStatus(anorder, Rejected)\
if food start cooking\
&emsp;&emsp;kfc.updateOrderStatus(anorder, Cooking)\
if food cooked\
&emsp;&emsp;kfc.updateOrderStatus(anorder, Cooked)\
&emsp;&emsp;if courier has come\
&emsp;&emsp;&emsp;&emsp;kfc package food and give to courier\
&emsp;&emsp;&emsp;&emsp;kfc.updateOrderStatus(anorder, Delivering)














