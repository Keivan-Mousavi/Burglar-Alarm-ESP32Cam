# Burglar Alarm ESP32Cam

In this type of design, an attempt has been made to don't use IP static to transfer information. 

The purpose of eliminating static IP is to lower the cost to the user and also to have a machine learning on the server side to continue the project.

<p>I use <a href="https://code.visualstudio.com/">VS Code</a> and <a href="https://platformio.org/">PlatformIO</a> for develop.</p>
<p>PlatformIO was a sweet experience to develop microcontrollers</p>

<p>
![ESP32-CAM-Pic](https://user-images.githubusercontent.com/22281772/112893911-800fc500-90f0-11eb-8063-d7b0d0c151b3.png)
</p>


<p>
  <b>PlatformIO.ini</b>
</p>
<pre>
<code>
  [env:esp-wrover-kit]
  platform = espressif32
  board = esp-wrover-kit
  framework = arduino
  monitor_speed = 115200
  build_flags = -DCORE_DEBUG_LEVEL=0 -DBOARD_HAS_PSRAM -mfix-esp32-psram-cache-issue
  board_build.f_flash = 80000000L
  board_build.flash_mode = qio
  board_build.partitions = huge_app.csv
</code>
</pre>
