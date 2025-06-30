
# Audio-Only Emotion Recognition using MFCC and Deep Learning

This project performs emotion recognition from speech audio using Mel Frequency Cepstral Coefficients (MFCCs) and a neural network classifier. It is trained and evaluated using the RAVDESS dataset.

---

## Features

- Records or uploads audio and predicts emotion in real-time
- Extracts MFCC features with padding for consistent model input
- Batch prediction for folders of .wav files
- Smart preprocessing caching to avoid redundant computations
- Evaluation using classification report
- Trained on RAVDESS dataset with emotions like happy, angry, sad, etc.

---

## Project Structure

audio_emotion_recognition/
 AudioOnly_Emotion_Recognition.ipynb     
 data/
    mfcc_data.pkl                          
 README.md                               
 audio/                         
 requirements.txt               

---

## Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
```

Minimal list:
```bash
pip install numpy librosa sounddevice scikit-learn torch torchaudio matplotlib
```

If using Gradio for GUI:

```bash
pip install gradio
```

---

## How It Works

### 1. Preprocessing

- Loads .wav files from data/raw/audio/
- Extracts MFCCs (40 coefficients) from each file
- Pads/truncates to 150 frames to ensure consistent size
- Saves X, y, and LabelEncoder to mfcc_data.pkl

### 2. Model Training

- You can define a simple CNN or LSTM model
- Trained with encoded emotion labels
- Model is saved as model.pth

### 3. Emotion Prediction

- Use microphone input (sounddevice) or a file
- Pass through the trained model
- Output the predicted emotion

---

## Example Output

Recording...
Recording saved. Predicting...
Predicted Emotion: angry

---

## Supported Emotions

| Code | Emotion   |
|------|-----------|
| 01   | neutral   |
| 02   | calm      |
| 03   | happy     |
| 04   | sad       |
| 05   | angry     |
| 06   | fearful   |
| 07   | disgust   |
| 08   | surprised |

---

## Future Improvements

- Add spectrogram-based CNN model
- Use GRU/LSTM for temporal modeling
- Integrate with web UI via Gradio or Streamlit
- Combine audio + video for multi-modal analysis

---
## Note

- **Please use your input and output folder path instead of all paths specified in the code

---

## Credits

- Dataset: RAVDESS - Ryerson Audio-Visual Database of Emotional Speech and Song (Audio only)
- Built using Python, PyTorch, Librosa, and SoundDevice

---

## License

This project is open-source and free to use under the MIT License.
