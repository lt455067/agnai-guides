---
title: "Creating a character"
layout: default
nav_order: 3
---
# Creating a character

Creating your first might seem daunting, but worry not - this is a guide accessible for complete beginners, and will cover all parts of the character creation process on Agnai, and every field in the character card. After going through it, you should have a basic idea of how character creation works, and learn enough about the process to feel comfortable enough to start.

All fields are optional. There isn't any "magic" going behind the scenes to make the character work, it's just a single prompt sent to the AI with all the details of the character, with the instruction to write the next reply in a chat as this character (think of all language models as assistants similar to ChatGPT under the hood), so keep in mind that you can customize your character card to your liking, and use whichever fields you prefer. For starters, you can just create a character with only the "name" and "personality" fields filled out (just provide a short description of the character in the "personality" field in plain text, no special format needed), and that should work just fine. For additional information about what each of the fields is used for and some helpful insights related to character creation, you can check this page.

## Fields:

### Basic:

**Character Name**: Pretty self-explanatory. The main name that this character will be referred to throughout the chat. Equivalent to the {{char}} placeholder if the character is the main character (i.e. the character you first select when creating a chat).

**Description / Creator's Notes**: This field serves two purposes. If you intend to AI generate a character, simply input the information about them here, select your service, and press "generate". To only generate a specific field, you can use the "regenerate" button next to the respective field. Otherwise, this field is intended as a short description, purely cosmetic. It shows up in your character list under the name, so you and anyone importing it can always see it easily.

**Tags**: for easy sorting, searching, filtering. Simply input a tag name and press "enter" to add it.

**Avatar/Sprite**: Lets you upload a file for your character to use as the profile picture (avatar). Must be under 8mb size. Alternatively, you can use "sprite", which has a built-in 2d character creator.

**Appearance Prompt**: If you want to generate an AI image for the avatar using the "generate image" button, use this field to input data for it. It is only for that, and not a field which the AI will read from during chats, you'll want to put that in "personality" instead. Alternatively, if you use the Attributes format for your "personality" field, you can name an attribute "looks" or "appearance" and it will be used to generate the image.

