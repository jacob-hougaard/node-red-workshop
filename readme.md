# Node-red workshop

This github repository is meant for learning how to setup and use node-red with IBM services on IBM cloud.

## Node-red overview. 

To avoid later confusions, the image below will give a quick overview on naviagting in node red. take carefull note on the location of the **debug view**, since it will be referenced later.

![node-red-overview](./assets/node-red-overview.png)

## Prerequisites. 

Before we begin, we need to setup some services on IBM cloud, mainly *node-red community*, *Weather services* and *Watson Text To Speech*.

### Setting up node-red-community

#### Setup service.

To setup your service, go to IBM cloud, and click on "create resource" on the top of the page. 

In the search bar on the top of the page, write node-red. Choose the one which says "Community" below the name. ![Node-red Starter](./assets/Node-red Starter.png)

You now have to choose the option which says "Cloudant". This will create a no-sql database along with your instance which will store your configurations and can be used for saving data from nodes. 

![Choose-node-red](./assets/Choose-node-red.png)

Afterwards the service might take a couple of minutes to start up. 

When your node-red instance is ready, click on the link which says "Visit App URL" next to the name. 



#### Configuring your node-red service.

When opening the node-red service for the first time, you will be prompted with a screen, asking you to create a username and password for your service. This is not mandatory, but highly recommended, since if you choose not to, your instance will be available publicly. 

After exiting the setup, you should be presented with a web-page with a large button. Click on the button to go to your node-red flow. 

#### Installing node-red dashboard.

When entering your workflow click on the menu at the top left of the screen, and click on *"Manage palette"*

![secure-node-red](./assets/secure-node-red.png)

a user settings panel should pop up (see above). From here, click on the install tab and search for node-red dashboard and click on the install button.

### Setting up text to speech and Weather services

The node-red service on IBM cloud comes with a variaty of integrations to IBM cloud services. In this tutorial, we have choosen to include Text to Speech and Weather integration, since these have different ways of connecting to node red, they are perfect for a tutorial.

To start of, open a new tab with IBM cloud in your browser and navigate to the "create resource" page like before.

On the panel on the left click on "AI" and choose the service called "Text to speech"![Text-to-speech](./assets/Text-to-speech.png)

Choose the light plan, fill in the name and click "create".

When the instance is created, copy your API-key and URL from the **manage** page of the service. write this down for later.

for weather services, go back to "create resource" and create an instance with "Weather company data" like you did with Text to Speech before. When the instance is created, you need to go into **Service credentials** and click on the button which says "new credential".

From your new credentials, copy the username, password and host and save them for later.

 https://twcservice.au-syd.mybluemix.net/rest-api/#/

**lat**

55.735660

**long**

9.126420

## Setting up our dashboard.

Now that we have created all of the instances that we need, we can start creating components and displaying data from our node-red instance. 

In your browser, go to your node-red service and scroll to the IBM Watson category in the menu to the left.

![empty-dashboard](./assets/empty-dashboard.png)

Above the IBM Watson category you should also see one called **weather** with a node called "weather insights" inside it. Drag it to the "flow" along with the Text to Speech IBM Watson node. ![weather-insights-tts](./assets/weather-insights-tts.png)

we now need to start building our dashboard. Open up a new tab in your browser and go to {your-node-red-url}/ui you should be presented with the following screen: 

![no-ui](./assets/no-ui.png)

What you need to do is go to the button on the menu where you found your Text to speech and weather data nodes. Here you can find a category called **Dashboard**. Choose the button node and place it next to the weather insights node and connect the two nodes.

![button-weather](./assets/button-weather.png)

What happens now is that every time we click the button on the UI, the **weather insights** node will get triggered.

Now, before we can do this, we need to setup our dashboard. Double click on your button node and a menu will pop up.

![button-setup](/Users/jacobhougaardbennedsen/WebstormProjects/node-red-workshop/assets/button-setup.png)

This will bring up a menu from which we can configure the button. The only thing that we have to worry about for now is the tab at the top which says "Group". The Group dictates where and on which sub-page the button is situated in the interface. 

Click on the pencil next to the dropdown and you will be presented with another panel![add-group](./assets/add-group.png)

Pick a name for your group (Home) and click on the pencil next to the Tab dropdown to create a new tab.

![add-tab](./assets/add-tab.png)

From here you can just click add, as the default values are fine for our example. When you return to the previous panel, you can click add again. And then on the last panel, click **Done**.

Now press **deploy** in the top right corner of node-red and go to your UI page. From here you should be able to see the button.

now go back to your node-red dashboard and double click on the **weather insight node** in the flow. Here you can paste in your **username**, **password** and **hostname** from before, under service, choose **current observations** for longitude and latitude use *55.735660,9.126420* which is the location of the legoland hotel in Billun Denmark.

now go to the top of the side menu in node red and drag the **debug** onto your flow and connect it to the other end of your weather insights. 

![debug](./assets/debug.png)

double click on the debug node and choose the complete msg object as output.

![complete-msg-object](./assets/complete-msg-object.png)

Now press **deploy**, go to your UI and press the button.

