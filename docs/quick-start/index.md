---
layout: default
title: "Quick Start"
has_children: False
nav_order: 1
---
# Quick Start

<iframe width="560" height="315" src="https://www.youtube.com/embed/JgT2jLMSOP0?si=W0U0PDqhfUT62lHa" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

Done with the video?  Skip ahead to [some more things to try](#some-next-things-to-try).

## Step-by-Step

1. Load up the Agnai interface
    * go to the website https://agnai.chat
    * Optionally, login / create an account (if you want your chats to persist across devices or you want to sign up for higher context / more powerful LLMs)
1. Have your first chat with a Robot
    * Talk to the robot by clicking on the "Robot" chat right on the homepage
    * Use the "Send a message" box at the bottom of the screen to chat, just like with any messaging platform
    * Wait a few moments for the robot to respond
    * By default, your chats will use the Agnai model.  See "**[Configuring your AI service](/docs/configuring-ai-service)**" for information on choosing and configuring the various AI services.
    * For more advanced information about chatting, controls, and settings, see "**[Chat Settings](/docs/chat-settings)**".
1. Create your own character
    * Click the "+" by "Character" for quick access to character creation
    * Give your character a name.  The character's name will influence the conversation.
    * Optionally add a description and some tags, a scenario, some persona information, and an example chat or two
    * Optionally upload an image for your character, or provide a description of the character's appearance and generate an image.  By default, image generation uses the Kobold Horde (and takes a long time).
    * Scroll down and click "Create" in the bottom right corner
    * For more information about character creation, see "**[Creating a character](/docs/creating-a-character)**".
1. Create a chat
    * On the top right of the page after you create a character is a "New" button
        * You can also click the "+" by "Chats"
    * Select your character from the dropdown list
    * Give the conversation a name
    * Scroll down and click "create"
    * Ignore the "override character definition" and "Scenario" controls for now
    * For more about advanced chat settings, see "**[Chat Settings](/docs/chat-settings)**" and "**[Scenarios](/docs/library/scenarios)**"
1. Create a memory
    * Go to the "Gear" in the top right of the page after you create a chat
    * Select "Memory"
    * With "None" selected, click "Create a new memory book"
    * Scroll down and give the book a name and optionally a description
    * Click "+ Entry" to create a new entry in the memory book
    * Give the entry a name
    * List out a series of phrases that should trigger the memory.  These could be one work, multiple words, or pattern-matching like "dino*"
    * Leave Priority and Weight at 0 for now (see "**[Memory Priority and Weight](/docs/memory/priority-and-weight)**")
    * Add the details of the memory to the box.  Keep your memory entry relatively short.  For longer memories, consider using "**[User Embeds](/docs/memory/user-embeds)**"
    * Some memories are automatically remembered from your chat history over longer conversations.  See "**[Chat Embeds](/docs/memory/chat-embeds)**"
    * see the "**[Memory](/docs/memory)**" subsection for more information
1. Change the character's behavior with a "jailbreak"
    * A "Jailbreak", aka User Jailbreak, Ultimate Jailbreak or UJB, is a powerful instruction for the bot
    * In the default prompt template (see "**[Prompt Templates](/docs/chat-settings/prompt-templates)**"), the UJB is one of the last pieces of context
    * The lower down in context something is, the more impact it has on the resposne
    * Try setting a "UJB" to make the character behave the opposite of their current behavior (see "**[System Prompt and Jail Breaks](/docs/chat-settings/system-prompt-and-jail-breaks)**")
    * See "**[Chat Settings](/docs/chat-settings)**" for other ideas, including "**[Advanced Settings](/docs/chat-settings/advanced-settings)**"

## Some next things to try
* Learn about [prompt templates](/docs/chat-settings/prompt-templates)
* Learn about [user embeds or chat embeds](/docs/memory/embeddings)
* Learn about [advanced settings for controlling the LLM](/docs/chat-settings/advanced-settings)
* Learn more about [context limits](/docs/what-is-an-llm/context-and-context-limits)
* Try [multi-bot conversations](/docs/tips-tricks-and-troubleshooting/multi-bot-conversations) or learn about [narrator bots](/docs/tips-tricks-and-troubleshooting/narrator-bots)
* Try [inviting a friend](/docs/tips-tricks-and-troubleshooting/multi-user-conversations-and-invites) to a conversation with your bot
* Learn about the [Library](/docs/library), [Scenarios](/docs/library/scenarios), and [Events](/docs/library/events)


