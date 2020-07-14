# AlexaHackathonSkill

### How to run the skill:
##### Creating it (Modified from [Amazon's github steps](https://github.com/alexa/skill-sample-nodejs-howto/blob/master/instructions/setup-vui-alexa-hosted.md))
1.  **Go to the [Amazon Developer Portal](http://developer.amazon.com?&sc_category=Owned&sc_channel=RD&sc_campaign=Evangelism2018&sc_publisher=github&sc_content=Survey&sc_detail=howto-nodejs-V2_GUI-1&sc_funnel=Convert&sc_country=WW&sc_medium=Owned_RD_Evangelism2018_github_Survey_howto-nodejs-V2_GUI-1_Convert_WW_beginnersdevs&sc_segment=beginnersdevs).  In the top-right corner of the screen, click the "Sign In" button.**
 * This is different from AWS, it's a normal amazon account you're signing in with (like the one you use on retail site). didn't even bother using my @amazon.com email just used my personal acc lol
(If you don't already have an account, you will be able to create a new one for free.)
2.  Once you have signed in, move your mouse over the **Your Alexa Consoles** text at the top of the screen and Select the **Skills (New)** Link.
3.  From the **Alexa Skills Console (New Console)** select the **Create Skill** button near the top of the screen.
4. Give your new skill a **Name**. It can literally be whatever, because the internal name you will call it by in Alexa is in the code
5. Keep the default **Custom** model selected, and scroll the page down. 
6. Choose **Alexa-Hosted (Node.js)** for the method to host your skill's backend resources.  Scroll backup and select the **Create Skill** button at the top right.
7. Just pick the "Hello World" template, doesn't really matter. Press "continue with template"
It will take a minute to create your Alexa hosted skill, then you will be taken to the Build tab of the console.

##### Importing the code from this github
1. Under the Build tab at the top go to **Interaction Model** -> **JSON Editor** and copy and paste the model.json file's contents into the window. "Save" the model then press "Build Model"
2. Under the code tab, replace index.js and package.json with the corresponding files in the GitHub. 
3. Add the file onboardingevents.js into the files by pressing "Create File" and just copying and pasting the contents
4. Press save and then deploy
 
##### Testing
Once the model has been created and the code has been deployed, you can select "Development" from the "Skill testing is enabled in" dropdown menu, and proceed to chat with Alexa

Note: Current name of skill is "hackathon skill" so you should start it with "start hackathon skill" or like "alexa ask hackathon skill ____"

### Basic Code Structure
* model.json - for processing language 
    * "Intents" - basically every type of action is an intent. So opening the skill and stopping the skill are Amazon pre built intents, but I added 
    * "Slots" - the modifiable part of an intent, so when you ask something like "whats the weather <in Chicago>," in Chicago would be the slot's value
    * You can modify these intents in the UI and it'll auto update the JSON, or you can modify the JSON directly

* index.js
    * Has the processing code, most of the code was generated in alexa.design/codegenerator (takes in your JSON of intents and created boilerplate code, really nice site)
        * Remember if you use this to add the changes in the index.js, like the deleting the import for http and const onboardingEvents = require('./onboardingevents.js');
    * If you need new dependecies for making HTTP requests or something, just add them to package.json

#### Basic code editing stucture:
* Create a new intent, add appropriate sample statements to train the model
* Create appropriate handles in index.js
* Print statements are on cloudwatch, and to go to them go to Code -> bottom left corner has a link
