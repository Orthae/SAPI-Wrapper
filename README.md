# Wrapper for Microsoft SAPI
Small library thats wraps Microsoft SAPI into a easier to use package. 

# Overview

## SpeechEngine.h

Main endpoint

| Method                                  | Description                                  |
| ----------------------------------------|:-------------------------------------------:|
| void speak(std::string const &text)     | Sends text to speech system                 |
| void speak(std::wstring const &text)    | Sends text to speech system                 |
| void setRate(long rate)                 | Sets speech speed from range of -10 to 10   |
| long getRate() const                    | Returns current speech rate                 |
| void setVolume(unsigned short volume)   | Sets speech volume from range of 0 to 100   |
| unsigned short getVolume() const        | Returns speech volume                       |
| std::vector<Voice> getVoices() const    | Returns vector of available voices          |
| void setVoice(Voice voice)              | Changes speech voice                        |

  
## Voice.h
Class representing available voice from Windows registry.

| Method                                        | Description                                 |
| ----------------------------------------------|:-------------------------------------------:|
| std::wstring getAge() const                   | Returns age                                 |
| std::wstring getGender() const                | Returns gender                              |
| std::wstring getLanguageCode() const          | Returns language code                       |
| std::wstring getName() const                  | Returns name                                |
| std::wstring getSharedPronunciation() const   | Returns shared pronunciation                |
| std::wstring getVendor() const                | Returns vendor                              |
| std::wstring getVersion() const               | Returns version                             |
| ISpObjectToken * getVoiceToken() const        | Returns voice token                         |x

# Usage
First you need to create SpeechEngine object, then you can use it.
~~~
#include "SpeechEngine.h"
SpeechEngine speechEngine;
~~~

Using text to speech.
~~~
speechEngine.speak("Text to speak");
~~~
Changing voice.
~~~
//Where x is voice index in vector
Voice voice = speechEngine.getVoices().at(x);
speechEngine.setVoice(voice);
~~~

# TODO
* Exceptions
* Proper docs
* Smart pointers on COM interface
