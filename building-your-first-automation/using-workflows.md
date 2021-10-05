---
description: >-
  In this section, we'll use a Workflow to connect the front-end App to the
  back-end Automation, so that we can serve our image on our App!
---

# Using Workflows

Just to recap, so far we have:

* Created our front-end user-facing App
* Created our Automation project with

  * a Datastore to save an image of our animal
  * an Activity to fetch the image of our animal and save it to the Datastore

Now we'll add a Workflow that calls the Activity to action when the user inputs a new animal. Return to the Automation dashboard, and click "Add Workflow".

![Automation Dashboard](../.gitbook/assets/image%20%283%29.png)

Once you've named your workflow and given it a description, you'll be pulled through to the Workflow Designer.

![Workflow Designer](../.gitbook/assets/image%20%282%29.png)

The canvas is where we'll drag and drop elements from the "Nodes", "Activities", and "Actions & Integrations" tabs to build our Workflow. Start by opening the Nodes tab, to reveal the _Start_ and _Stop_ nodes. Drag them down onto the canvas.

![Adding Start and Stop nodes to our Workflow](../.gitbook/assets/image%20%2811%29.png)

Every workflow **must** have a Start and Stop node. Now, we'll select the "Activities" tab and drag our "Get Animal Image" Activity onto the canvas.

![Adding our Activity to our Workflow](../.gitbook/assets/image%20%2852%29.png)

Selecting each element in our Workflow will allow us to connect them together in a logical cause-effect manner.

![Connecting Workflow elements](../.gitbook/assets/image%20%2857%29.png)

Once an element is selected, drag the grey arrow as shown above to the next element to connect them together. Connect the Start node to the Activity element, and the Activity element to the Stop node.

![Connected elements in our Workflow](../.gitbook/assets/image%20%2831%29.png)

Awesome! Everything's set for us to stitch it all together using Event Listeners.

