# CogVideo && CogVideoX

[中文阅读](./README_zh.md)

[日本語で読む](./README_ja.md)

<div align="center">
<img src=resources/logo.svg width="50%"/>
</div>
<p align="center">
Experience the CogVideoX-5B model online at <a href="https://huggingface.co/spaces/THUDM/CogVideoX-5B" target="_blank"> 🤗 Huggingface Space</a> or <a href="https://modelscope.cn/studios/ZhipuAI/CogVideoX-5b-demo" target="_blank"> 🤖 ModelScope Space</a>
</p>
<p align="center">
📚 View the <a href="https://arxiv.org/abs/2408.06072" target="_blank">paper</a> and <a href="https://zhipu-ai.feishu.cn/wiki/DHCjw1TrJiTyeukfc9RceoSRnCh" target="_blank">user guide</a>
</p>
<p align="center">
    👋 Join our <a href="resources/WECHAT.md" target="_blank">WeChat</a> and <a href="https://discord.gg/B94UfuhN" target="_blank">Discord</a> 
</p>
<p align="center">
📍 Visit <a href="https://chatglm.cn/video?lang=en?fr=osm_cogvideo">QingYing</a> and <a href="https://open.bigmodel.cn/?utm_campaign=open&_channel_track_key=OWTVNma9">API Platform</a> to experience larger-scale commercial video generation models.
</p>

## Update and News

- 🔥🔥 **News**: ```2024/8/27```: The **CogVideoX-2B** model's open-source license has been changed to the **Apache 2.0
  License**.
- 🔥🔥 **News**: ```2024/8/27```: We have open-sourced a larger model in the CogVideoX series, **CogVideoX-5B**.
  We have significantly optimized the model's inference performance, greatly lowering the inference threshold. You can
  run **CogVideoX-2B** on older GPUs like the `GTX 1080TI`, and run the **CogVideoX-5B** model on mid-range GPUs like
  the `RTX 3060`. Please ensure you update and install the dependencies according to
  the [requirements](requirements.txt), and refer to the [cli_demo](inference/cli_demo.py) for inference code.
