# Assignment 01 - Understanding OpenAI Chat Completion API Parameters
## What is API? 
- The API is an application program interface. It is used to communicate between different applications or within an application.
  - Examples:
    - Send data from a Database hosted on a server to the front end of an application and vice versa.
    - Send data from one application to another application. e.g. Google & Facebook Login APIs for authorization.
    - Open AI and Gemini APIs that will retrieve data from the LLMs based on the given parameters.
## Open AI Chat Completion API Parameters:
 - Messages
   - Messages are used to instruct the LLM on what to respond and how to respond i.e. context of the conversation. <br> For example: <br>
     - An instruction for the system to respond in a Markdown format. <be>
   ```
   messages=
   {
       "role": "system",  # The role of the message
       "content": "You are a helpful assistant. Respond in Markdown format."  # Instructions for the system
   }
 - Model
   - The model specifies which Open AI model should be used to generate the response. There are different Open AI models for different purposes like o1-preview for complex tasks and o1-mini for coding and maths tasks. We will use GPT-4o mini as it is cost-efficient and has vision capabilities. 
 - Max Completion Tokens
   - To set the max tokens limit, we use this parameter while querying from the Open AI model. i.e. the ```max_token=50``` means the propmpt+response shouldn't consume more than 50 tokens. 
 - n
   - It defines the total number of responses. i.e. a maths problem might have multiple solutions so if we set ```n=3``` the model would respond up to three possible solutions. 
 - Stream
   - This parameter is used to continuously get the large response in segments instead of waiting for the complete response. It accepts boolean value e.g ```stream=True``` or ```stream=False```
 - Temperature
   - it is used to control the creativity of the response. The values range from (0.0) to (2.0)
     - Case: "_A room is used for_" with ```temperature=0.0```
       - A room is used for providing space for specific activities, such as living, sleeping, working, or storage.
     - Case: "_A room is used for_" with ```temperature=0.9```
       - A room is used for countless possibilities — from relaxing with a good book, hosting lively conversations, and creating art, to simply being a cozy retreat where you can unwind and dream.
 - Top_p
   - This parameter can be used in conjunction or as an alternative to ```temperature```. Its value ranges from 0.0 to 1.0 where 1.0 means to include all the possibilities in a response while 0.5 will consider the 50% of token probability mass which reduces the randomness of a response while keeping the diversity.
   - Lower ```top_p``` values focus the model on the most likely tokens, while higher values allow for broader token selection.
 - Tools
   - It makes the AI model more versatile by enabling it to interact with external systems. e.g. Calculator to perform mathematical operations or a browser to retrieve real-time data from the web.
   - Tools are typically pre-configured and accessible via specific API setups.  

  
