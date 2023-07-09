# voice-sentiment
Create an AI model capable of predicting emotional state of the user by the use of voice and natural language understanding.
This is the final project for the Building AI course from [Elements of AI](https://www.elementsofai.com/). Please note that this is an idea for a project and not a finished solution.


## Summary

Create a model that is able to predict the emotional state of a user, when the user is dialoguing with the solution. The sentiment labela need to be defined with the help of a psychologist, The features to consider will range from voice tone, sentiment analysis of transcribed content, earlier dialogs, and questions the solutions asks the user.


## Background

The problem is 
The state of the art of voice assistants and chatbots is neutral, in the sense that these do not consider the tone of the user who's speaking, or the sentiment of the instructions the user is delivering. The lack of sentsitivity to the delivery makes the assistant feel and sound both robotic and emotionless, which in turn makes a chatbot or voice assistant feel artificial. This problemm is relevant to any existingvoice assistant or chatbot. My personal motivation for creating a solution is mainly the desire to quantify emotions so that we can create better communication tools that feel more human. Imagine if an elder interacting with this solution could feel truly accompanied by an empathetic robot.
Allthough this could be partially solved with a workaround by asking the user how she is feeling today, but it would not be an online detection.
Once an emotional state has been defined (predicted), this information can be used to configure the chatbot so that it behaves differently, depending on the emotional state defined. For example, if the user is feeling a bit blue or sad, the responses delivered by the Large Language Model (LLM), should be configured to produce more compassionate answers or suggest actions that make the user feel accompanied in her emotional state, such as playing favourite music. Or if the user feels active and eager to know, to let the LLM answer swiftly and concise. The analysis of the user's emotional state could enable adapting the interaction with the user in real time.


## How is it used?

Upon the user activates the conversation with the bot, the bot could ask, how the user is feeling today. With that piece of information, mapped to a supported emotional state, the bot can use an LLM to provide an answer that is fit and pertinent to a persona in that emotional state. Throughout the session, by sensing how the user is speaking, tone, velocity, volume, pauses, and by analyzing the sentiment of what the user is saying, the bot will be able to change its overall assesment of how the user is feeling, and adapt its reponses.

This solution could be applied to any situation when the user is asking to have a chat, ranging from early morning to find out what to eat for breakfast, how to dress for current weather

Any user able to pronounce lexically correct and distinguishable utterances, could be helped by this solution, no matter age, gender or other caracteristics of the user. Ideally, the solution should be able to learn from the user how to identify her, as to improve resilience against disturbing contexts and noise.

Here's an overview of initially identified components:

* User's Web Browser: This is the front-end component of the app, running in the user's web browser. It captures the user's voice input and sends it to the Web Server for processing.

* Web Server: This is the back-end component of the app, running on a server. It receives the user's voice input, transcribes it into text using a Speech-to-Text service, sends the text to the OpenAI API for ChatGPT, receives the response, and sends it to the Response Synthesizer. This components configures also the next action to be taken, whether it´s a response from the LLM or a conversational pattern to apply depending the emoational state of the user

* Emotional-state-analyzer: This component determines the emotional state the user is in, and provides a pertinent output to be consumed by the web server.

* Speech-to-Text Service: This component converts the user's voice input into text. You can use a service like Google Cloud Speech-to-Text or AWS Transcribe for this.

* OpenAI API for ChatGPT: This component provides an API for ChatGPT, allowing you to send text to the model and receive a response. You can use the OpenAI API for this.

* Text-to-Speech Service: This component converts the response text into audio. You can use a service like Amazon Polly or Google Cloud Text-to-Speech for this.

* Response Synthesizer: This component plays the audio response back to the user. It could be a web audio API, such as Web Audio API or MediaRecorder API, that generates audio from the response and plays it back to the user.


## Data sources and AI methods

The data can be gathered from different sources:
* voice recording captured by the voice assistant with subsequent emotional state labeling by humans
* sentiment analysis of transcribed text
* earlier interactions with the user, such as a time window for the now moment, say one hour, or earlier days interactions

By creating a responsive web app, powered by speech-to-text, speech-synthesis, content configuration, and LLM text inference, voice data can be collected that will serve as training data for the emotional state sentiment model.


## Challenges

The sentiment model will not be able to provide meaninful answers by itself. It needs to pass its output to content generating modules such as LLMs or search engines in the pipeline. The ethical considerations should be carefully examined since this model can be easily exploited to extract information about the users current emotional state and use it in a manner that doesn't inflict on the user's privacy or consented handling of the personal data.


## What next?

To start building the project I foresee the following skills to be needed:
* Psychology of the human behavior to decipher conversational context and how to best approach it to make it a pleasant experience. Needs research, working together with experts in the field, and creating prototypes to validate provided assumptions
* Data scientist and research team to create the model that will predict the user's emotional state
* Data engineer to create the data pipeline needed to feed the models
* Web application engineers to create the fullstack web app that stores voice data and provides a user experience close to a real conversation between two humans
* Legal assistance to provide awareness of ethical dropholes and assess compliancy to privacy regulations
* Funding for a research project
