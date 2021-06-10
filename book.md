% Airkit Manual

# Airkit Book

Website: airkit-book.com

## ROUGH TOC

* [Introduction](#intro)
* Where to use Airkit
* [Advantages of Airkit over other platforms](#airkitAdvantages)
* [Journeys](#journeys)
* Actors
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

When using an identifier, it is only possible to have one instance of the journey running at one time. This means if someone calls back into an Airkit number, should they resume the experience they were having before?

Outline of journey section

* Journey settings in configuration builder
* Journey analytics
* Journey conflicts
* Journey Keys
* Journey Identifiers

## Builders

### Connection Builder

#### App APIs {#appApi}

## Airscript

### Variable Scopes

#### Session Scope {#sessionScope}


## Airkit API {#airkitApi}