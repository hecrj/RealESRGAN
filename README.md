# RealESRGAN

A fork of [`Real-ESRGAN`](https://github.com/ai-forever/Real-ESRGAN). Used in some of my projects.

This fork mainly removes the `huggingface-hub` dependency, for now.

Also, additional models (like `4x-Ultrasharp`) have been converted and are available in [the HuggingFace repository](https://huggingface.co/hecrj/RealESRGAN).

### Installation

```bash
uv add https://github.com/hecrj/RealESRGAN.git
```

### Usage

```python
from PIL import Image
from RealESRGAN import RealESRGAN

import torch

device = torch.device('cuda' if torch.cuda.is_available() else 'cpu')

model = RealESRGAN(device, scale=4)
model.load_weights('weights/RealESRGAN_x4.pth')

image = Image.open('input.png').convert('RGB')

output = model.predict(image)
output.save('output.png')
```

Download the models you want to use from [HuggingFace](https://huggingface.co/hecrj/RealESRGAN).
