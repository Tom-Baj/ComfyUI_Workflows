ComfyUI beginner friendly Flux.2 Klein 4B GGUF Simple Fast Consistent Character Dataset Builder Workflow by Sarcastic TOFU
===========================================================================================================================

This is a very simple, beginner-friendly ComfyUI workflow—based on Flux.2 Klein 4B GGUF—that quickly and consistently builds character datasets. It works with straightforward, natural-language text instructions to generate your desired character dataset from just a single reference image, enabling you to train a LoRA later. Unlike other consistent character dataset builders that use SDXL or Flux, this workflow involves no lengthy processes. Flux.2 Klein is excellent on its own at preserving and reusing character details from a reference image, allowing you to generate multiple outputs in quick succession. This is an adaptation of my earlier similar Consistent Character Dataset Builder Workflows based on QWEN Image Edit & Kontext, but with much improved speed and quality.

I used a Q8 Model that works well with my 8GB AMD GPU. But is you have better GPU you can simply swap the model with full unquantized Flux.2 Klein 4B model or on the other side if you have a weaker GPU you can find other low grade hardware supported GGUF models from here ( Unsloth's HuggingFace repo for Flux.2 Klein 4B GGUF models - https://huggingface.co/unsloth/FLUX.2-klein-4B-GGUF/tree/main ) and other mathing resources.

The Flux.2 Klein 4B and 9B models are a new family of high-speed AI image generators that use a "rectified flow" architecture to unify image generation and professional-grade editing into a single, compact package. These models are significantly faster than older versions because they use "step-distillation," which allows them to create high-quality images in just 4 steps—achieving sub-second speeds on modern hardware—rather than the dozens of steps required by previous models. The 4B variant is released under a permissive Apache 2.0 License for both personal and commercial use, while the more powerful 9B variant uses a Non-Commercial License intended for research and personal projects. Both models support 11 native aspect ratios ranging from 1:1 square to 21:9 ultrawide and 9:21 vertical, and they can produce sharp images up to 4 megapixels (such as 2048x2048). To make them even more accessible, there are Q (Quantized) models like the FP8 (8-bit) and NVFP4 (4-bit) versions, which reduce the "brain size" of the model to save memory; specifically, the FP8 version is about 1.6x faster and uses 40% less VRAM, while the NVFP4 version is up to 2.7x faster and uses 55% less VRAM. Because of these optimizations, the 4B model can run on systems with as little as 8GB to 12GB of VRAM and can even operate (with the lowest Flux.2 Klein 4B Q2 or Q3 GGUFs) on very low grade 6GB, 4GB, 2GB VRAM GPUs or even on modern integrated graphics (iGPUs) from the latest laptop or mini PC chips.

You need a Hugging Face account to download your necessary files (Details are mentioned below). Make sure you install GGUF addon for ComfyUI using ComfyUI manager or any other missing nodes you may have and place the correct files in correct places. Also check out my other workflows for SD 1.5 + SDXL 1.0, WAN 2.1, WAN 2.2, MagicWAN Image v2, QWEN, HunyuanImage-2.1, HiDream, KREA, Chroma, AuraFlow, Z-Image Turbo and Flux. Feel free to toss some yellow Buzz on stuffs you like.

How to use this -

#1. Just select your desired Flux.2 Klein 4B GGUF (or swap it with full model) models first and now

#2. now select your input character reference image and set the character's first and last name

#3. Now set common Image Dimensions for your dataset (a brief guideline of this is in Workflow's note section)

#4. on next step enter your image editing instructions - Batch character prompts like "subject seen from" and "Make this person" followed by other details. Also add common negative filters or use the existing one provided.

#5. after this select image sampling methods, CFG, steps etc. settings (this part is tricky, if you want you can just have the values as it is)

#6. finally press the run button to generate. That's it..

** I have given multiple .txt files with prompts in the zip file containing this workflow to help you fast pace your dataset building process - one for character poses, one for sfw character prompts, one for nsfw character prompts and one for the selected set of 10 prompts used in this workflow. You can mix and match them but remember if you want to use a set of prompts you have to follow these 3 rules - #1. keep your each prompt short, #2. end each prompt with a dot (.) so don't use dot on the middle of a prompt and #3. Start your new prompt on the very next line, don't keep a line empty.

Enjoy!

Required Files
==================

Flux.2 Klein 4B Models -
-----------------------

### Download Link for Flux.2 Klein 4B GGUF Model used
------------------------------------------------------

https://huggingface.co/unsloth/FLUX.2-klein-4B-GGUF/resolve/main/flux-2-klein-4b-Q8_0.gguf

### Download Link for Flux.2 Klein 4B Text Encoder used
--------------------------------------------------------

https://huggingface.co/Comfy-Org/flux2-klein-4B/resolve/main/split_files/text_encoders/qwen_3_4b.safetensors

### Download Link for Flux.2 Klein 4B VAE used
-----------------------------------------------

https://huggingface.co/Comfy-Org/flux2-dev/resolve/main/split_files/vae/flux2-vae.safetensors
