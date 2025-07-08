# STREET-SURVEILLANCE
Street surveillance using artificial intelligence and YOLOv12 for object detection.

## Goals
- Determine if there are people at the pedestrian crossing.
- Detect cars approaching the pedestrian crossing.
- Count the number of cars in the parking lot.
- Count the number of people who have crossed the pedestrian crossing.

## Data Collection
- Photographs were captured from a live camera feed at 12-minute intervals.
- A total of 876 images were collected over 10 days.

## Annotation of Photos
- Each image was annotated for two object classes: cars and people.

## Limitations
- Supports only a single camera.
- Performance degrades in poor weather conditions.

## Practical Applications
- Enhanced pedestrian safety at crosswalks with poor visibility.
- Integration with autonomous vehicles for improved traffic assessment.
- Parking availability insights via a mobile app.

## Demonstration
![Snapshot of detection](https://github.com/Friebay/STREET-SURVEILLANCE/blob/main/Demonstration/fbap4Zm.png?raw=true)
![Animated demo](https://github.com/Friebay/STREET-SURVEILLANCE/blob/main/Demonstration/8mb.video-7oM-RFZteKvn.gif?raw=true)

## Model Performance Analysis

![Confusion Matrix](https://github.com/Friebay/STREET-SURVEILLANCE/blob/main/confusion_matrix_normalized.png?raw=true)

### Car Detection (True Car Column):

- 96% of actual cars are correctly predicted as 'Car'. This is a very strong performance, indicating the model is highly effective at identifying cars when they are present.

- Only 4% of actual cars are misclassified as 'background'.

### Human Detection (True Human Column):

- Only 50% (0.50) of actual humans are correctly predicted as 'Human'. This is a significant weakness.

- A substantial 49% (0.49) of actual humans are misclassified as 'background'. This means nearly half of the people are being missed by the system.

### Background Classification (True background Column):

- 55% (0.55) of what is truly background is correctly identified as 'background'.

- A significant portion, 45% (0.45), of the actual background is incorrectly predicted as 'Car'.

## Setup and Installation

### Quick Start

1. **Clone the repository**
   ```bash
   git clone https://github.com/Friebay/STREET-SURVEILLANCE.git
   cd STREET-SURVEILLANCE
   ```

2. **Create and activate virtual environment**
   
   **Windows (Command Prompt):**
   ```cmd
   python -m venv yolov12_env
   yolov12_env\Scripts\activate.bat
   ```

3. **Install dependencies**
   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

4. **Set up environment variables**

   - Visit your [Roboflow API Settings](https://app.roboflow.com/settings/api) and copy your private API key.
   - Create a `.env` file in the project root and add your key:

   ```bash
   echo ROBOFLOW_API_KEY=your_api_key_here > .env
   ```

5. **Launch Jupyter Notebook**

   ```bash
   jupyter notebook
   ```

   Then, open `train_yolov12_object_detection_model.ipynb` in your browser and follow the steps inside the notebook.