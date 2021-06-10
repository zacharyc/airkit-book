% Airkit Manual

# Airkit Book

Website: airkit-book.com

## ROUGH TOC

* [Introduction](#intro)
* Where to use Airkit
* [Advantages of Airkit over other platforms](#airkitAdvantages)
* [Journeys](#journeys)
* [Actors](#actors)
* The Studio
	* Builders
* The Console
* Deployments
* Resources
* Integrations
* Journey Builder
* App Builder
	* Components
* Connection Builder

## Introduction {#intro}

Airkit is a collection of tools that allow developers to create rich, omni-channel experiences for the last mile of customer interaction. Between the studio and infrastructure, Airkit is a set of tools for anyone who wants to create fantastic customer experiences.

### This Book
This book is designed to be a manual to help one get up and running with Airkit. We will discuss the framework and platform in a somewhat linear fashion building concepts on each other until we have a comprehensive understanding of the platform and Airkit applications. 

Building a book like this requires a ton of help. The Airkit platform is constantly improving as well. This may mean that certain parts of the book may become outdated. Please email zack@airkit.com or support@airkit.com with questions or errata.

###  Who is this book for?
This book is designed for people looking to learn about Airkit. Some sections will be less technical than others but in order to get the more complicated concepts some front end development experience may help. 

Testing an image 

<!-- ![The Console Homepage](images/image1.png) -->

## Where to Use Airkit {#whyUseAirkit}

## Airkit Advantages {#airkitAdvantages}

## Journeys {#journeys}

As Airkit is built around dealing with the last mile of customer experiences, Airkit calls this last mile experience for each customer a "Journey." Each customer who uses your app will go through a journey. Journeys contain stateful information that is persisted across the different channels of web, text, and voice. Journeys even have their own variables and state stored in the session namespace.

To understand this better, let's look at a simple WISMO (Where is my Order) application, like the Digital Self Service example on the Airkit website. In the example, the user calls into a company to track their subscription to a coffee bean company. Each Journey needs to have a unique identifier. When I user starts a Journey with a phone call, the default journey identifier is the phone number of the user.

### Journey Identification

In the example discussed above, the journey was identified by the phone number of the user calling in. Not all journeys start with a phone number. Some journeys are entirely web based. It is possible to set up custom identifiers for a journey, but without any specification, each journey has unique id. This can be found in the [Session Scope](#sessionScope) under the `id` property. The term **session_id** is commonly used to refer to this value. Session Ids are useful when running [App API](@appApi) or trying to send events to particular sessions.

Journeys can also be identified by session keys. Keys can be set on a journey during the time of creation, through the [Airkit API](#airkitApi). These keys can also be used to identify the journey in Analytics as well as certain APIs.

#### Journey Identification Conflicts

When using an identifier, it is only possible to have one instance of the journey running at one time. This means if someone calls back into an Airkit number, should they resume the experience they were having before? The behavior for this is configured in [Configuration Builder](#configurationBuilder). Depending on the settings, if a conflicting Journey arises, the pre-existing journey can be continued, ended and new one started, or the new journey can be rejected.

## Actors {#actors}

Actors are the users of the Airkit Application. Actors have [journeys](#journeys) through an Airkit App. The actor also has unique data structure defined by all applications. It is possible to see the actor object by checking [Data Builder](#dataBuilder). The Default Identity Object, the type of Actor, has the following properties:

* first_name
* last_name
* full_name
* email
* phone
* time_zone

Not all actors will be required to have all of these properties, but if the Application starts a phone call or sends a text message, the current actor must have a phone number set. The actor is top level scoped variable. To set a phone number on the current actor, use the [Set Variable](#setVariableAction) action to set the `actor.phone` to the desired phone number. Because the actor then needs to be refreshed, it is also required to run the [Initialize Actor](#initializeActor) action as well. 

## Builders

### Journey Builder


### Connection Builder

#### App APIs {#appApi}

### Data Builder

### Configuration Builder {#configurationBuilder}

### Acton Builder {#actionBuilder}

#### Defining How Your Controls Interact

Action Builder is unlike other builders in that it exists in the inspector only and does not have a representation in the navigation section on the left side of the window. You can find the Action Builder under the Actions Tab in the inspector when you have an item selected in the Tree in App Builder. Not every component type will have Events. In the example below, Clicked is the Event that has two actions: Run "Create Zendesk Ticket" and Change Card View to "Thank You".

![Action Builder](images/builders/action-builder1.png)

#### Action Picker

Clicking on the plus button the right of an Event or condition will present you with the Action Picker.

![Action Builder](images/builders/action-builder2.png)

The left side of the Action Picker are the Categories of available actions. Select different items on the left to see the different available Actions for each Category. There is a complete list of actions by category at the bottom of this document.

Selecting an action will place at the bottom of the Action Chain.

#### Action Tree

The Action tree is where you can see all the actions for the Events on a control.

![Action Builder](images/builders/action-builder3.png)

The tree can contain individual actions or condition statements. Actions can re-ordered and moved into and out condition statements by grabbing the handle at the left side of the action action. These actions will be run in a top down order, branching based on conditions.

#### Action Editor

Clicking on an Action in the Action Tree will present the action editor.

![Action Builder](images/builders/action-builder4.png)

In the Action Editor you will be able to see all the configurations of the selected Action. Each different type of Action will have different options in its' Action Editor.

#### Available Actions

* Canvas Actions
	* Add Card - Add a New Card to the canvas
	* Update Card - Change the current card view
	* Remove Card - Remove the selected card from the canvas
	* Open Modal - Present another card as a modal
	* Close Modal - Dismiss the presented modal
* App
	* Run Data Operation - Run a single data operation
	* Run Data Operation Repeatedly - Run a data operation for each item in a data set
	* Set Variable - Assign a variable a new value
	* Initialize Actor - Set the actor
	* Set Identifier - Associate a unique identifier with this session
	* Run Event - Run a journey event
* Voice and Chat
	* Start Voice Bot - Start a voice bot with the current actor
	* Start Chat Bot - Start a new Chat Bot conversation with the current actor
* Action Tree
	* Condition - Group and run a set of actions when certain conditions are met
	* Create Timer - Schedule an action chain to run a later time
	* Cancel Timer - Cancel a scheduled timer
	* End Journey - End the current journey
* Reporting
	* Metic: Count - Create a counter
	* Metric: Field - Create a metric field
	* Metric: Statistic - Create a statistical metric
	* Metric: Start Timer - Create a timed metric and start it
	* Metric: Stop Timer - Stop a timer and record the time
	* Log Custom Event - Used to log a custom event with an Airscript expression

## Airscript

### Variable Scopes

#### Session Scope {#sessionScope}


## Airkit API {#airkitApi}