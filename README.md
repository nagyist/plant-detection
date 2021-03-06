# plant-detection
Detects and marks green plants in a (not green) soil area image using Python OpenCV.

The goal is to mark unwanted volunteer plants for removal.

__Install OpenCV on Debian:__
```
sudo apt-get install python-opencv python-numpy python-picamera
```
__Run the script:__

Download an image of soil with plants in it and save it as `soil_image.jpg` or use the sample.

Run the script: `python Plant_Detection.py`

View `soil_image_marked.jpg`

__Alternatively, process images using a python command line:__
```python
from Plant_Detection import Plant_Detection
help(Plant_Detection)
PD = Plant_Detection(image='soil_image.jpg')
PD.calibrate()
PD.detect_plants()
PD = Plant_Detection(image='soil_image.jpg', morph=15, iterations=2, debug=True)
PD.detect_plants()
```

__Or, run the GUI and move the sliders:__
```python
python Plant_Detection_GUI.py
```
Default image to process is `soil_image.jpg`. To process other images, use:
```python
python Plant_Detection_GUI.py other_image_name.png
```
![plant detection gui screenshot](https://cloud.githubusercontent.com/assets/12681652/15620382/b7f31dd6-240e-11e6-853f-356d1a90376e.png)

## Image file processing suggested workflow

#### Save image to be processed
For example: `test_image.jpg`
#### Run the GUI and move the sliders:
```python
python Plant_Detection_GUI.py test_image.jpg
```
This will create a plant detection parameters input file from the slider values.
#### Enter a python command line: `python`
```python
from Plant_Detection import Plant_Detection
PD = Plant_Detection(image='test_image.jpg', parameters_from_file=True)
PD.detect_plants()
```
#### View output
Annotated image: `test_image_marked.png`
