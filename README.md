# Quickly Build A Multi Modal Quiz & Dictionary Alexa Skill

# Adding screens to your voice experience

This Alexa sample skill demonstrates the use of interactive render template directives through multi modal screen design, **now in the V2 SDK**. It provides an infrastructure that on one hand, provides lists to users to allow them to select from and get more information about topics (which are then rendered via body & list templates). On the other hand, it also provides users with a quiz that supports both touch and voice control. **Most importantly, the skill has been designed in such a way that you can modify the core skill data to any category you like!**

If this is your first time here, you're new to Alexa Skills Development, or you're looking for more detailed instructions, click the **Get Started** button below:


If you're slightly more advanced or familiar with SMAPI (Skill Management API), jump to the **Setup w/ ASK CLI** section below.


Be sure to take a look at the [Additional Resources](#additional-resources) at the bottom of this page!


## About
**Note:** The rest of this readme assumes you have your developer environment ready to go and that you have some familiarity with CLI (Command Line Interface) Tools, [AWS](https://aws.amazon.com/), and the [ASK Developer Portal](https://developer.amazon.com/alexa-skills-kit). If not, [click here](./instructions/0-intro.md) for a more detailed walkthrough.



### Usage

```text
Alexa, open Berry Bash.
	>> Welcome to Berry Bash..

Alexa, ask Berry Bash to tell me about raspberries
```

### Repository Contents
* `/.ask`	- [ASK CLI (Command Line Interface) Configuration](https://developer.amazon.com/docs/smapi/ask-cli-intro.html)	 
* `/lambda/custom` - Back-End Logic for the Alexa Skill hosted on [AWS Lambda](https://aws.amazon.com/lambda/)
* `/models` - Voice User Interface and Language Specific Interaction Models
* `/instructions` - Step-by-Step Instructions for Getting Started
* `skill.json`	- [Skill Manifest](https://developer.amazon.com/docs/smapi/skill-manifest.html)

## Setup w/ ASK CLI

### Pre-requisites

* Node.js (> v4.3)
* Register for an [AWS Account](https://aws.amazon.com/)
* Register for an [Amazon Developer Account](https://developer.amazon.com/)
* Install and Setup [ASK CLI](https://developer.amazon.com/docs/smapi/quick-start-alexa-skills-kit-command-line-interface.html)

### Installation
1. Clone the repository

	```bash
	$ git clone https://github.com/harsh4870/Berry-bash.git
	```

2. Initiatialize the [ASK CLI](https://developer.amazon.com/docs/smapi/quick-start-alexa-skills-kit-command-line-interface.html) by Navigating into the repository and running npm command: `ask init`. Follow the prompts.

	```bash
	$ go inside folder
	$ ask init
	```

3. Install npm dependencies by navigating into the `/lambda/custom` directory and running the npm command: `npm install`

	```bash
	$ cd lambda/custom
	$ npm install
	```


### Deployment

ASK CLI will create the skill and the lambda function for you. The Lambda function will be created in ```us-east-1 (Northern Virginia)``` by default.

1. Deploy the skill and the lambda function in one step by running the following command (from the folder root):

	```bash
	$ ask deploy
	```

### Testing

1. To test, you need to login to Alexa Developer Console, and enable the "Test" switch on your skill from the "Test" Tab.

2. Simulate verbal interaction with your skill through the command line using the following example:

	```bash
	 $ ask simulate -l en-US -t "open berry bash"

	 ✓ Simulation created for simulation id: ***
	◡ Waiting for simulation response{
	  "status": "SUCCESSFUL",
	  ...
	 ```

3. Once the "Test" switch is enabled, your skill can be tested on devices associated with the developer account as well. Speak to Alexa from any enabled device, from your browser at [echosim.io](https://echosim.io/welcome), or through your Amazon Mobile App and say:

	```text
	Alexa, open berry bash
	```



## Customization

1. ```./skill.json```

   Change the skill name, example phrase, icons, testing instructions etc ...

   See the Skill [Manifest Documentation](https://developer.amazon.com/docs/smapi/skill-manifest.html) for more information.

2. ```./lambda/custom/index.js```

   Modify messages, and facts from the source code to customize the skill. Check out the [Customise](./5-publication.md) section for more info.

3. ```./models/*.json```

	Change the model defintion to replace the invocation name and the sample phrase for each intent.  Repeat the operation for [each locale](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/developing-skills-in-multiple-languages) you are planning to support.

