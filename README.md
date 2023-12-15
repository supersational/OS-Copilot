# OS-Copilot

How it works:

### Custom GPTs
ChatGPT Plus users can now create custom GPTs which support "Actions" (https://platform.openai.com/docs/actions) These are incredibly powerful as they allow a GPT to interact with the world. This project connects a custom GPT to a computer by giving it a set of actions it can choose from. Currently we have mouse clicking, keyboard typing, performing hotkeys (multiple keys at the same time), and an action that simply 'looks' at the screen. 

You can use the OS-Copilot GPT on a smartphone or via the website, even using the same computer that you wish to control (although it becomes slightly harder to use the chat interface when it is using another application).

### Seeing the screen
All major operating systems have accessibility APIs, these help people with vision impairments to read and use a computer. A challenging part of this project was designing a way to convert the screen reader data into HTML which the GPT can read in text format. Not all apps support screen readers, but other researchers are improving vision-based AI that could replace the need for screen reader support. There are both benefits and drawbacks to using this non-vision-based method, but in future both methods may be combined to support each other dynamically. 

### Project Future:
Crafting a computer agent robust enough to be genuinely useful is a challenging task, but there are smaller milestones along the way. One useful new feature will be the ability to convert an action sequence into a hotkey - the AI agent will write code that operates on the UI, and this can be triggered by a hotkey or UI condition. This method would avoid the latency of asking an AI, since the AI would only be needed to write the code sequence (and step in if the code didn't work), similar methods are being employed in robotics where the language-model writes code that controls the robot in a precise way.

Fine tuning a smaller model to run locally for this task would be useful to avoid the need to send any data to a 3rd party (currently OpenAI), and will allow for exciting improvements like continuous improvement and learning to use new apps. 

Porting to platforms other than OSX is also a long term goal, the system already designed in a modular way - the OSX screen reading and control in a seperate module. However adding other OSs  will require a lot of effort and programming expertise.


### FAQ
- Why don't you let it run code via an action? This would make it much more powerful (e.g. like AutoGPT)
	- Seeing the mouse move and words being typed on the screen has a lot of advantages over a command line script being run - it is understandable, you can debug it easier, and you can stop it as soon as you see something going wrong (simply moving the mouse overrides the action)
- Where is the source code? 
	- Source code is not very useful without documentation on how to use it. That takes time to write but I would like to release this if there is enough interest, so let me know if you think you have a use for it!
- Is this possible to use without ChatGPT plus?
	- In theory, yes. The previous version of this was simpler and capable of using any language model, and using a specialised model would be interesting to investigate! But currently, GPT-4 is the best model for the job since it is able to perform multiple actions in a single chat-reply. However it would not be that difficult to hook this up to another model. 
