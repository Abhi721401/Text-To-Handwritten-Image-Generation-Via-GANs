# Text-To-Handwritten-Image-Generation-Via-GANs

### User uploads their handwritten picture and a text paragraph , and our model converts it to user handwritten image

### Project Goal:
Build a model that can learn a person's handwriting style from a few image samples and then generate any paragraph in the same handwriting.
This is similar to capabilities showcased in Google Nano Banana Pro, but implemented using open-source datasets and PyTorch.

The system is trained on the IAM Handwriting Dataset and uses a combination of:

A Style Encoder to capture the writer’s stroke characteristics

A Text Encoder to understand the target text

A Conditional GAN to synthesize realistic handwritten word images

A Paragraph Renderer to stitch words into clean paragraphs

A Gradio Web Interface for real-time usage

### Dataset:
This project uses the IAM Handwriting Words Dataset, which includes thousands of handwritten words along with their corresponding text labels.

The model learns:

stroke patterns

writer variations

character shapes

letter spacing

word alignment

### Model Architecture
# 1. Style Encoder (CNN)
Extracts writer-specific features:
slant
sharpness
stroke width
spacing patterns

# 2. Text Encoder (GRU)
Encodes each word as a dense vector representing its character sequence.

# 3. Generator (Conditional GAN)
Produces 64×256 grayscale handwritten word images.

# 4. Discriminator (Projection-Based)
Ensures outputs:
match text
match writer style
appear realistic

### Training Summary:
The model is trained on ~37k valid IAM word images.

# Signals used:

Adversarial Loss (real vs fake)

L1 Reconstruction Loss (stabilizes learning)

Conditional Projection Loss (style matching)

# Training progresses from:

blurry shapes (epochs 1–10)

readable characters (epochs 20–40)

clean, stylistic handwriting (epochs 60–120)

We can increase the number of epoch to get better results
