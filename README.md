# PRODIGY_GA_02: Image Generation with Pre-trained Models

## Overview

**PRODIGY_GA_02** is an ongoing project at **Prodigy**, focused on leveraging **Generative AI** to create images from text prompts. This project demonstrates the power of pre-trained generative models like **DALL-E-mini** and **Stable Diffusion** to generate high-quality, creative images from simple textual descriptions. By exploring these models, the project showcases how AI can enhance the creative process and provide innovative tools for content creation, design, and more.

## Table of Contents

1. [Project Description](#project-description)
2. [Getting Started](#getting-started)
3. [Installation](#installation)
4. [Usage](#usage)
5. [Examples](#examples)
6. [Project Features](#project-features)
7. [Contributing](#contributing)
8. [License](#license)
9. [Contact](#contact)

## Project Description

**PRODIGY_GA_02** focuses on utilizing pre-trained generative models like **DALL-E-mini** and **Stable Diffusion** to convert textual descriptions into images. The project leverages the `diffusers` and `transformers` libraries to harness the power of these AI models, enabling the generation of diverse and high-quality images based on simple prompts.

---

## Getting Started

To get started with this project, follow these steps to set up the environment and run the image generation code. This can be done either locally or in a cloud environment like Google Colab, which provides easy GPU support.

### Prerequisites

1. Python 3.x
2. GPU (Recommended for faster processing)

### Installing Dependencies

Install the required libraries by running the following command:

```bash
pip install diffusers transformers accelerate scipy ftfy
```

In Google Colab, ensure that you select **GPU** as the hardware accelerator under **Runtime > Change runtime type** for faster processing.

---

## Installation

Before running the code, make sure you have the necessary libraries installed. You can install them using `pip`:

```bash
pip install diffusers transformers accelerate scipy ftfy
```

---

## Usage

### Step-by-Step Instructions

1. **Import Libraries**

Import the required libraries for image generation:

```python
from diffusers import StableDiffusionPipeline
import torch
from IPython.display import display
```

2. **Load the Model**

Load the pre-trained **Stable Diffusion** model. If you have a GPU available, it will speed up the image generation process:

```python
# Check if a GPU is available
if torch.cuda.is_available():
    device = "cuda"
else:
    device = "cpu"

# Load the pre-trained model
pipe = StableDiffusionPipeline.from_pretrained("runwayml/stable-diffusion-v1-5")
pipe = pipe.to(device)
```

3. **Generate Images**

Define your text prompt and generate the corresponding image:

```python
# Define your text prompt
prompt = "Your text prompt here"

# Generate the image
image = pipe(prompt).images[0]

# Display the generated image
display(image)
```

4. **Save Images**

You can save and download the generated image:

```python
# Save the generated image
image.save("image_name.png")

# Download the image
from google.colab import files
files.download("image_name.png")
```

---

## Examples

Here are a few example prompts you can use to generate images:

- "A futuristic cityscape with flying cars and neon lights at night."
- "Donald Trump and Elon Musk drinking breakfast together."
- "Elon Musk in his spaceship, Starship."
- "Father Christmas giving a live chicken to a smiling boy child."

Feel free to experiment with your own prompts to explore different visual concepts!

---

## Project Features

- **Pre-trained Models**: Utilizes powerful pre-trained models like **DALL-E-mini** and **Stable Diffusion** to generate images.
- **Text-to-Image Conversion**: Allows for the creation of images based on simple text descriptions.
- **Easy-to-Use**: Code is optimized for ease of use, especially in Google Colab with GPU support for faster results.
- **Open-Source**: This project is open for contributions, improvements, and collaboration.

---

## Notes

- This project uses the **`diffusers`** and **`transformers`** libraries for image generation.
- A stable internet connection is required to download the pre-trained models.
- The code is optimized for running in **Google Colab** with GPU acceleration. If you're running the code locally, make sure to adjust the `device` variable to match your environment.

---

## Contributing

Contributions are welcome! If you'd like to improve this project, feel free to fork the repository and submit a pull request. Some ways you can contribute:

- Add new features or improve existing functionality.
- Enhance the documentation.
- Report any issues or bugs you encounter.

Open an issue or submit a pull request for any improvements.

---

## License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## Contact

For any questions or inquiries, feel free to reach out to me:

- **Email**: [nsidibedaniel62@gmail.com](mailto:nsidibedaniel62@gmail.com)
- **LinkedIn**: [Nsidibe Daniel Essang](https://www.linkedin.com/in/nsidibe-essang-142778204/)
