# Node-red workshop

This github repository is meant for learning how to setup and use node-red with IBM services on IBM cloud.



## Prerequisites. 

Before we begin, we need to setup some services on IBM cloud, mainly *node-red community*, *Weather services* and *Watson Text To Speech*.

### Setting up node-red-community

#### Setup service.

To setup your service, go to IBM cloud, and click on "create resource" on the top of the page. 

In the search bar on the top of the page, write node-red. Choose the on which says "Community" below the name. ![Node-red Starter](/Users/jacobhougaardbennedsen/WebstormProjects/node-red-workshop/assets/Node-red Starter.png)

You now have to choose the option which says "Cloudant". This will create a no-sql database along with your instance which will store your configurations and can be used for saving data from nodes. 

![Choose-node-red](/Users/jacobhougaardbennedsen/WebstormProjects/node-red-workshop/assets/Choose-node-red.png)

Afterwards your instance may take a couple of minutes to start up. 

When your node-red instance is ready, click on the link which says "Visit App URL" next to the name. 



#### Configuring your node-red service.

The first thing that you will be presented with when logging on to your instance is a screen which asks you to create a username and password. This is mandatory, but we reccomend that you do it anyway.

### ![secure-node-red](/Users/jacobhougaardbennedsen/WebstormProjects/node-red-workshop/assets/secure-node-red.png)

After exiting the setup, you should be presented with a web-page with a large button. Click on the button to go to your node-red flow. 

#### Installing node-red dashboard.

When entering your workflow click on the menu at the top left of the screen, and click on *"Manage palette"*

![secure-node-red](/Users/jacobhougaardbennedsen/WebstormProjects/node-red-workshop/assets/secure-node-red.png)

a user settings panel should pop up (see above). From here, click on the install tab and search for node-red dashboard and click on the install button.

### Setting up Weather services



### Setting up text to speech



## A quick node-red overview

As described by the node-red webpage *"Node-RED is a programming tool for wiring together hardware devices, APIs and online services in new and interesting ways."*. It removes a lot of "boilerplate" code and presents services as nodes, which can be plugged together to create complex workflows.

## Setting up our dashboard.

Before we can start working with the IBM services, we first need to have somewhere to display it. If you followed the prerequisites you should be able to see something when going to your-dashboard-url/ui. Since we havent created anything you should be prompted with an empty page. 



