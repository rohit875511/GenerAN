# GenerAN
The goal of this project was to fine-tune Tooncrafter's model to produce more realistic and smooth facial expressions. GenerAN is currently being marketed commercially, and has recieved written forms of interest from multiple animation studios. GenerAN generates the in-between frames for a given input and output frame.

For parties interest in beta-testing or purchase contact: rohitnsundaram@gmail.com

## Product Video:
[![Watch Demo](https://img.youtube.com/vi/-GBcWIkIFp4/0.jpg)](https://youtu.be/-GBcWIkIFp4)

Link: https://youtu.be/-GBcWIkIFp4

Try out Tooncrafter's model here: https://replicate.com/fofr/tooncrafter

## Data Collection

Base # of clips gathered: ~1200

Clip lengths: ~2 seconds (~48 frames at 24 fps)

Resolution: 256×256 or 512×320

Subjects: diverse facial expressions, head poses, and lighting conditions

Emotions: neutral, happy, sad, angry, surprised, fear, disgust

Mouth/phonemes: A/E/I/O/U, M/B/P, F/V, L/Th

Eye/brow movements: blinks, raises, squints

## Landmark and Emotion Annotation

Each frame was annotated using MediaPipe's Face Landmarker, and each clip designated an emotion label. 

<img width="1000" height="551" alt="Emotion = ‘happy’" src="https://github.com/user-attachments/assets/76cb6997-193a-4717-af5f-bd891e5655c8" />

Landmarks and emotion were stored alongside frame in this format:

{
  "clip_id": "clip01",
  
  "start_frame": "frame_0001.png",
  
  "end_frame": "frame_0048.png",
  
  "middle_frames": ["frame_0002.png", ..., "frame_0047.png"],
  
  "landmarks": {...},
  
  "emotion": {...}
}
## Data Augmentation

Utilizing data augmentation techniques the previous # of training examples increased to ~8,500 clips. 

### Spatial Augmentation

Horizontal flip: mirrors the face, simulating left/right motion.

Rotation ±5°: slight head tilts to capture natural variation.

Random crop / zoom ±5–10%: simulates minor framing changes and ensures model learns robust face representation.

### Photometric Augmentation

Brightness ±20%: mimics different lighting conditions.

Saturation ±5–10%: simulates subtle color variations across clips.

Mild Gaussian blur: adds small visual imperfections.

### Temporal Augmentation

Playback speed 0.9× / 1.1×: simulates slightly slower or faster motion.

Frame skipping (drop 1–2 frames)

Temporal cropping: slightly shifts start/end points for variety.

## License

This dataset and pipeline are released under the **Apache License 2.0**, which allows commercial use, modification, and distribution, provided proper attribution is given and license notices are preserved.

- Original ToonCrafter license: [Apache 2.0](http://www.apache.org/licenses/LICENSE-2.0)
- This work is based on ToonCrafter by **Tencent**, with dataset modifications to improve facial expression generation.
- Full license text is included in the `LICENSE` file.



