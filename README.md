# cucumber
This projects contains a Maven project w/cucumber which covers Cucumber essential features

The summary of this project can be found below:
First we need to create the feature file that will contain our Scenarios.
	This file should be written using Gherkin syntax language that Cucumber understands.
	Normally it may include the following suggestions:
		#Given: Some precondition step
		#When: Some key actions
	 	#Then: To observe outcomes or validation
	 	#And,But: To enumerate more Given,When,Then steps
	 	#Scenario Outline: List of steps for data-driven as an Examples and <placeholder>
	 	#Examples: Container for s table
	 	#Background: List of steps run before each of the scenarios
	 	#""" (Doc Strings)
	 	#| (Data Tables)
		#@ (Tags/Labels):To group Scenarios 
	 	#<> (placeholder)
	 	#”"
	 	## (Comments)
	Several scenarios can be included within the same feature file.
	When some word is parameterised we should mark it w/quotes to know the condition can be reused.
The 2nd step is create a Step file in JAVA mapping the Scenarios written in feature file.
We can use Regular Expression:
To match the content within the annotation (@Given, @When, @Then, @And)
To avoid writing (reusing) the same conditions several times.
Use ^ and $ to reflect the beginning and end of a sentence.
The condition can be parametirized using () to indicate Cucumber that it’s something will be passed as a parameter within the method.
Parametrisation can be done in 2 ways:
Creating different scenarios within feature file and using () in @Given, @When, etc annotation.
Declaring examples within feature file and then using () in the annotation - Don’t forget to mark your variables using <> tags.
You can run the same scenario using different examples.
The scenario has to be modified using Scenario Outline
If a word has been marked w/quotes in the feature file, it has to be marked as well within the annotation condition.
Tags is a great way to organise your features and scenarios. A scenario or feature can have as many tags as you like, separate them by spaces. Tags are declared within feature file and Test clase inside @CucumberOptions.
Any tag that exists on a Feature will be inherited by Scenario, Scenario Outline or Examples.
Background feature gives the possibility to execute something before any scenario is being executed.
However, it has a limitation that is going to be executed only for that particular Scenario file.
Cucumber has a better integration w/JUnit rather TestNG.
Hooks is a very interesting feature:
It has a global access like @Before and @After that will be executed for all the feature files.
You can link the above methods to an specific @tag to execute them only for a specific scenario.
The methods will be executed in order of appearance.
