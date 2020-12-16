#### Known Issues:

* `[Err] [REST.cc:205] Error in REST request` - this is a known error
    in Gazebo 9. To fix it, edit `~/.ignition/fuel/config.yaml` and
    change the server URL in there from https://api.ignitionfuel.org
    to https://api.ignitionrobotics.org
* `Couldn't open joystick force feedback!` - this error is non-fatal
    and can be ignored. It's a common error in the `joystick_drivers`
    node

## Controlling the Robot
### Joystick
The robot supports the generic Linux
[joystick](http://wiki.ros.org/joy) controllers. The `sd_control`
package contains a node to turn joystick commands into control
messages that drive the throttle and steering of the model. To use
this, launch a simulation as described above, then run the following:
```
roslaunch sd_control sd_twizy_control_teleop.launch
```

You can map specific buttons using the parameters defined in that
launch file. For instance, the following uses the left stick for
throttle, the right stick for steering, and right button (RB) to
enable control on a Logitech F710 Gamepad:
```
roslaunch sd_control sd_twizy_control_teleop.launch enable_button:=5 throttle_axis:=1 steer_axis:=2
```
## sd_bringup
sd_bringup is aangepast voor Google Cartographer

## Cartographer_ROS
Voor simulatie van google cartographer met ROS moet je de instructies van Google Cartographer volgen  https://google-cartographer-ros.readthedocs.io/en/latest/compilation.html

# De twizy2D.lua bestand hoort in src/cartographer_ros/cartographer_ros/configuration_files te zitten.
De cofiguratie binnen twizy2d.lua zijn gepersonaliseerd voor mijn computer,

Verander zo nodig de refresh rate en sample rate als het te traag of als je computer meer aan kan.

Als je computer toch nog te traag is kan je ook aan de minimum range en maximum range zitten van de velodyne VLP-16 LIDAR sensor.



