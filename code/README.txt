We need RaspberryPi and GrovePi, Camera, Buzzer, Vibration Motor and LED. 
Connect Buzzer to 
		Vibration Motor to
		LED to
Camera is placed facing driver's face and it should take pictures when the take pic is clicked on from dashboard.(See images in project report for more clarity). 

Import attached Node-Red flow to your node-red editor. Few modules have to be installed for the flow to work :
Node-Red modules to be installed
node-red-grovepi-nodes
Node-red-contrib-moment
Node-red-node-Watson 
Node-red-node-sqlite
Node-red-node-cf-cloudant 
Node-red-dashboard 
Node-red-contrib-camerapi
After installing all the modules deploy it. Change Watson Visual Recognition API Key and classifier_id if required.
 Classifier Id in "set custom model" node and API key in "Analyze Image" node.
	API Key : il4pkH15SVAorLk-Ntgd8AbafZiUdZ4gcCG65g8H8Q49
	Classifier Id : DefaultCustomModel_105856722
	
Install SQLite DB on local machine, execute below commands to create tables and insert data into the DB. 

	SQLITE3 IoTproject;
	CREATE TABLE driveSafe( sixam_twelvepm INT,twelvepm_sixpm INT, sixpm_twelveam INT,twelveam_sixam INT);

	
Create IBM Internet Of Things Project and get API key and auth token. 
Register devices with IBM. 
In the node-red flow, change api key and security credentials in all MQTT nodes.. 
Create Dashboard and add Value chart to display if the driver is awake or asleep, LED, Buzzer and wrist band are ON. 
Local dashboard displays user's image
For value chart, use EventAnalyze event for value chart. Now deploy the flow and open the dashboard (both node-red and IBM cloud) in a new window. 

Now test the prototype with a sleeping driver image and an asleep driver image and observe.
When the camera takes a pic of an asleep driver, it turns on the LED,Buzzer and Vibration motor. The values are displayed in dashboard in cloud. The driver's picture is displayed in the local dashboard.
No action takes place when the camera takes a picture of an awake driver. 
