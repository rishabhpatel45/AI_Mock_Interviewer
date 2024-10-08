<h1>AI_Mock_Interviewer</h1>
<h3>This sophisticated tool is designed to simulate a real interview environment, helping you practice and refine your interview skills.</h3>


Welcome to the AI Mock Interviewer!

The provided code powers a sophisticated AI mock interviewer using a combination of the comprehensive LLM Meta Llama 3 8B, Speech Recognition library (STT), Google Text-to-Speech (gTTS) and Gradio via the Hugging Face Inference API. This model is designed to simulate a realistic interview environment, allowing users to practice and improve their interview skills. 

=>KEY FEATURES OF THE CODE

      1.AI-Powered Mock Interview System:Utilizes Meta Llama3 model for generating interview questions and evaluating responses.

      2.Multi-Modal Input Support:Accepts both audio (for user answers) and video inputs, enhancing the interview experience.

      4.Speech Synthesis and Recognition:Converts text questions to speech using Google Text-to-Speech (gTTS) and transcribes user answers from audio files using Google Speech Recognition.

      5.Dynamic Question Generation:Generates distinct questions based on topic, position, and difficulty level, ensuring a tailored and challenging interview experience.

      6.User ACCURACY assessment:Tracks the number of correct answers of the user out of the total answers
      
      7.Advanced Evaluation Logic:Evaluates user answer. If the user is right, the model praises him and moves to the next question, else, it PROVIDES A HINT and asks for revised answer. If the user is correct 
        this time, it praises him and moves to next question, else, PROVIDES THE CORRECT ANSWER and then moves to next question.

      8.To end the interview and view feedback, just input "finish interview" in user answer textbox.

      9.Performance Feedback:Generates detailed feedback on the user's interview performance, highlighting strengths and areas for improvement at the end of interview.

     10.Interactive User Interface:Implements a Gradio-based interface with a user-friendly design, allowing users to interact with the system seamlessly.

     11. Scalability and Flexibility:Designed to be easily extendable with additional functionalities or models, supporting various interview scenarios and topics.


=>INTERVIEW INTERFACE OVERVIEW

The code implements an interactive mock interview system using Gradio. Here's a detailed overview of the interface and its components:
Input Fields for Initial Details:
            Topic Input: A text box for the user to enter the topic of the interview.
            Position Input: A text box for the user to specify the position they are interviewing for.
            Difficulty Input: A radio button selection allowing the user to choose the difficulty level (easy, medium, hard)

->Gradio Interface Components
      
      Start Button:
            Start Interview Button: Initiates the interview process, generating the first question and preparing the system to handle user responses.

      Output Components:
            Question Output: A text box that displays the current interview question.
            Audio Output: An audio player to play the synthesized speech of the current interview question.
            Handle Answer Output: A hidden state to manage and pass the answer-handling function across interactions.
            Audio Input: An audio recorder for the user to submit their spoken answer.
            Video Input: A video recorder for the user to submit a video, used for sentiment analysis.
            Transcribed Output: A text box to display the transcribed version of the user's spoken answer.

      Submit Button:
      Submit Answer Button: Allows the user to submit their answer. This triggers the evaluation of the answer and generates the next question or feedback.


->Workflow
      Starting the Interview:
            The user enters the topic, position, and difficulty level.
            The user clicks the "Start Interview" button.
            The system generates the first question and plays its audio.

      Answer Submission:
            The user records their answer using the audio input (and optionally, a video input for sentiment analysis).
            The user clicks the "Submit Answer" button.
            The system processes the audio to transcribe the user's answer.
            The system evaluates the answer, provides feedback, hints if necessary, and generates the next question.

      Real-Time Interaction:
            The interface dynamically updates with each interaction, displaying the next question and playing its audio.
            The system maintains a conversation history, updating the user on their performance and guiding them through the interview process.

->Backend Processes
      Question Generation: Utilizes the Hugging Face language model to generate interview questions tailored to the provided topic, position, and difficulty.
      Answer Verification: Evaluates user answers against the expected responses, providing immediate feedback and hints if necessary.
      Speech Synthesis: Converts text questions and feedback into speech for a more immersive experience.
      Speech Recognition: Transcribes user answers from audio inputs.
      Feedback Generation: Provides detailed feedback on the user's overall performance, strengths, weaknesses, and areas for improvement.

This interactive interface simulates a realistic interview environment, offering comprehensive practice and feedback to users preparing for actual interviews.

=>MODEL CONFIGURATION

The code uses various models and services integrated through the Hugging Face Hub and other APIs to facilitate the mock interview. Here’s a summary of the model configurations and integrations:

      Hugging Face InferenceClient for Question Generation:
            Model: meta-llama/Meta-Llama-3-8B-Instruct
            Purpose: Generates interview questions based on the specified topic, position, and difficulty.

      Hugging Face Inference API for Facial Expression Recognition:
            Model: trpakov/vit-face-expression
            Purpose: Analyzes facial expressions from video frames to provide sentiment analysis.
            API URL: https://api-inference.huggingface.co/models/trpakov/vit-face-expression

      Text-to-Speech (TTS) Integration:
            Library: gTTS (Google Text-to-Speech)
            Purpose: Converts text to speech for audio playback of questions and feedback.
            Output Format: MP3 files (e.g., question.mp3, temp.mp3)

      Speech Recognition:
            Library: speech_recognition (using Google Speech-to-Text API)
            Purpose: Converts spoken responses into text.

      OpenCV:
            Library: cv2
            Purpose: Captures video frames.

This combination of models and APIs enables a comprehensive mock interview system that generates, verifies, and assesses interview responses, while providing real-time feedback.
