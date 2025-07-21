---

---
---
**features:**
- real-time video streaming on webapp
- violation reporting w/ date time & location logging
- vehicle speed prediction
- licence plate Optical Character Recognition
- Vehicle Horn detection

	**A violation is characterized by:**
	1. vehicle speeding (speed > 10 kph)
	2. excessive usage of horn (more than 5 horns in 10 secs)
	
	**When a violation is detected, these are reported:**
	3. type of violation (speeding or horn usage)
	4. if type = horn: number of times horn was used 
	5. if type = speeding: vehicle speed estimate
	6. vehicle license plate reading
	7. photo of vehicle used for OCR licence plate reading 
	8. location, date & time data derived from placement of camera
	
	**violations are stored in a mongodb database.**

**constraints:**
- YOLO model will have to be continually running in order to  calculate all detected vehicles speeds.
- Once a car is detected for speeding or Horn abuse, use the last and future n frames to check for license plate via OCR.
	- ex. speeding detected at frame 12 and n=10
	- frames 2 - 22 will be processed by OCR to check for license plate.
	- higher n values result in more chances to detect plate, but will be proportionally slower.
- Horn detection cannot identify source of sound.
- Horn events are identified as any sharp & high-pitched noise.
- Camera placement is crucial for accurate speed prediction and license plate reading.

**approach:**
*Detection & Violation Logging*
- Integrate RTSP video capture from camera   
- Run YOLO model for vehicle detection
- Implement speed calculation w/ pixel tracking method as a fallback in case model doesn't support speed calculations.
- Use OCR to recognize plates
- Save violation data + image to disk/db
*Horn Detection*
- Connect camera Audio to Pi
- Process audio in 10s windows
- Detect high-energy peaks as horn events
*Web Interface*
- Live stream via Flask/React (MJPEG)
- Dashboard to view violations (table + thumbnails)

example violation:

{
  "violation_id": "MLBY-010",
  "timestamp": "2025-04-11T15:55:00Z",
  "location": "Rubiato compound",
  "type": "speeding"
  "vehicle_speed": 700.4,
  "horn_count": 420,
  "plate_number": "NEED4SPEED",
  "image_path": "images/violation_123.jpg"
}

creds:
`RoadsenseAdmin`
`RoadSense`
`roadsense@roadsense.local`

camera => YOLO model => backend service => frontend

model: YOLO11n
Precision: F32
format: ONNX

services
1. yolo processor for:
	1. car speeds /
	2. license plates
	3. storing json data,license plate (if recognized) & frame at time of report /
2. report and image uploader /
3. mtx stream http endpoint provider 


play rtsp stream: `ffplay -rtsp_transport udp "rtsp://RoadsenseAdmin:RoadSense@192.168.1.25:554/stream1"`
