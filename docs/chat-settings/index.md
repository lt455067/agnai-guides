---
title: "Chat Settings"
layout: default
nav_order: 4
---
# Chat Settings

In a chat, if you go to the "⚙️" in the top right corner, you can see the settings fly-out.

![agnai-chat-settings-flyout.png](..%2F..%2Fassets%2Fimages%2Fagnai-chat-settings-flyout.png)

Clicking on "Preset" will bring you to the chat settings window:

![agnai-preset-settings.png](..%2F..%2Fassets%2Fimages%2Fagnai-preset-settings.png)

## Preset Creation and Selection

From the top down, what you'll see is that the "Selected" preset defaults to Agnaistic built-in.

To create a new preset, you can change any setting and a new preset will automatically be created when you save.  

Start by giving the preset a name at the top under "Preset Name".

## AI Service Selection

Agnaistic is designed to work with several different AI services.  If you have a service configured in your [global AI settings](https://agnai.chat/settings) then it will be available for selection in this dropdown.

By default, only Agnaistic, Horde, and third-party / textgen options are available.

### Model Selection

Some AI services, like Agnaistic's built-in service, allow you to select different models.  

Changing the model can have a dramatic affect on the LLM's outputs.  You can read more in ["choosing a language model"](/docs/what-is-an-llm/choosing-a-language-model).

## Tabs
The rest of the preset is divided among a number of tabs.

* [General Tab](#general-tab)
* [Prompt Tab](#prompt-tab)
* [Memory Tab](#memory-tab)
* [Advanced Tab](#advanced-tab)

## General Tab
The general settings vary slightly based on which AI service you're using.  For this guide, we will focus on the Agnaistic settings.  If you want an explanation of other settings, reach out on [Discord](https://agnai.chat/discord).

![agnai-preset-general-tab.png](..%2F..%2Fassets%2Fimages%2Fagnai-preset-general-tab.png)

### General settings

#### Max New Tokens
The amount of tokens in your context to reserve for the model's response.  

Some considerations:
* Model generations will be halted after this number of tokens are generated.  
* Setting this higher reduces the amount of context available for chat history, memory, etc.
* Higher max new tokens will also take longer to generate.  

For additional information, see ["Context and Context Limits"](/docs/what-is-an-llm/context-and-context-limits)

## Prompt Tab
Explanation on how to use the Prompt tab.
### Prompt settings
* Prompt definition and options
* Other settings (to be specified depending on the contents of this tab)

## Memory Tab
Description of the Memory tab and its features.
### Memory settings
* Memory management options for AI
* Other settings (to be specified depending on the contents of this tab)

## Advanced Tab
Explanation of the Advanced tab.
### Advanced settings
* Particular settings (to be specified depending on the contents of this tab)

## Saving Changes
Step-by-step instruction on how to save changes made in the GenerationSettings.

## Additional Features
Additional features (if any) present on the GenerationSettings page.

## Troubleshooting
Common issues that might be faced by users while using the GenerationSettings page, alongside possible solutions.
