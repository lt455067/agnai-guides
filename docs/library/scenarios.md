---
title: "Scenarios"
layout: default
nav_order: 5
has_parent: true
parent: "Library"
---
# Scenarios

There are two kinds of things people think about when it comes to the word "scenarios" in Agnai. One is the "scenario" section in the character card, and one is the "scenario" tab inside of the Library tab in the left-hand menu. This article is about the latter, go to the Character Card section for information about the former. To make use of a scenario you created, simply select it from the dropdown when creating a new chat.

The first thing you will notice on the Scenario page is, apart from the title and description, the "prompt text" field. This option lets you either override the scenario in your character card (if you select the appropriate toggle) or add to it, making it easy to pick the scenario text you want for this particular chat without needing to change the character card.
You can also leave additional instructions in the "user instructions" field. These will appear at the start of the chat.

Now let's move on to the main reason you'd want to use scenarios: events.

Firstly, you need to pick a **trigger**, which is how your event will start. There are four types of triggers:

**Greeting** - the event will only activate once, at the beginning of the chat. This is useful if you want to have a greeting which you can re-use for multiple characters, or, with the "hidden" event type, give instructions to generate a greeting in a certain manner (which can be more interesting than just reusing pre-written greetings).

**Manual Trigger** - the event will be activated once the "Trigger Event" button is pressed in chat. If there are multiple options available, one will be picked at random.

**Chat Opened** - the event will trigger once the chat is opened. This can be used to have the character greet you after you return to a previous chat, simulating more human-like interaction.

**Message Received** - the event will trigger once you send a message. This will result in double replies in a normal one-on-one character chat.

Except for the Greeting trigger, you can also use **event flags**. They are essentially conditions which need to be met in order for the event to be available to activate.
There are two fields for flags, **Required States** and **States to Assign**. Both serve different purposes, Required States being to add conditions for the event to activate, and States to Assign being to add flags which this event adds/removes.
You can add a flag by simply typing any kind of name in the States to Assign field (for instance, "event"), and pressing Enter to validate your selection (same functionality as with tags in the character card). You can also remove a flag by typing its name with a ! preceding it, (for instance "!event"). Once you have assigned a flag to an event, you can also use the state name in other events in the States to Assign field. Following our example, typing "event" here will mean that this event requires the "event" flag to be activated to trigger, and "!event" will mean that it requires the flag **not** to be activated. There is also a field to override event flags inside a chat, if you wish to change their status manually.
Flags are powerful building blocks. With them, you can, for instance, design a progressive chain of events by having event1 require event2 require event3... and so on, which normally is harder to do, since the character card is constant, unless you edit it along the way.

You also need to select the **type** and **prompt** of your event. The prompt is just a text field, and the type is how this text field is inserted into the chat. There are four event types:

**Hidden** - This sends the event prompt to the AI behind the scenes, effectively meaning that it is sent as an invisible message, which the AI character will then reply to. This is very useful if you do not want to have a pre-written reply (as the other options do it), but instead instruct the AI to generate the reply in a certain way.

**World** - shows the event prompt as an event independent of the characters.

**Character** - shows the event prompt as if spoken by the AI character.

**Out Of Character** - only visible by you. Essentially a tooltip.

That concludes the overview of the functionalities of scenarios. Hopefully this page helped you.

