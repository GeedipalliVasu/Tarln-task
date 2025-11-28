📘 AI Text-to-Image Generator (Talrn ML Internship Task)
This project is developed as part of the Talrn Machine Learning Internship Task.
It implements a text-to-image generator using open-source Stable Diffusion models and can run fully in Google Colab with GPU support.

🚀 Features
✅ Text-to-Image Generation
Enter any prompt — the model generates images using Stable Diffusion.

✅ Adjustable Controls
Number of images

Image size

Inference steps

Guidance scale

Negative prompts

✅ Ethical AI Controls
Simple prompt filter for restricted words

Automatic watermark ("AI Generated")

User responsible-use guidelines

✅ Image Export & Metadata
Saves generated images automatically

Metadata includes:

prompt

timestamp

parameters

filename

Export as PNG/JPEG

✅ Fully Open Source
Uses open-source models from Hugging Face and the Diffusers library.

🧠 Technologies Used
Python

Stable Diffusion

Hugging Face Diffusers

Transformers

Accelerate

Xformers (optional GPU optimization)

Google Colab GPU (T4/L4/A100)

⚙️ Setup & Installation (Colab)
You can run the entire project in Google Colab:

1️⃣ Install Dependencies
!pip install diffusers transformers accelerate safetensors huggingface_hub xformers pillow
2️⃣ (Optional) Login to Hugging Face
Required for gated models like SD v1.5.

from huggingface_hub import notebook_login
notebook_login()
3️⃣ Load the Model
The notebook automatically detects GPU/CPU and loads Stable Diffusion.

🎨 Usage
Provide a prompt:
prompt = "A futuristic city at sunset, highly detailed, 4k"
Generate an image:
out = pipe(prompt=prompt, num_inference_steps=25, guidance_scale=7.5)
img = out.images[0]
display(img)
Save results + metadata:
Automatically handled via:

save_with_meta(img, prompt, params)
All images save to:

/outputs/
🛡 Ethical Use Guidelines
Avoid generating violent, explicit, harmful, or illegal content.

This project includes a simple keyword-based filter.

All generated images contain a watermark: “AI Generated”

Use responsibly and comply with model licenses.

📌 Limitations
Image generation speed depends on GPU availability.

CPU mode is extremely slow (not recommended).

First model download takes a few minutes.

Safety checker bypassed in favor of custom filtering (for educational use).

🚧 Future Improvements
Add a full Flask/Streamlit web UI

Add image-to-image generation

Integrate ControlNet for pose/depth/sketch guidance

Add LoRA training for custom styles

Add a database for storing history and user prompts

📞 Contact
If required by Talrn:

Email: your email

Name: your name

Availability: your internship start date
