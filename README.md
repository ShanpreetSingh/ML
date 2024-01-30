# ML
Audio to Text
I have used SpeechRecognition  library of python.
The required code is:

import speech_recognition as sr

def audio2text(audio_file_path):
    recognizer = sr.Recognizer()

    with sr.AudioFile(audio_file_path) as audio_file:
        audio_data = recognizer.record(audio_file)

    try:
        text = recognizer.recognize_google(audio_data)
        print("Transcript: {}".format(text))
    except sr.UnknownValueError:
        print("Speech Recognition could not understand the audio")
    except sr.RequestError as e:
        print("Could not request results from Google Speech Recognition service; {0}".format(e))



