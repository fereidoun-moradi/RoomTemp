# Temperature Control System

# Timed Rebeca
The developed  <a href="https://github.com/fereidoun-moradi/RoomTemp/blob/main/OneRoomTemp_Github.rebeca">Timed Rebeca model</a> includes the model of main components of a temperature control system that regulates the temperature of a room. The <a href="https://github.com/fereidoun-moradi/RoomTemp/blob/main/OneRoomTemp_Github.jpg">state transition diagram</a> of the model shows the states and transitions. 

The initial configuration of the system: the desired temprature value in the controller sets to the value 21 and the window is close so that the outside cold air does not blow inside. The temprature is increased in the room. 

# Abstraction
Abstraction tool is used to abstract the state-space generated by Afra model checker. 
Input lists of variables: <a href="https://github.com/fereidoun-moradi/RoomTemp/blob/main/inputVar.txt">variables</a>

Abstracted version of the input state-space (<a href="https://github.com/fereidoun-moradi/RoomTemp/blob/main/miniModel.png">state transition diagram</a>): <a href="https://github.com/fereidoun-moradi/RoomTemp/blob/main/miniModel.statespace">Tiny Twin</a>

# Lingua Franca
Lingua Franca programing language is used to develop an executable file. The <a href="https://github.com/fereidoun-moradi/RoomTemp/blob/main/Temperature_Control_System.lf">code</a> is compiled by Lingua Franca compiler.
The code <a href="https://github.com/fereidoun-moradi/RoomTemp/blob/main/RoomTemp_Monitor_compSensor.jpeg">diagram</a> shows the reactors and the reactions.
