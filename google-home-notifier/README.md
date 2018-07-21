# node-red flow for google-home-notifier with Google Cloud Text-To-Speech

## Feature

- Supports Google Cloud Text-To-Speech
	- Hi-Fi speech quality.
	- Supports to change voice.
	- Supports to change rate/pitch of speech.
- Supports volume level of notification.
- Supports audio url.
- Synchronize successive notification request.
- Requrires customized google-home-notifier: https://github.com/tinoue/google-home-notifier

## Inputs:

- msg.payload : Text to notify
- msg.audio : Optional. if true the msg.payload is URL of MP3 audio.
- msg.volume : Optional. value takes between 0 and 1.

## Settings:

### Common Settings
- `Set Google Home hostname/IP address` node
	- Optional. Set this if you have trouble finding your Google Home.
- `Set params for google-home-notifier` node
	- language: Two letter country code. 'en' by default.
	- volume_default: Value takes 0 between 1. Set 0 not to change volume level.
	- use_cloud_tts: Use high quality Google Clound Text-To-Speech which you need to have account of Google Cloud Platform.

### Settings for Google Cloud Text-To-Speech
- `Set apikey of Cloud Text-To-Speech` node
	- Set API key. Handle the key with care.
- `Set params for Google Cloud Text-To-Speech` node
	- See [demo page](https://cloud.google.com/text-to-speech/). Press "Show JSON" to get value of the following parameters.
	- languageCode : Default is "en-US".
	- voliceName : Default is "en-US-Wavenet-D"
	- speakingRate: value between 0.25 and 4.0. default is 1.0
	- pitch: value between -20 and 20. default is 0.0

## Installation

### Plugin dependencies:
- node-red-contrib-credentials
- node-red-contrib-hostip
- node-red-node-base64

### Install google-home-notifier with volume API

```
cd <your node-red directory>
npm i https://github.com/tinoue/google-home-notifier.git
```

Note. This is a forked version which supports volume API.
Also this version includes [horihiro's patch](https://github.com/noelportugal/google-home-notifier/pull/41) which you don't have to edit browser.js.

### Edit .node-red/settings.js
```javascript

   functionGlobalContext: {
      googlehomenotifier:require('google-home-notifier')
   :
},
```

### restart node-red

