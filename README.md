# webot
soccer bot


Webots is a free and open-source 3D robot simulator used in industry, education and research. The Webots project started in 1996, initially developed by Dr. Olivier Michel at the Swiss Federal Institute of Technology in Lausanne, Switzerland and then from 1998 by Cyberbotics Ltd. as a proprietary licensed software

Webots includes a large collection of freely modifiable models of robots, sensors, actuators and objects. In addition, it is also possible to build new models from scratch or import them from 3D CAD software. When designing a robot model, the user specifies both the graphical and the physical properties of the objects. The graphical properties include the shape, dimensions, position and orientation, colors, and texture of the object. The physical properties include the mass, friction factor, as well as the spring and damping constants. Simple fluid dynamics is present in the software.

The Ball's size, mass and color correspond to the soccer ball used in the Robocup SPL. You can change the centerOfMass to [0 0 0] to avoid the random rolling effect.

#Ball

Ball {
  SFVec3f    translation     0 0 0
  SFRotation rotation        0 0 1 0
  SFString   name            "ball"
  SFColor    color           1.0 0.54 0.08
  SFFloat    radius          0.0325
  SFFloat    mass            0.055
  MFVec3f    centerOfMass    [0 -0.0001 0]
  SFFloat    linearDamping   0.17
  SFFloat    angularDamping  0.33
  SFString   contactMaterial "default"
}

RobotstadiumSoccerField
Robot soccer field inspired from the RoboCup 2014 Standard Platform League. The soccer field is built on a total carpet area of length 10.4 m and width 7.4 m. The field dimensions (within the white lines) are 9 x 6 m.

#RobotstadiumSoccerField

RobotstadiumSoccerField {
  SFVec3f    translation     0 0 0
  SFRotation rotation        0 1 0 0
  SFString   name            "robotstadium soccer field"
  SFString   contactMaterial "default"
  SFColor    frame1Color     1 1 1
  SFColor    frame2Color     1 1 1
  SFFloat    postRadius      0.05
}

#Robot

Robot {
  SFString controller      "void"   # any string
  MFString controllerArgs  []       # any string
  SFString customData      ""       # any string
  SFBool   supervisor      FALSE    # {TRUE, FALSE}
  SFBool   synchronization TRUE     # {TRUE, FALSE}
  MFFloat  battery         []       # see below
  SFFloat  cpuConsumption  10       # [0, inf)
  SFBool   selfCollision   FALSE    # {TRUE, FALSE}
  SFBool   showWindow      FALSE    # {TRUE, FALSE}
  SFString window          ""       # any string
  SFString remoteControl   ""       # any string
}
