# cURL 
curl --request POST \
  --url https://mkp-api.fptcloud.com/v1/audio/speech \
  --header "Authorization: Bearer your-api-key" \
  --header "Content-Type: application/json" \
  --data '{
    "model": "your-model-name",
    "input": "xin chào, chúng tôi là FPT",
    "voice": "std_kimngan"
  }' \
  --output speech.wav
# Python
from openai import OpenAI

BASE_URL = "https://mkp-api.fptcloud.com"
API_KEY = "your-api-key"
MODEL_NAME = 'your-model-name'
VOICE = "std_kimngan"

client = OpenAI(api_key=API_KEY, 
                base_url=BASE_URL)

response = client.audio.speech.create(
    input="xin chào, chúng tôi là FPT",
    model=MODEL_NAME,
    voice=VOICE,
)

response.write_to_file("speech.wav")