**Scenario**: Used to describe the circumstances between you and the character (and others, if you are using group chats). You can override that field or add to it by making [custom scenarios](https://agnai.guide/docs/library/scenarios) in the Library tab, and selecting the scenario in the "Advanced" tab of the character card, so that you can change the scenarios of the conversation without modifying the card. As all fields, it is optional, don't be afraid to skip it if you can't think of a use for it.

**Greeting**: Here, you can design custom first messages which your character can use (add more with the "Add Alternate Greeting" button). If you write multiple of them, you can switch between them manually. Greetings are useful because of the way language models work - they mimic what they see. This is why if you want a specific style of response (for instance, long responses in third person, with speech in quotes and actions in asterisks), greetings and the "sample conversation" field can be effective - you're *showing* the AI how to respond, not *telling* it. But as usual, there is no right/wrong way to do it. You can omit the greeting entirely, supplement it with instructions, or even write your entire character inside the greeting.

An advantage of using greetings is also that they do not take up permanent tokens, so they will not be sent to the AI every single reply. Instead, greetings are treated just as any other message would, so if you have filled up your context limit, the greeting will disappear (be "forgotten") just as an older message would. Reducing your permanent token count helps with response times, lowers costs with pay-per-token services and saves more context space for other things such as history and memory books.

**Persona Schema**: It's the format for your "personality" section, where you typically want all the important information about your character. You can use "plain text", which is just text, or "attributes", which is a more organized format, where you have attribute names of your choosing (e.g. "personality", "appearance"...) and their descriptions (e.g. "Sweet older lady, loves to spoil her grandchildren", "gray hair, wrinkles, blue eyes"). There is not much difference between the two - under the hood, "attributes" is equivalent to having "attribute: description, attribute2: description2..." in "plain text". Nevertheless, attributes can help in keeping your personality more organized and neat-looking, and might make it easier to shorten your token count by using comma-separated attributes. That doesn't mean lessening the token count is always what you want, though, being more verbose can convey more information, and sometimes it can be preferable. It is generally good to avoid bloated descriptions (save that for the actual chat, or for greeting/sample conversation) and get to the point, making sure whatever you put in here is really necessary.

**Sample Conversation**: Much like "greeting", this section is to show the AI how to speak by example. An example conversation would look something like:

*character name*: Hi!
{{user}}: Hello!
*character name*: How are you today?
{{user}}:I'm good, thanks!

You can also use {{char}} instead of the character's actual name, but generally it is not recommended to use it, since it always refer to the main character of a chat, so it will be messed up if it is used in the card of a secondary character. {{user}} is a placeholder which automatically gets replaced with your name in the chat.
Sample conversations, like greetings, take a different approach than personality and the Advanced fields, and are there for mimicking purposes. It can be tricky to get it right, since they can affect so many things, for instance, response length, and they're typically rather long as well. It does, however, work well with language models, because it shows the model how you want it to reply. Again, though, it is optional. If you don't have a particular style which you'd like the AI to follow, or if you don't feel like making the effort, you can omit that section. You can also only give the replies of the character, not your own.

### Advanced:

You should generally not mess with Advanced settings if you're just getting started. However, several of them can be very useful to know how to use once you get the hang of it.

**System Prompt**: It's like an initial message which is read as if coming from the system, so it serves as an instruction setter for the chat. By default, Agnai does send a short setup message to the AI so that it registers that the task it is supposed to perform is to reply for the character in a roleplay chat (you can modify it in a prompt template if you wish for different behavior). System prompt follows the same principle. Think of it like an instruction manual for your chat, used to tell the AI what to follow. Not to be confused with the prompt template.

**Post-conversation History Instructions (jailbreak/UJB)**: Large language models pay the most attention to the ending of the conversation, that is just how they work. If you want particularly strong instructions which the AI will adhere to in every reply, you can use the jailbreak. It's an effective way to make the model listen more, since it will be inserted at the bottom of the prompt sent to the AI. It's named a "jailbreak" because it has originally been used to bypass censorship on proprietary models, but you can also use it on uncensored models, since it's generally for the purposes of instructing a model to behave a certain way.

**Insert/Depth Prompt (Author's Note)**: Similar to the jailbreak, but it is inserted x messages before the end, where you set the x with the "Insert Depth" slider. Useful if you want to weaken the jailbreak by inserting the message a bit further from the very bottom of the prompt. If you want to insert messages at varying depth in your prompt, you can wrap them in insert tags in your prompt template, like: {{#insert x}} message {{/insert}}, where x is the number of your choosing.

**Character Book**: You can add a memory book to the character here, which will only be activated when this character replies. For adding a memory book to the whole chat, you'll want to go into the chat settings inside of a chat.

**Creator**: Field for the character creator's name. Purely cosmetic.

**Character Version**: Field for keeping track of character versions. Purely cosmetic.

**Voice**: You can set the voice service you use here (configure in the "Voice Settings" page in Settings, supported options: ElevenLabs, NovelAI, Web Speech Synthesis).

### Images

Here, you can set the settings for images for this character specifically. If you want global image settings, you should go to Settings -> Images. You can find the general instructions to setup both here, since they work similarly.

Firstly, choose a service. If you have a 10 dollar Agnai sub, the Agnaistic image generation is available, with DreamshaperXL Lightning model. If you use that model, use the recommended settings (5 steps, 2 CFG, 1024x1024 image size). You can also use NovelAI if you have a sub. If you are on free tier, then you can use Horde (somewhat slow and unreliable, but free) and Stable Diffusion (need to run it on your own machine in the background with appropriate hardware and connect it to Agnai. On Automatic1111, you can use --api --share arguments to generate a link, and paste it to Agnai)

Now let's move onto the specific parameters you can configure.

**Sampling Steps**: Steps in which the image is produced. Roughly, the more the better, but it depends on the sampler. If you use the DPM++ 2M Karras sampler for instance, you don't really need more than 25. With something like Euler a, it would give more benefits. If unsure, leave as-is.

**Image Width/Height**: Depends on whether you use a model based on SD 1.5 or SDXL. For the former, always leave one of width/height at 512, for the latter, 1024. By default, if unsure, use 512x512 or 1024x1024, depending on the model type, and if you want a different aspect ratio, adjust one of the dimensions. Agnaistic image generation is SDXL-based and cannot go beyond 1024x1024.

**CFG Scale**: (for Agnaistic image generation, use 2) It's how closely the image matches the prompt. As a default for non-Agnaistic, you can use around 7. Lower values might produce higher quality results but will stick to the prompt less, and higher values will do the opposite.

**Prompt Prefix/Suffix**: For adding stuff to the beginning/end of the prompt sent to the AI. Typically for prefix you want quality tags (best quality, masterpiece...) and for suffix, specific style tags (anime, realistic, full body).

**Negative Prompt**: For stuff you do not want in your image. e.g. bad quality, blurry, signature

**Summary Prompt**: Prompt sent to the language model to create a summary for your image. I'd recommend using one which outputs tags, if you use it (you can turn it off with the toggle below), because Stable Diffusion works better with those, looking for keywords, and not necessarily understanding full sentences well.