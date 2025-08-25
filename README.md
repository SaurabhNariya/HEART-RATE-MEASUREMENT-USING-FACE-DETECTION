# Heart-Rate-Measurement-Using-Camera  

(https://github.com/SaurabhNariya/HEART-RATE-MEASUREMENT-USING-FACE-DETECTION/blob/main/result.png)

## Abstract  
- Heart Rate (HR) is a key physiological parameter and reflects a person’s overall physical state.  
- This project is a **non-contact method** to measure heart rate in real time using only a camera.  
- The basic idea is to extract pulse information from **subtle skin color changes** caused by blood circulation.  
- Possible applications include driver fatigue monitoring, healthcare tracking, and wellness checks.  

## Methodology  
- Detect face, align, and select ROI (Region of Interest) using facial landmarks.  
- Apply a **band-pass filter** with lower bound `0.8 Hz` and upper bound `3 Hz` (≈ 48–180 bpm).  
- Calculate the average color values of the ROI per frame and store them in a buffer (length = 150).  
- Perform FFT on the buffer; the **highest frequency peak corresponds to the heart rate**.  
- Apply Eulerian Video Magnification to visually enhance color fluctuations.  

## Requirements  
pip install -r requirements.txt

## Implementation
python GUI.py

## To plot heart rate graphs:
python graph_plot.py

## To run color amplification:
python amplify_color.py

## Results
* Validation was done using a Compact 5 Econet medical device as ground truth.
* In most stable conditions, the measured HR from the application matches the device reading.

## References
* "Real Time Heart Rate Monitoring From Facial RGB Color Video Using Webcam" – H. Rahman et al.

* "Remote Monitoring of Heart Rate using Multispectral Imaging" – M. Kellman, S. Zikanova, B. Phipps (CMU).

* "Non-contact automated cardiac pulse measurement using video imaging" – M.Z. Poh, D.J. McDuff, R.W. Picard.

* "Camera-based Heart Rate Monitoring" – J.N. Jensen, M. Hannemose.

* Graph plotting adapted from webcam-pulse-detector.

* Facial landmark detection inspired by PyImageSearch tutorial.

## Notes
* Works only for one person at a time.
* Sudden movements may cause wrong HR readings; stable positioning for ~10 seconds gives best results.
* This project is for educational purposes only.

## For queries, contact:
## 📧 Saurabh Nariya – saurabhnariya1234@gmail.com



