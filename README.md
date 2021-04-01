# Burglar Alarm ESP32Cam

<p>
In this type of design, an attempt has been made to don't use IP static to transfer information. 
</p>
<p>
The purpose of eliminating static IP is to lower the cost to the user and also to have a machine learning on the server side to continue the project. 
<br />
The manufacturer of this device can also earn money through the sale of the Internet and other services.
</p>

<p>
The next phase of the project is on movement and face recognition.
</p>

<p>
  * It should be noted that the above module is only for demos and for large projects need a more powerful module in terms of camera power and sending images online.
 </p> 
 
 <p>
 The way this device works is that by using this module, it receives a warning information from the server and then the camera turns on and starts sending photos frame by frame to the server.
 </p>
 
<p>I use <a href="https://code.visualstudio.com/">VS Code</a> and <a href="https://platformio.org/">PlatformIO</a> for develop.</p>
<p>PlatformIO was a sweet experience to develop microcontrollers</p>

<p>Required device : </p>
<ul>
<li>ESP32-CAM</li>
<li>USB to serial FT232RL-FTDI</li>
</ul>

![ESP32-CAM-Pic](https://user-images.githubusercontent.com/22281772/112893911-800fc500-90f0-11eb-8063-d7b0d0c151b3.png)

<p>&nbsp;</p>
<table style="height: 292px; width: 244px;">
<tbody>
<tr style="background-color: #fcc89f; height: 62px;">
<td style="width: 111px; text-align: center; height: 62px;">&nbsp;ESP32-CAM</td>
<td style="width: 117px; text-align: center; height: 62px;">&nbsp;USB to serial FT232RL-FTDI</td>
</tr>
<tr style="height: 49px;">
<td style="width: 111px; text-align: center; height: 49px;">&nbsp;3V3</td>
<td style="width: 117px; text-align: center; height: 49px;">&nbsp;VCC</td>
</tr>
<tr style="height: 49px;">
<td style="width: 111px; text-align: center; height: 49px;">GND</td>
<td style="width: 117px; text-align: center; height: 49px;">GND</td>
</tr>
<tr style="height: 49px;">
<td style="width: 111px; text-align: center; height: 49px;">&nbsp;UOR</td>
<td style="width: 117px; text-align: center; height: 49px;">TX</td>
</tr>
<tr style="height: 49px;">
<td style="width: 111px; text-align: center; height: 49px;">&nbsp;UOT</td>
<td style="width: 117px; text-align: center; height: 49px;">RX</td>
</tr>
</tbody>
</table>

![ESP32-CAM](https://user-images.githubusercontent.com/22281772/112893971-8dc54a80-90f0-11eb-89ff-90f0ac09a8e6.png)

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

<p>
<b>Add this librarys</b>
  </p>
<pre>
<code>
  HTTPClient
  WiFiClientSecure
  WiFi
  ArduinoJson
</code>
</pre>
