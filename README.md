# Handwritten Multi-Digit Recognition Using Deep Learning

A CNN-based system that recognizes handwritten multi-digit numbers with automatic segmentation and real-time prediction.

## Overview

This project extends traditional single-digit recognition to handle complete multi-digit numbers. Instead of just recognizing a "2" or an "8", it can look at your drawing of "28" and correctly identify it as twenty-eight, not just two separate digits.

The system uses a convolutional neural network trained on MNIST data, combined with computer vision techniques for automatic digit segmentation.

## Features

- **Single digit recognition** with 98%+ accuracy
- **Multi-digit number recognition** (supports 1-6 digits)
- **Automatic digit segmentation** using contour detection
- **Real-time drawing interface** with instant predictions
- **Confidence scoring** for each individual digit
- **Left-to-right digit ordering** preservation

## How It Works

1. **Draw** your number on the canvas
2. **Segmentation** algorithm finds individual digit boundaries
3. **CNN model** predicts each digit separately
4. **Assembly** combines predictions into the final number

The trickiest part was getting the segmentation right - separating touching digits while maintaining the correct reading order.

## Tech Stack

- **TensorFlow/Keras** - Neural network framework
- **OpenCV** - Image processing and segmentation
- **tkinter** - GUI interface
- **NumPy** - Numerical computations
- **PIL** - Image handling
- **Matplotlib** - Visualization

## Model Architecture

6-layer CNN with:

- Convolutional layers with ReLU activation
- Max pooling for dimensionality reduction
- Dropout layers for regularization
- Dense layers for final classification
- Softmax output for probability distribution

## Performance

- **Training accuracy**: ~99%
- **Test accuracy**: ~98.5%
- **Prediction speed**: <100ms
- **Supported range**: 1-6 digit numbers

## Installation

```bash
pip install tensorflow opencv-python pillow numpy matplotlib tkinter
```

## Usage

Run the main python notebook:

This opens a drawing interface where you can:

- Draw single digits or multi-digit numbers
- See real-time predictions
- View confidence scores for each digit
- Clear and redraw as needed

## Files

- `analysis.ipynb` - Data exploration and model training
- `mnist_model.h5` - Trained CNN model weights

## Challenges Solved

**Digit Segmentation**: Used contour detection and morphological operations to separate individual digits from connected drawings.

**Order Preservation**: Implemented left-to-right sorting to maintain correct digit sequence (crucial for multi-digit numbers).

**Preprocessing Pipeline**: Created robust image preprocessing to handle various handwriting styles and spacing patterns.

## Applications

This system could be adapted for:

- Postal code recognition systems
- Check processing automation
- Digital form processing
- Educational handwriting tools
- Accessibility applications

## What I Learned

Working on this project taught me about:

- CNN architecture design and hyperparameter tuning
- Computer vision preprocessing techniques
- Real-time image processing pipelines
- Building user-friendly ML interfaces
- Handling edge cases in digit segmentation

## Future Improvements

- Support for more complex mathematical expressions
- Better handling of overlapping digits
- Mobile app version
- Support for different handwriting styles and languages

---

Built as a learning project to explore computer vision and deep learning concepts. The jump from single-digit to multi-digit recognition involved solving interesting challenges in automatic segmentation and sequence processing.
