---
title: "Off Topic Responses"
layout: default
parent: "Tips, Tricks, and Troubleshooting"
---

# Off-topic, Out-of-character Response

If your bot is ignoring your chat mesasges and saying whatever they want, or your generally getting responses that don't make sense in the given context or don't fit the character you've created for your bot, there's several things to consider.

Also, if your just getting random nonsense that doesn't even look like words, you're suffering a similar problem.

Ultimately, you're up against one of two things -- context length and token probability (as is usually the case with LLMs).

Agnaistic chatbots are powered by large language models (LLMs) and can converse on a wide variety of topics. However, these models can sometimes produce off-topic responses, including deviating from character personality traits or even completely ignoring the current conversation.  Below are some reasons why this may happen.

## Impact of Temperature

'Temperature' is a critical parameter in chatbot response generation. Raising temperature increases the probability of less-probable tokens, and lowering temperature will decrease that probability.  

Token probability, the likelihood assigned by the model for each potential output, plays a critical role in determining the chatbot's responses. Off-topic responses can occur if the model assigns a higher probability to irrelevant tokens.  This becomes more relevant as you try to battle repetition with features like repetition penalties, top k, mirostat, temperature, and similar probability-altering settings.

A high temperature value incites diverse and potentially off-topic responses, but a low value guides the chatbot towards more on-topic replies.  A proper balance between temperature and other advanced parameters, depending on the issue you're trying to solve, can result in better response generations.

If you're getting a lot of random nonsense and crazy symbols, try lowering your temperature.  Likewise, if you're certain that you're not running into context issues, a lower temperature can help keep your character "on-script".  Note that while temperature is a useful tool to increase (or decrease) the probability of less-probable tokens, it's best used in combination with other settings like min-p, top-k, TFS, Mirostat, and repetition penalty.

See [advanced settings](/docs/chat-settings/advanced-settings) for more information.


## Influence of Context and Max Context Length

Chatbot responses are significantly influenced by their preceding context. However, due to the limitation known as 'max context length', chatbots can only consider a certain number of tokens as context (see [context and context limits](/docs/what-is-an-llm/context-and-context-limits)). Once this limit is hit, vital information is potentially discarded.  Exaples of context limit issues include when your character card is over 1000 tokens, your memory token counts are high and your memory book is quite large, your chat embeddings or user embeddings are high, your max new response tokens are high, or similar.  The result will be that your chat history is trimmed to the point of non-existance and thus your bot is no longer receiving your latest messages.

Context is calculated as follows:

Context available for recent chat history = (Max Context Length) - (Max New Tokens) - (Character Card Tokens) - (Tokens used for memory embeds) - (tokens used for chat embeds) - (tokens used for user embeds)

Assuming you are on a free model with max new tokens at 500, character card tokens at 1000, memory embeds at 500, and chat embeds at 500 with user embeds disabled, then you will have 4000 - 500 - 1000 - 500 - 500 - 0, or 1500 tokens available for chat history.  If you instead have 1000 max new tokens, 2000 tokens for character card, and 1000 tokens for memory embeds, you will then have 0 tokens available for recent conversation history and the bot will go off topic.

## Chatbot Intelligence and 'Lost Middle' Phenomenon

Despite the complexity and intelligence of chatbots, extended interactions can lead to a phenomenon known as the 'Lost Middle', where the bot gives more weight to elements at the start and the end of the context and less relevance to content in the middle.  Using prompt template ordering or advanced prompt templates will allow you to position information to leverage the primacy and recency effects.  Alternatively, just be aware of this and leverage the system prompt and UJB or Author's Note which are at the top and bottom of the prompt respectively.  You can also lower your max context length and work with a smaller context if this becomes an issue.

## Conclusion

Maintaining on-topic conversations with a chatbot is a balancing act of managing context and getting the right settings.  If you have additional questions, catch us on discord and ask away :)