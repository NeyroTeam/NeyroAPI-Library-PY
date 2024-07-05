```markdown
# NeyroAPI Python Library

This library provides a Python interface to interact with the Neyro API, supporting text, image, and audio functionalities.

## Installation

To install the library, use pip:

```bash
pip install neyro-api
```

## Usage

### Synchronous API

```python
from neyro_api import NeyroAPI

api_key = "YOUR_API_KEY"
captcha_key = "Captcha key"
neyro_api = NeyroAPI(api_key, captcha_key)

# Text API
text_response = neyro_api.text_gpt_new(messages=["Hello, how are you?"], model="gpt-3.5-turbo", max_tokens=512, temperature=0.9, plugins=[], id="b62f4cc5-0a7b-4044-9267-065c63c24469")
print("Text API Response:", text_response)

# Image API
image_response = neyro_api.image_sh(prompt="A beautiful landscape", width=512, height=512, steps=50, number=1, sampler="k_lms", model="stable_cascade", stream=True)
print("Image API Response:", image_response)

# Audio API
audio_response = neyro_api.audio_tts(model="google", voice="adam", text="Hello, this is a test.", language="en")
print("Audio API Response:", audio_response)
```

### Asynchronous API

```python
import asyncio
from neyro_api import AsyncNeyroAPI

api_key = "YOUR_API_KEY"
captcha_key = "Captcha key"
async_neyro_api = AsyncNeyroAPI(api_key, captcha_key)

async def main():
    text_response = await async_neyro_api.text_gpt_new(messages=["Hello, how are you?"], model="gpt-3.5-turbo", max_tokens=512, temperature=0.9, plugins=[], id="b62f4cc5-0a7b-4044-9267-065c63c24469")
    print("Async Text API Response:", text_response)

    image_response = await async_neyro_api.image_sh(prompt="A beautiful landscape", width=512, height=512, steps=50, number=1, sampler="k_lms", model="stable_cascade", stream=True)
    print("Async Image API Response:", image_response)

    audio_response = await async_neyro_api.audio_tts(model="google", voice="adam", text="Hello, this is a test.", language="en")
    print("Async Audio API Response:", audio_response)

asyncio.run(main())
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.

## License

This project is licensed under the MIT License.
```