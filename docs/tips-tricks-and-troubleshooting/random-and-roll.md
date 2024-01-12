---
title: "Random and Roll"
layout: default
parent: "Tips, Tricks, and Troubleshooting"
---

# Random and Roll

When working with prompt templates, UJBs, system prompts, and memories, one technique that can provide some interesting results is inducing additional randomness.

Two ways that you can introduce randomness into your prompt is through placeholder tags called {{random}} and {{roll}}:

## Random 

> **{% raw %}{{random choice a, choice b, choice c}}{% endraw %}**

Using this placeholder tag, you can have your prompt randomly include one of the choices.  This is best understood with an example:

If you have a prompt template that looks like the following:

> {% raw %} The sailor {{random went out to sea, went fishing, went to the bar, cussed}}. {% endraw %}

Then during prompt generation, your context will end up looking like:

> The sailor went out to sea.

On another message, you might get:

> The sailor went to the bar.

As you can see from the examples, a random selection from the list of comma-separated values is made and inserted into the context during generation.

## Roll

> **{% raw %}{{roll 20}}{% endraw %}** _here we roll a 20-sided dice, but you could roll dice with any number of sides_

Roll is simpler than random, and its effects are both less predicatable and potentially more interesting.  If we were to roll 10, like so:

>{% raw %}Luck is {{roll 10}}{% endraw %}**

What our context ends up looking like is:

> Luck is 4

Where 4 could be 1, 2, 10, 8, etc.  10 is the highest number.  This can then be used with instructions to the LLM, potentially in the character card or in the jailbreak or prompt template.

Something like:

> If luck is less than 4, whatever {% raw %}{{char}}{% endraw %} is currently doing fails dramatically.
> If luck is greater than 8, {% raw %}{{char}}{% endraw %} spontaneously does something magical. 
> {% raw %}Luck is {{roll 10}}{% endraw %}**

Depending on the LLM, the above may have some fairly interesting and unpredicatable results on the response.
