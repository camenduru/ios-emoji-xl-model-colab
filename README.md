🐣 Please follow me for new updates https://twitter.com/camenduru <br />
🔥 Please join our discord server https://discord.gg/k5BwmmvJJU <br />
🥳 Please join my patreon community https://patreon.com/camenduru <br />

## 🦒 Colab

| Colab | Info
| --- | --- |
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/camenduru/ios-emoji-xl-model-colab/blob/main/ios_emoji_xl_v2_model_colab.ipynb) | ios_emoji_xl_v2_model_colab
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/camenduru/ios-emoji-xl-model-colab/blob/main/ios_emoji_xl_v1_model_colab.ipynb) | ios_emoji_xl_v1_model_colab

## Version 1.0 (72x72 pixel)

```py
Trained with 72x72 pixel apple emojis 😋

GPU = Nvidia A40 (Large) at https://replicate.com
Num examples = 3953
Num batches each epoch = 989
Num Epochs = 2
Instantaneous batch size per device = 4
Total train batch size (w. parallel, distributed & accumulation) = 4
Gradient Accumulation steps = 1
Total optimization steps = 1000
Total Run time: 44.26 minutes
Total Cost: $1.94
```

## Version 2.0 (160x160 pixel)

```py
Trained with 160x160 pixel ios v16.4 emojis 😋

GPU = Nvidia A40 (Large) at https://replicate.com
Num examples = 4129
Num batches each epoch = 1033
Num Epochs = 1
Instantaneous batch size per device = 4
Total train batch size (w. parallel, distributed & accumulation) = 4
Gradient Accumulation steps = 1
Total optimization steps = 1000
Total Run time: 45.46 minutes
Total Cost: $1.98
```

## Version 2.0 Stable Diffusion WebUI LoRA
https://civitai.com/models/140968/emoji-xl <br />
https://huggingface.co/camenduru/ios-emoji-xl/blob/main/ios_emoji_xl_v2_lora_webui.safetensors <br />

## Model & Dataset Repo
https://huggingface.co/camenduru/ios-emoji-xl/tree/main

## Replicate LoRA to WebUI LoRA Converter Code
- Thanks to
- https://github.com/ignacfetser ❤
- huggingface/diffusers#2326 ❤
- https://github.com/harrywang/finetune-sd/blob/main/convert-to-safetensors.py ❤

```py
pip install safetensors==0.3.3

import re
from safetensors.torch import load_file, save_file
checkpoint = load_file('/content/ui/models/Lora/ios_emoji_xl_v2_lora.safetensors')
new_dict = dict()
for idx, key in enumerate(checkpoint):
    new_key = re.sub('\.processor\.', '_', key)
    new_key = re.sub('mid_block\.', 'mid_block_', new_key)
    new_key = re.sub('_lora.up.', '.lora_up.', new_key)
    new_key = re.sub('_lora.down.', '.lora_down.', new_key)
    new_key = re.sub('\.(\d+)\.', '_\\1_', new_key)
    new_key = re.sub('to_out', 'to_out_0', new_key)
    new_key = 'lora_unet_' + new_key
    new_dict[new_key] = checkpoint[key]
save_file(new_dict, 'ios_emoji_xl_v2_lora_converted.safetensors')
```

## Output Version 2.0
|  |  |  |  |  |
| --- | --- | --- | --- | --- |
![download (8)](https://github.com/camenduru/ios-emoji-xl-model-colab/assets/54370274/e1b834aa-8342-4d87-86f2-3c47c8bc083e) | ![download](https://github.com/camenduru/ios-emoji-xl-model-colab/assets/54370274/6a7d2424-e29a-40ff-a500-70544e680447) | ![download (15)](https://github.com/camenduru/ios-emoji-xl-model-colab/assets/54370274/0e02f62f-1001-40a9-b8ac-a826506a74cd) | ![download (20)](https://github.com/camenduru/ios-emoji-xl-model-colab/assets/54370274/4f94d267-b190-4808-84e3-e91e83bdf8eb) | ![3179b54e-f9fd-4992-b6a5-8bcefc1eddd2](https://github.com/camenduru/ios-emoji-xl-model-colab/assets/54370274/c5db74ea-572b-4098-a912-847c4c2a7bc9)

## Output Version 1.0
|  |  |  |  |  |
| --- | --- | --- | --- | --- |
![out-0](https://github.com/camenduru/ios-emoji-xl-model-colab/assets/54370274/63ced594-e889-40f5-9d50-dd3cec1efaed) | ![5](https://github.com/camenduru/ios-emoji-xl-model-colab/assets/54370274/1a87d515-38d5-439c-bbd1-523f46de8d1f) | ![download (2)](https://github.com/camenduru/ios-emoji-xl-model-colab/assets/54370274/3c01739f-6094-4eeb-893a-3b4f4ab91337) | ![download](https://github.com/camenduru/ios-emoji-xl-model-colab/assets/54370274/63f7beb3-e4c6-4f29-ba91-c7cc79f2c723) | ![download (1)](https://github.com/camenduru/ios-emoji-xl-model-colab/assets/54370274/6ce8f20f-3a43-4013-9f9c-60765b30892a)

## Special Thanks
Thanks to https://github.com/samuelngs/apple-emoji-linux for the 160x160 pixel emojis ❤ <br />
Thanks to fofr ❤ for the idea. better model: https://twitter.com/fofrAI/status/1698741974835065171 <br />
Thanks to https://replicate.com ❤ <br />
