# Deepfake Detection With CNN

This repository provides a deepfake detection tool that identifies whether an input face image is real or fake. The tool uses a pre-trained InceptionResnetV1 model and Grad-CAM to visualize the regions in the image contributing to the prediction. A user-friendly interface is implemented using [Gradio](https://gradio.app/).

## Features

- **Deepfake Detection**: Classifies images as either "real" or "fake" with confidence scores.
- **Explainability**: Visualizes the important regions of the input image influencing the prediction using Grad-CAM.
- **Interactive Interface**: Gradio-based UI for seamless user interaction.
- **Pre-loaded Examples**: Includes example images to test the tool.

## Installation

### Prerequisites

- Python 3.8 or later
- PyTorch (with GPU support recommended for better performance)

### Steps

1. Clone the repository:
    ```bash
    git clone <repository-url>
    cd <repository-folder>
    ```

2. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Ensure you have the pre-trained weights (`resnetinceptionv1_epoch_32.pth`) and example images (`examples.zip`) in the root directory.

4. Extract the example images:
    ```bash
    unzip examples.zip -d examples
    ```

## Usage

Run the application using:
```bash
python deepfake_predictor.py
```

The Gradio interface will launch, and you can access it in your browser. You can:

- Upload an image to detect if it's real or fake.
- View the explainability map overlaid on the face image.
- Test the tool with pre-loaded example images.

## File Structure

- `deepfake_predictor.py`: Main script to run the detection tool.
- `examples.zip`: Contains sample images for testing.
- `resnetinceptionv1_epoch_32.pth`: Pre-trained model weights.
- `requirements.txt`: Python dependencies for the project.

## Model Details

- **Architecture**: InceptionResnetV1 (pre-trained on VGGFace2).
- **Detection Mechanism**:
  - The face is detected and cropped using MTCNN.
  - Grad-CAM is applied to highlight areas in the image that influence the prediction.

## Examples

- Input an image of a face.
- The output includes:
  - Prediction (Real or Fake) with confidence scores.
  - Visualization of important regions contributing to the decision.

## Dependencies

- `torch`
- `torchvision`
- `facenet-pytorch`
- `pytorch-grad-cam`
- `numpy`
- `Pillow`
- `opencv-python`
- `gradio`

Install these dependencies using:
```bash
pip install torch torchvision facenet-pytorch pytorch-grad-cam numpy Pillow opencv-python gradio
```

## License

This project is licensed under the MIT License. See the LICENSE file for more details.

## Acknowledgments

- [Facenet-PyTorch](https://github.com/timesler/facenet-pytorch)
- [Grad-CAM](https://github.com/jacobgil/pytorch-grad-cam)
- [Gradio](https://gradio.app/)

Feel free to contribute to this project by submitting issues or pull requests!