- 🔥 **News**: ```2024/8/20```: [VEnhancer](https://github.com/Vchitect/VEnhancer) now supports enhancing videos
  generated by
  CogVideoX, achieving higher resolution and higher quality video rendering. We welcome you to try it out by following
  the [tutorial](tools/venhancer/README_zh.md).
- 🔥 **News**: ```2024/8/15```: The `SwissArmyTransformer` dependency in CogVideoX has been upgraded to `0.4.12`.
  Fine-tuning
  no longer requires installing `SwissArmyTransformer` from source. Additionally, the `Tied VAE` technique has been
  applied in the implementation within the `diffusers` library. Please install `diffusers` and `accelerate` libraries
  from source. Inference for CogVideoX now requires only 12GB of VRAM. The inference code needs to be modified. Please
  check [cli_demo](inference/cli_demo.py).
- 🔥 **News**: ```2024/8/12```: The CogVideoX paper has been uploaded to arxiv. Feel free to check out
  the [paper](https://arxiv.org/abs/2408.06072).
- 🔥 **News**: ```2024/8/7```: CogVideoX has been integrated into `diffusers` version 0.30.0. Inference can now be
  performed
  on a single 3090 GPU. For more details, please refer to the [code](inference/cli_demo.py).
- 🔥 **News**: ```2024/8/6```: We have also open-sourced **3D Causal VAE** used in **CogVideoX-2B**, which can
  reconstruct the video almost losslessly.
- 🔥 **News**: ```2024/8/6```: We have open-sourced **CogVideoX-2B**，the first model in the CogVideoX series of video
  generation models.
- 🌱 **Source**: ```2022/5/19```: We have open-sourced **CogVideo** (now you can see in `CogVideo` branch)，the **first**
  open-sourced pretrained text-to-video model, and you can
  check [ICLR'23 CogVideo Paper](https://arxiv.org/abs/2205.15868) for technical details.

**More powerful models with larger parameter sizes are on the way~ Stay tuned!**

## Table of Contents

Jump to a specific section:

- [Quick Start](#Quick-Start)
    - [SAT](#sat)
    - [Diffusers](#Diffusers)
- [CogVideoX-2B Video Works](#cogvideox-2b-gallery)
- [Introduction to the CogVideoX Model](#Model-Introduction)
- [Full Project Structure](#project-structure)
    - [Inference](#inference)
    - [SAT](#sat)
    - [Tools](#tools)
- [Introduction to CogVideo(ICLR'23) Model](#cogvideoiclr23)
- [Citations](#Citation)
- [Open Source Project Plan](#Open-Source-Project-Plan)
- [Model License](#Model-License)

## Quick Start

### Prompt Optimization

Before running the model, please refer to [this guide](inference/convert_demo.py) to see how we use large models like
GLM-4 (or other comparable products, such as GPT-4) to optimize the model. This is crucial because the model is trained
with long prompts, and a good prompt directly impacts the quality of the video generation.

### SAT

**Please make sure your Python version is between 3.10 and 3.12, inclusive of both 3.10 and 3.12.**

Follow instructions in [sat_demo](sat/README.md): Contains the inference code and fine-tuning code of SAT weights. It is
recommended to improve based on the CogVideoX model structure. Innovative researchers use this code to better perform
rapid stacking and development.

### Diffusers

**Please make sure your Python version is between 3.10 and 3.12, inclusive of both 3.10 and 3.12.**

```
pip install -r requirements.txt
```

Then follow [diffusers_demo](inference/cli_demo.py): A more detailed explanation of the inference code, mentioning the
significance of common parameters.

## Gallery

### CogVideoX-5B

<table border="0" style="width: 100%; text-align: left; margin-top: 20px;">
  <tr>
      <td>
          <video src="https://github.com/user-attachments/assets/cf5953ea-96d3-48fd-9907-c4708752c714" width="100%" controls autoplay loop></video>
      </td>
      <td>
          <video src="https://github.com/user-attachments/assets/fe0a78e6-b669-4800-8cf0-b5f9b5145b52" width="100%" controls autoplay loop></video>
      </td>
       <td>
          <video src="https://github.com/user-attachments/assets/c182f606-8f8c-421d-b414-8487070fcfcb" width="100%" controls autoplay loop></video>
     </td>
      <td>
          <video src="https://github.com/user-attachments/assets/7db2bbce-194d-434d-a605-350254b6c298" width="100%" controls autoplay loop></video>
     </td>
  </tr>
  <tr>
      <td>
          <video src="https://github.com/user-attachments/assets/62b01046-8cab-44cc-bd45-4d965bb615ec" width="100%" controls autoplay loop></video>
      </td>
      <td>
          <video src="https://github.com/user-attachments/assets/d78e552a-4b3f-4b81-ac3f-3898079554f6" width="100%" controls autoplay loop></video>
      </td>
       <td>
          <video src="https://github.com/user-attachments/assets/30894f12-c741-44a2-9e6e-ddcacc231e5b" width="100%" controls autoplay loop></video>
     </td>
      <td>
          <video src="https://github.com/user-attachments/assets/926575ca-7150-435b-a0ff-4900a963297b" width="100%" controls autoplay loop></video>
     </td>
  </tr>
</table>

### CogVideoX-2B

<table border="0" style="width: 100%; text-align: left; margin-top: 20px;">
  <tr>
      <td>
          <video src="https://github.com/user-attachments/assets/ea3af39a-3160-4999-90ec-2f7863c5b0e9" width="100%" controls autoplay loop></video>
      </td>
      <td>
          <video src="https://github.com/user-attachments/assets/9de41efd-d4d1-4095-aeda-246dd834e91d" width="100%" controls autoplay loop></video>
      </td>
       <td>
          <video src="https://github.com/user-attachments/assets/941d6661-6a8d-4a1b-b912-59606f0b2841" width="100%" controls autoplay loop></video>
     </td>
      <td>
          <video src="https://github.com/user-attachments/assets/938529c4-91ae-4f60-b96b-3c3947fa63cb" width="100%" controls autoplay loop></video>
     </td>
  </tr>
</table>

To view the corresponding prompt words for the gallery, please click [here](resources/galary_prompt.md)

## Model Introduction

CogVideoX is an open-source version of the video generation model originating
from [QingYing](https://chatglm.cn/video?lang=en?fr=osm_cogvideo). The table below displays the list of video generation
models we currently offer, along with their foundational information.

<table style="border-collapse: collapse; width: 100%;">
  <tr>
    <th style="text-align: center;">Model Name</th>
    <th style="text-align: center;">CogVideoX-2B</th>
    <th style="text-align: center;">CogVideoX-5B</th>
  </tr>
  <tr>
    <td style="text-align: center;">Model Description</td>
    <td style="text-align: center;">Entry-level model, balancing compatibility. Low cost for running and secondary development.</td>
    <td style="text-align: center;">Larger model with higher video generation quality and better visual effects.</td>
  </tr>
  <tr>
    <td style="text-align: center;">Inference Precision</td>
    <td style="text-align: center;"><b>FP16* (Recommended)</b>, BF16, FP32, FP8*, INT8, no support for INT4</td>
    <td style="text-align: center;"><b>BF16 (Recommended)</b>, FP16, FP32, FP8*, INT8, no support for INT4</td>
  </tr>
  <tr>
    <td style="text-align: center;">Single GPU VRAM Consumption</td>
    <td style="text-align: center;">FP16: 18GB using <a href="https://github.com/THUDM/SwissArmyTransformer">SAT</a> / <b>12.5GB* using diffusers</b><br><b>INT8: 7.8GB* using diffusers with torchao</b></td>
    <td style="text-align: center;">BF16: 26GB using <a href="https://github.com/THUDM/SwissArmyTransformer">SAT</a> / <b>20.7GB* using diffusers</b><br><b>INT8: 11.4GB* using diffusers with torchao</b></td>
  </tr>
  <tr>
    <td style="text-align: center;">Multi-GPU Inference VRAM Consumption</td>
    <td style="text-align: center;"><b>FP16: 10GB* using diffusers</b></td>
    <td style="text-align: center;"><b>BF16: 15GB* using diffusers</b></td>
  </tr>
  <tr>
    <td style="text-align: center;">Inference Speed<br>(Step = 50, FP/BF16)</td>
    <td style="text-align: center;">Single A100: ~90 seconds<br>Single H100: ~45 seconds</td>
    <td style="text-align: center;">Single A100: ~180 seconds<br>Single H100: ~90 seconds</td>
  </tr>
  <tr>
    <td style="text-align: center;">Fine-tuning Precision</td>
    <td style="text-align: center;"><b>FP16</b></td>
    <td style="text-align: center;"><b>BF16</b></td>
  </tr>
  <tr>
    <td style="text-align: center;">Fine-tuning VRAM Consumption (per GPU)</td>
    <td style="text-align: center;">47 GB (bs=1, LORA)<br> 61 GB (bs=2, LORA)<br> 62GB (bs=1, SFT)</td>
    <td style="text-align: center;">63 GB (bs=1, LORA)<br> 80 GB (bs=2, LORA)<br> 75GB (bs=1, SFT)</td>
  </tr>
  <tr>
    <td style="text-align: center;">Prompt Language</td>
    <td colspan="2" style="text-align: center;">English*</td>
  </tr>
  <tr>
    <td style="text-align: center;">Prompt Length Limit</td>
    <td colspan="2" style="text-align: center;">226 Tokens</td>
  </tr>
  <tr>
    <td style="text-align: center;">Video Length</td>
    <td colspan="2" style="text-align: center;">6 Seconds</td>
  </tr>
  <tr>
    <td style="text-align: center;">Frame Rate</td>
    <td colspan="2" style="text-align: center;">8 Frames per Second</td>
  </tr>
  <tr>
    <td style="text-align: center;">Video Resolution</td>
    <td colspan="2" style="text-align: center;">720 x 480, no support for other resolutions (including fine-tuning)</td>
  </tr>
  <tr>
    <td style="text-align: center;">Positional Encoding</td>
    <td style="text-align: center;">3d_sincos_pos_embed</td>
    <td style="text-align: center;">3d_rope_pos_embed</td>
  </tr>
  <tr>
    <td style="text-align: center;">Download Page (Diffusers)</td>
    <td style="text-align: center;"><a href="https://huggingface.co/THUDM/CogVideoX-2b">🤗 HuggingFace</a><br><a href="https://modelscope.cn/models/ZhipuAI/CogVideoX-2b">🤖 ModelScope</a><br><a href="https://wisemodel.cn/models/ZhipuAI/CogVideoX-2b">🟣 WiseModel</a></td>
    <td style="text-align: center;"><a href="https://huggingface.co/THUDM/CogVideoX-5b">🤗 HuggingFace</a><br><a href="https://modelscope.cn/models/ZhipuAI/CogVideoX-5b">🤖 ModelScope</a><br><a href="https://wisemodel.cn/models/ZhipuAI/CogVideoX-5b">🟣 WiseModel</a></td>
  </tr>
  <tr>
    <td style="text-align: center;">Download Page (SAT)</td>
    <td colspan="2" style="text-align: center;"><a href="./sat/README.md">SAT</a></td>
  </tr>
</table>

**Data Explanation**

- When testing with the diffusers library, the `enable_model_cpu_offload()` option and `pipe.vae.enable_tiling()`
  optimization were enabled. This solution has not been tested for actual VRAM/memory usage on devices other than *
  *NVIDIA A100/H100**. Generally, this solution can be adapted to all devices with **NVIDIA Ampere architecture** and
  above. If optimization is disabled, VRAM usage will increase significantly, with peak VRAM approximately 3 times the
  value in the table.
- When performing multi-GPU inference, the `enable_model_cpu_offload()` optimization needs to be disabled.
- Using an INT8 model will result in reduced inference speed. This is done to accommodate GPUs with lower VRAM, allowing
  inference to run properly with minimal video quality loss, though the inference speed will be significantly reduced.
- The 2B model is trained using `FP16` precision, while the 5B model is trained using `BF16` precision. It is
  recommended to use the precision used in model training for inference.
- [PytorchAO](https://github.com/pytorch/ao) and [Optimum-quanto](https://github.com/huggingface/optimum-quanto/) can be
  used to quantize the Text Encoder, Transformer and VAE modules to lower the memory requirement of CogVideoX. This
  makes it possible to run the model on free-tier T4 Colab or smaller VRAM GPUs as well! It is also worth noting that
  TorchAO quantization is fully compatible with `torch.compile`, which allows for much faster inference speed. `FP8`
  precision must be used on `NVIDIA H100` and above devices, requiring source installation of
  the `torch`, `torchao`, `diffusers`, and `accelerate` Python packages. `CUDA 12.4` is recommended.
- Inference speed testing also used the aforementioned VRAM optimization scheme. Without VRAM optimization, inference
  speed increases by about 10%. Only models using `diffusers` support quantization.
- The model only supports English input; other languages can be translated to English during large model refinements.

## Friendly Links

We highly welcome contributions from the community and actively contribute to the open-source community. The following
works have already been adapted for CogVideoX, and we invite everyone to use them:

+ [Xorbits Inference](https://github.com/xorbitsai/inference): A powerful and comprehensive distributed inference
  framework, allowing you to easily deploy your own models or the latest cutting-edge open-source models with just one
  click.
+ [VideoSys](https://github.com/NUS-HPC-AI-Lab/VideoSys): VideoSys provides a user-friendly, high-performance
  infrastructure for video generation, with full pipeline support and continuous integration of the latest models and
  techniques.

## Project Structure

This open-source repository will guide developers to quickly get started with the basic usage and fine-tuning examples
of the **CogVideoX** open-source model.

### Inference

+ [dcli_demo](inference/cli_demo.py): A more detailed inference code explanation, including the significance of
  common parameters. All of this is covered here.
+ [cli_demo_quantization](inference/cli_demo_quantization.py):
  Quantized model inference code that can run on devices with lower memory. You can also modify this code to support
  running CogVideoX models in FP8 precision.
+ [diffusers_vae_demo](inference/cli_vae_demo.py): Code for running VAE inference separately.
+ [space demo](inference/gradio_composite_demo): The same GUI code as used in the Huggingface Space, with frame
  interpolation and super-resolution tools integrated.
+ [convert_demo](inference/convert_demo.py): How to convert user input into long-form input suitable for CogVideoX.
  Since CogVideoX is trained on long texts, we need to transform the input text distribution to match the training data
  using an LLM. The script defaults to using GLM-4, but it can be replaced with GPT, Gemini, or any other large language
  model.
+ [gradio_web_demo](inference/gradio_web_demo.py): A simple Gradio web application demonstrating how to use the
  CogVideoX-2B / 5B model to generate videos. Similar to our Huggingface Space, you can use this script to run a simple
  web
  application for video generation.

```shell
cd inference
# For Linux and Windows users
python gradio_web_demo.py

# For macOS with Apple Silicon users, Intel not supported, this maybe 20x slower than RTX 4090
PYTORCH_ENABLE_MPS_FALLBACK=1 python gradio_web_demo.py
```

<div style="text-align: center;">
    <img src="resources/gradio_demo.png" style="width: 100%; height: auto;" />
</div>

### sat

+ [sat_demo](sat/README.md): Contains the inference code and fine-tuning code of SAT weights. It is recommended to
  improve based on the CogVideoX model structure. Innovative researchers use this code to better perform rapid stacking
  and development.

### Tools

This folder contains some tools for model conversion / caption generation, etc.

+ [convert_weight_sat2hf](tools/convert_weight_sat2hf.py): Convert SAT model weights to Huggingface model weights.
+ [caption_demo](tools/caption): Caption tool, a model that understands videos and outputs them in text.

## CogVideo(ICLR'23)

The official repo for the
paper: [CogVideo: Large-scale Pretraining for Text-to-Video Generation via Transformers](https://arxiv.org/abs/2205.15868)
is on the [CogVideo branch](https://github.com/THUDM/CogVideo/tree/CogVideo)

**CogVideo is able to generate relatively high-frame-rate videos.**
A 4-second clip of 32 frames is shown below.

![High-frame-rate sample](https://raw.githubusercontent.com/THUDM/CogVideo/CogVideo/assets/appendix-sample-highframerate.png)

![Intro images](https://raw.githubusercontent.com/THUDM/CogVideo/CogVideo/assets/intro-image.png)
<div align="center">
  <video src="https://github.com/user-attachments/assets/2fa19651-e925-4a2a-b8d6-b3f216d490ba" width="80%" controls autoplay></video>
</div>


The demo for CogVideo is at [https://models.aminer.cn/cogvideo](https://models.aminer.cn/cogvideo/), where you can get
hands-on practice on text-to-video generation. *The original input is in Chinese.*

## Citation

🌟 If you find our work helpful, please leave us a star and cite our paper.

```
@article{yang2024cogvideox,
  title={CogVideoX: Text-to-Video Diffusion Models with An Expert Transformer},
  author={Yang, Zhuoyi and Teng, Jiayan and Zheng, Wendi and Ding, Ming and Huang, Shiyu and Xu, Jiazheng and Yang, Yuanming and Hong, Wenyi and Zhang, Xiaohan and Feng, Guanyu and others},
  journal={arXiv preprint arXiv:2408.06072},
  year={2024}
}
@article{hong2022cogvideo,
  title={CogVideo: Large-scale Pretraining for Text-to-Video Generation via Transformers},
  author={Hong, Wenyi and Ding, Ming and Zheng, Wendi and Liu, Xinghan and Tang, Jie},
  journal={arXiv preprint arXiv:2205.15868},
  year={2022}
}
```

## Open Source Project Plan

- [x] CogVideoX Model Open Source
    - [x] CogVideoX Model Inference Example (CLI / Web Demo)
    - [x] CogVideoX Online Experience Example (Huggingface Space)
    - [x] CogVideoX Open Source Model API Interface Example (Huggingface)
    - [x] CogVideoX Model Fine-Tuning Example (SAT)
    - [ ] CogVideoX Model Fine-Tuning Example (Huggingface Diffusers)
    - [X] CogVideoX-5B Open Source (Adapted to CogVideoX-2B Suite)
    - [X] CogVideoX Technical Report Released
    - [X] CogVideoX Technical Explanation Video
- [ ] CogVideoX Peripheral Tools
    - [X] Basic Video Super-Resolution / Frame Interpolation Suite
    - [ ] Inference Framework Adaptation
    - [ ] ComfyUI Full Ecosystem Tools

We welcome your contributions! You can click [here](resources/contribute_zh.md) for more information.

## License Agreement

The code in this repository is released under the [Apache 2.0 License](LICENSE).

The CogVideoX-2B model (including its corresponding Transformers module and VAE module) is released under
the [Apache 2.0 License](LICENSE).

The CogVideoX-5B model (Transformers module) is released under
the [CogVideoX LICENSE](https://huggingface.co/THUDM/CogVideoX-5b/blob/main/LICENSE).
