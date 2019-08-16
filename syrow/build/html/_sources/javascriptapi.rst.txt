javaScript APIs
================



.. function:: CHATTER_FUNCTION.sendCustomMessage(message,is_hidden);

    In this function you have to pass the boolean value(true / false) for parameter ``is_hidden`` . 

    * This function will make visitor messages hidden, it will be shown only in agent chatbox.

    
.. function:: CHATTER_FUNCTION.hideChatBox();

    This function will hide entire chat box.

.. NOTE::

    * There is no parameter for this function so you don't have to pass any value and this note is applicable for these all functions.

.. function:: CHATTER_FUNCTION.displayChatBox();

    This function will display chat box which is hidden.

.. function:: CHATTER_FUNCTION.openChat();

    This function open the chat box quickly.

.. function:: CHATTER_FUNCTION.closeChat();

    This function close the chat box quickly.

.. function:: CHATTER_FUNCTION.clearCookies();

   This function will clear uid and visitor details from cookies.

.. function:: CHATTER_FUNCTION.getVisitorDetails();

    This function will return visitor details.

.. function:: setVisitorDetails(name , phoneNumber , email);

   Delete existing cookie of name "uidDetails" i.e. post name, phone no and email in database (table name: Visitor) and create cookie "uidDetails" with new name, phone no and email.

.. function:: setColors(bubbleColor , windowColor , fontColor);

   Set chat window color, chat bubble color, and icon color using bubbleColor , windowColor , fontColor respectively.


.. function:: CHATTER_FUNCTION.resetColor();
   
    This function will reset to default color scheme.




function ::


  
 CHATTER_FUNCTION.sendCustomMessage(message,is_hidden); 
 // is_hidden - true / false

 CHATTER_FUNCTION.hideChatBox();
 // this will hide entire chat box

 CHATTER_FUNCTION.displayChatBox();

 CHATTER_FUNCTION.openChat();

 CHATTER_FUNCTION.closeChat();

 CHATTER_FUNCTION.clearCookies();
 // clear uid and visitor details from cookies.

  CHATTER_FUNCTION.getVisitorDetails();
 //return visitor details

 CHATTER_FUNCTION.setVisitorDetails(name, phoneNumber, email);

 CHATTER_FUNCTION.setColors(window_color, icon_color, font_icon_color, support_bubble_color);

 CHATTER_FUNCTION.resetColor();
 //reset to defafault

 function setVisitorDetails(name , phoneNumber , email) {
    //delete existing cookie of name "uidDetails"
    //post name, phone no and email in database (table name: Visitor)
    //create cookie "uidDetails" with new name, phone no and email
 }

 function setColors(bubbleColor , windowColor , fontColor) {
    //set chat window color, chat bubble color, and icon color using bubbleColor , windowColor , fontColor respectively
 }


.. figure::  images/bubblecolor.png
	   :align:   center

.. figure::  images/font-windowcolor.png
	   :align:   center

Above images will help you to understand what is bubble, window and font colors.



