---
title: "What is LLM Context"
layout: default
parent: "What is an LLM"
---
# What Is LLM Context

Large Language Models (LLMs) can generate text similar to how humans do. They use 'context', or the information they have so far, to understand the conversation and produce appropriate responses. However, they can only consider a certain amount of words at a time, so it's important to carefully craft the context to include the exact important words where they're needed most.

## Definition of LLM Context
In Language Language Models (LLMs), 'context' is the surrounding text that the model uses to make sense of what it should say next. It's like a moving window of text that the model uses to figure out word meanings, understand references, and keep the conversation consistent. However, once information is out of this window, the model no longer "remembers" it. So, 'context' is like the model's temporary memory that helps it generate appropriate responses.

## Context Limits
Different models are trained on different amounts of context.  Additionally, the technical limitations of language models mean that some models only support up to a fixed amount of context like 4k or 8k.  Even on models that support larger context, due to cost assoociated with hardware required to support the larger contexts the hosting service for the LLM may set their own limits.  

Finally, just because you have 32k or 128k context (and you're willing to pay the associated costs), doesn't mean that you'll get better results by maxing out the context with lots of information.  For reasons like the "lost-middle phenomenon" (which resembles human primacy/recency) and also other limitations, LLMs struggle to retrieve information in larger contexts.  

Generally, when it comes to context, [less is typically more](/docs/tips-tricks-and-troubleshooting/less-is-more)

## Context and AI Chat Bots 

When you talk with the language model, your "[prompt template](/docs/chat-settings/prompt-templates)" is parsed and the placeholders are filled in to make the context that is sent to the LLM.

Important considerations:

* System Prompt
* Character Card (including name, greeting, scenario, persona, example chats, character system prompt, character post-history, and author's note)
* Embeddings (including chat embeds, user embeds, and memories)
* Events and state
* Chat History 
* "Jail Break" or UJB
* And of course your most recent message

Carefully controlling all of the above allows you to craft your bot's perception and understanding of the world, as well as its understanding of its own role in the world as well.

## Primacy and Recency, and Context Limits

It's useful to know that the most-recent message tends to matter most to chat-based models.  While this can vary from model-to-model, most chat-based language models tend to pay more attention to data closer to the bottom of the context window.  This is likely because that's where the message they're directly responding to is located.  It also means that tricks like [author's notes](/docs/creating-a-character/authors-note) and [jail breaks](/docs/chat-settings/system-prompt-and-jail-breaks#jail-breaks) can have a very powerful impact on the type of responses your character provides.

It can also be useful to note that the initial messages also tend to matter more than the text in the middle.  It's useful to "set the stage" early on with a scenario and some basic facts about your character before filling the chat with additional context.  This will help set the tone for the rest of your conversation.

The default ordering of the prompt template takes this into consideration.  However, you may find it useful to experiment with [advanced prompts](/docs/chat-settings/prompt-templates#advanced-prompting) or simply re-ordering the elements of the basic prompt templates taking the above into consideration.

## Conclusion 
In summary, "context" plays a vital role in the functioning of language models, serving as the essential previous text that models use to form their subsequent responses.  It is often constrained due to technical limitations. Carefully curating your context is an important part of taming your chatbot.
