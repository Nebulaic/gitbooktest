---
description: 'In this section, we''ll connect everything together with Event Listeners.'
---

# Linking Everything with Event Listeners

An event listener is a service that waits for a **call** to trigger an **event**. In this case, the App makes a call to start the "Get Animal Image" action \(i.e. the event\). There are a number of ways to create and use event listeners on the Toca platform, with the upcoming In Page Logic \(IPL\) functionality of Version 5.43 set to make event listeners even more accessible and powerful.

We'll start where we left off, inside of the Workflow Designer. Click the Start node, then "Add Listener" in the right-hand drawer.

![Adding an event listener](../.gitbook/assets/image%20%2841%29.png)

![Create Listener Wizard](../.gitbook/assets/image%20%2844%29.png)

Make sure to turn off "**Private**" for now - that'll complicate things too far for our purposes. We'll also need an **input** for our listener - this will be the text that the user inputs in the app \(e.g. "lion"\) that we pass to our Activity to perform the image search.

![Creating an input](../.gitbook/assets/image%20%2842%29.png)

We'll give it a name and a default value.

![Naming our input and adding a default animal \(I like honeybadgers...\)](../.gitbook/assets/image%20%289%29.png)

Okay! Save everything here and move across to the App Designer.

![Adding our listener to the Form Layout App Component](../.gitbook/assets/image%20%2828%29.png)

Select the Form Layout component \(the easiest way to do this is to click the Text Input, then hit ↑\) and in the Properties panel on the right, type the name of the listener. That's all we have to do here. 

The Form Layout component will grab any values from inputs within the form \(in this case, only the Text Input\) and call the event listener when the "SUBMIT" button is clicked. 

However, we need to explicitly tell it to pass the contents of the Text Input as our "image\_string". Click back on the Text Input and in the Properties panel, select _image\_string_ in the "Form Input" dropdown.

![Linking the Text Input to the image\_string](../.gitbook/assets/image%20%2833%29.png)

We also need to let the App know about our Datastore. Click the cog icon in the top right, then "App Resources" to add the "My First Automation" Automation to the App. Make sure to "Add Item" to add our Animal Store.

![Accessing App Settings](../.gitbook/assets/image%20%2827%29.png)

![Adding Animal Store to our App](../.gitbook/assets/image%20%2861%29.png)

Hit "Apply" and close. Finally, click on the Image component, and use the "{x} Pick Datachip" button to add the Image we saved in our Datastore. Make sure to set the "Variable" to _animal_ and the "Update Rate" to 1 second \(not -1!\)

![Adding Image from Datachip](../.gitbook/assets/image%20%2843%29.png)

![](../.gitbook/assets/image%20%2812%29.png)

Awesome! We're all done on the app side. Now, we just need to pass the image\_string to the "Get Animal Image" Activity back in the Activity Designer. Make sure to save your App before you go!

We need to add an input to our Activity with the same name as our listener is expecting to receive from the App. In our case, this is "image\_string". Click on the "Input & Output" tab at the top left of the page.

![Adding an Input to our Activity](../.gitbook/assets/image%20%2824%29.png)

Then "Add Variable" under Inputs:

![](../.gitbook/assets/image%20%2873%29.png)

The name of the variable **must** match the name of the input to our listener so that the listener properly passes the user input from the App to the Activity.

![N.B. The names of the input to the listener and the Activity MUST match!](../.gitbook/assets/image%20%2849%29.png)

Now we'll take this input and pass it to the Text Input Action. Click the pencil \(edit\) on our Text Input Action.

![Back in the Activity Designer](../.gitbook/assets/image%20%2845%29.png)



![](../.gitbook/assets/image%20%2819%29.png)

We'll now link the "Text" using the "{x}" Datachip button, with the input from our event listener. Click back on "Input & Output" then select the "image\_string" Datachip to pull it into the Text Input.

![](../.gitbook/assets/image%20%2858%29.png)

![](../.gitbook/assets/image%20%2814%29.png)

![](../.gitbook/assets/image%20%2826%29.png)

Then save - that's it! Now we just need to publish.

