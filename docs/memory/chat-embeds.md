---
title: "User Embeds and Chat Embeds"
layout: default
nav_order: 6
has_parent: true
parent: "Memory"
---
# User Embeds and Chat Embeds

> Note: this is only a brief overview of how to use chat embeds and user embeds in Agnai.  For a more in-depth overview of how embeddings work with LLMs in general, check out https://pub.aimind.so/llm-embeddings-explained-simply-f7536d3d0e4b?gi=537c9fd225d8


User embeds and chat embeds are both a form of retrieval augmented generation (RAG) and form a sort of "dynamic memory".  Similar to the memory books, User Embeds and Chat Embeds will use keywords and context from the chat history to include relevant pieces of information.

Like memories, embeds are a way to dynamically include relevant information without cluttering up your character card, system prompt, etc.

## User Embeds

User embeds are accessible from the Library and also from the Chat Settings -> Memory panel.  You can embed a website or a file in several supported formats.  When you embed a document like a website or a file, the system will parse the document and split it into chunks based on line separation.  Each line of the document will become a separate embedding.  This means that if you're making a custom lorebook in a text file, including each relevant piece of information on its own line is recommended.  Word-wrapping is not a factor, only line-breaks from hitting "enter" will separate out the embeddings.

For user embeds, it's likely that you may need to adjust your prompt template.  The default prompt template does not include the necessary {% raw %}{{user_embed}}{% endraw %} placeholder.

For example, you may want to have a prompt template that looks like the following using a validated preset prompt:

```
{% raw %}
{{#if system_prompt}}{{system_prompt}}
{{/if}}
Below is an instruction that describes a task. Write a response that completes the request.

Write {{char}}'s next reply in a fictional roleplay chat between {{#each bot}}{{.name}}, {{/each}}{{char}} and {{user}}.

{{char}}'s Persona:
{{personality}}
{{/if}}

{{#if user_embed}}Relevant information to the conversation
{{user_embed}}
{{/if}}

{{#if memory}}These are relevant memories:
{{memory}}
{{/if}}

{{#if scenario}}The scenario of the conversation: {{scenario}}
{{/if}}

{{#if chat_embed}}Relevant past conversation history
{{chat_embed}}
{{/if}}

{{#if example_dialogue}}This is how {{char}} should talk: {{example_dialogue}}
{{/if}}
***

{{#each msg}}{{#if .isbot}}### Response:
{{.name}}: {{.msg}}{{/if}}{{#if .isuser}}### Instruction:
{{.name}}: {{.msg}}{{/if}}
{{/each}}

{{#if ujb}}### Instruction:
The following is a very important instruction which must be followed:
{{ujb}}
{{/if}}

### Response:
{{post}}
{% endraw %}
```

Note that this is an example prompt template and while this will work okay with Alpaca formatted models like the current 7b and 13b models, the 70b model is a Vicuna formatted model and you will need to adjust the prompt template above accordingly.  Several ways exist to do this and you can either check the docs on prompt templates or you can ask in the discord server.

## Chat Embeds

Chat Embeds come from your chat history rather than coming from a file that you control.  When you load a chat, the messages that are loaded into your browser are likewise added to the embeddings engine.  If you scroll up to load in past messages, these past messages will also be embedded as they load in. 

As you continue the conversation, your new messages will trigger relevant chat embeddings to be added to your prompt.  Based on what you're talking about, previous messages that would otherwise not fit into your chat history context are loaded into your context at the {% raw %}{{chat_embed}}{% endraw %} placeholder.  Once your chat embed context limit is reached, chat embeds are no longer included.

Chat embeds are loaded into an in-memory database locally.  The chat embeds most relevant to the conversation are retrieved from this database "magically" and inserted.  If the chat message is not loaded into the browser window (i.e it's not in the initial message load) you can either scroll up to load more chat messages or otherwise it won't be in your local embeddings database for that chat session.

