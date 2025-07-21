# cURL
```
curl --request POST \
  --url https://mkp-api.fptcloud.com/v1/audio/transcriptions \
  --header "Authorization: Bearer your-api-key" \
  --form "model=your-model-name" \
  --form "file=@your-file-path.mp3" \
  --form "language=en" \
  --form "response_format=json" \
  --max-time 60
```
# Python
```
from openai import OpenAI

BASE_URL = "https://mkp-api.fptcloud.com"
API_KEY = "your-api-key"
MODEL_NAME = "your-model-name"
LANGUAGE = 'en'

client = OpenAI(api_key=API_KEY, 
                base_url=BASE_URL)

file = "speech.wav"
# file = "speech.mp3"
with open(file, "rb") as audio_file:
    data = audio_file.read()
    response = client.audio.transcriptions.create(
        model=MODEL_NAME,
        file=data,
        language=LANGUAGE,
        timeout=60,
        response_format="json"
    )

    print(response.text)
```
