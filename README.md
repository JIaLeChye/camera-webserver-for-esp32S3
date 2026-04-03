# Esp32 camera webserver for data collection
[ฉบับไทย](https://github.com/San279/camera-webserver-for-esp32S3/blob/master/README-th.md)
<br/>
<br/>
This project is dedicated for collecting images from Esp32S3 to train [FOMO object detection model](https://edge-impulse.gitbook.io/docs/edge-impulse-studio/learning-blocks/object-detection/fomo-object-detection-for-constrained-devices) in [Edge Impulse](https://edgeimpulse.com/). The Hardware that was used were provided by [Wireless Solution Asia](https://wirelesssolution.asia/). Users can collect images from the webserver and download to their computer directly. User can aslo manipulate Esp32S3 camera resolutions and sensors settings. Just unzip the project inside the Arduino directory and you're good to go! 

## What you'll need
- [Arduino IDE](https://www.arduino.cc/en/software), preferably the latest ones, but older versions will still do the job.
- ESP32-S3 is preferable but older version will do just fine.
- OV2640 camera or any OV series. 

## Project files descriptions

1. **camera-webserver-for-esp32S3.ino** - Arduino sketch that handles MJPEG camera streaming and settings API endpoints on the ESP32-S3.
2. **index.html** - HTML structure with responsive panels for live preview, capture controls, image gallery, and camera settings.
3. **index.js** - Core JavaScript logic for stream connection, camera control, image capture/download, and dynamic UI management.
4. **style.css** - Modern responsive styling with desktop-first layout (left-right sections on desktop, stacked on mobile), card-based panels, and theme variables.

## How to Install and run the project

<strong> 1. Download the project and unzip it to your Arduino Directory. </strong>
<br /><br />
<strong> 2. Open camera-webserver-for-esp32S3 directory and launch camera-webserver-for-esp32S3.ino. Enter WIFI SSID and PASSWORD.  </strong>
<br /><br />
<strong> 3. Under tools change your Board to "ESP32S3 Dev Module" and PSRAM to "OPI PSRAM".  </strong>
<br /><br />
<strong> 4. Upload the code to your ESP32S3 and copy the IP address.  </strong>
<br /><br />
<strong> 5. Open index.html file. The page will show a loading screen with an IP input field. Enter the ESP32 IP address and click Connect.  </strong>
<br /><br />
The webserver will connect and start streaming. You don't need to manually paste the IP into the browser anymore!
<br /><br /><br /><br />
<strong> 6. Done!!!  </strong>
<br/> <br/>
<strong> - I've created repository to provide simple guide to training FOMO object detection model please visit [train-FOMO-object-detect-esp32](https://github.com/San279/train-FOMO-object-detect-esp32). </strong>
<br/> <br/>
## Webserver features
- **Desktop-friendly layout**: Modern side-by-side design with live stream on the left and controls on the right. Responsive design adapts beautifully to mobile devices.<br />
- **Smart IP management**: Enter and change the ESP32 IP address directly from the loading screen or main page. No browser prompts needed. Simply update the IP and click Connect anytime.<br />
- **Real-time connection status**: Visual feedback shows connection state (Connecting, Connected, Invalid IP or CORS blocked) without blocking popups.<br />
- User can switch languages on the top right corner of the web (English / ไทย).<br />
- **Resolution-responsive video**: Video frame automatically scales to match your selected camera resolution for optimal viewing.<br />
- Adjustable Camera Settings, to see more details about each setting please visit [
https://heyrick.eu/blog/index.php?diary=20210418&keitai=0](https://heyrick.eu/blog/index.php?diary=20210418&keitai=0).<br />
- User can hide the setting console by clicking on the settings icon in the top bar.<br />
- **Adjustable Resolutions**: Choose from 13 different resolution options (96×96 to 1280×1024).<br />
- **Class labels**: Assign a name to each captured image set for easy organization and labeling.<br />
- **Capture controls**: Start capturing images with the Capture button. Set capture intervals (minimum 0.1 seconds) and limit total images with Instances.<br /> 
- Download button will zip all captured images into a single file for easy batch downloading.<br />
- Clear button will delete all captured images at once.<br />
- Delete individual images by clicking the X on each thumbnail.<br /><br />
![alt_text](/Images_for_readme/capture_console.PNG)
<br /><br /> <br />
- **Image Gallery**: View and manage all captured images in the gallery panel.<br /><br />
![alt_text](/Images_for_readme/gallery_img.PNG)
<br /> <br /><br /> <br />
## Credit
Thanks to [WIRELESS SOLUTION ASIA CO.,LTD](https://wirelesssolution.asia/) for providing AIOT board to support this project. Also thanks to [RandomNerdTutorials]([RandomNerdTutorial](https://RandomNerdTutorials.com/esp32-cam-video-streaming-web-server-camera-home-assistant) for providing essential codes for streaming Esp32 camera to webserver.
