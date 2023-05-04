# Case Study: Temperature Control System 

The developed  <a href="https://github.com/fereidoun-moradi/RoomTemp/blob/main/OneRoomTemp_Github.rebeca">Timed Rebeca model</a> includes the model of main components of a temperature control system that regulates the temperature of a room. 


<b>System Specification:</b> 

The temperature control system is responsible for maintaining the temperature of a room at a desired range (i.e., the values between 21 and 23). We assume that the temperature of the room is within the desired range at the beginning (i.e., the value 22). This system includes a sensor, a hc\_unit (heating and cooling unit) as an actuator, and a controller. The controller receives sensor data from the sensor and transmits the activatec, activateh or switchoff command to the hc_unit to respectively activate the cooling or heating process, or switch the heating/cooling process off. Assume that there is a window inside the room and the outside air blows inside when the window is open. The temperature of the room is slowly affected by outside air blowing, whether the outside weather is colder or warmer than the current temperature of the room. The values 0, 1, or -1 for the effect of outside air blowing on the room temperature are chosen using nondeterministic assignment. The controller does not know whether the window is open or closed but can activate the heating/cooling process based on the sensed temperature value. The cooling process is activated if the temperature value is higher than the desired range (e.g., the value 24). The heating process is activated if the temperature value is lower than the desired range (e.g., the value 20). The heating/cooling process is switched off if the temperature value is regulated to the desired range.
The physical process is temperature regulation, and the desired states show the temperature value in the range. 
The regulation value is used to control the heating and cooling process through the hc\_unit when it is turned on by the controller.



The Timed Rebca model augmented with attacks. The written safety properties for the system as follows. 

<a href="https://github.com/fereidoun-moradi/RoomTemp/blob/main/TCS_attackmodels.rebeca">Timed Rebeca model</a>

<a href="https://github.com/fereidoun-moradi/RoomTemp/blob/main/TCS_attackmodels.property">Properties</a>


# ltscast tool (maps the State Space to LTS)

![toolset3](https://user-images.githubusercontent.com/45528113/199219377-742ded4c-0063-4347-8961-4504f5b6f01e.jpg)




The <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfunction_variables">cast function</a> maps a state space genrated by Afra model checker to the state space of the mCRL2. 
It outputs the state space in <a href="https://www.mcrl2.org/web/user_manual/language_reference/lts.html#language-aut-lts">aut (Aldebaran) format</a>. The mapped state space can be used as the input file in mCRL2 tool for abstracting the transtion system based on <a href="https://www.mcrl2.org/web/user_manual/tools/release/ltsconvert.html">difference equivalence relationships</a> and a list of silent (tau) transtions.

The <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfunction_variables.lf">source code</a> of the cast function is developted in c++ and compiled by  <a href="https://www.lf-lang.org/download">Lingua Franca (LF)</a> compiler. 

The <a href="https://github.com/fereidoun-moradi/extraction_Function">extraction function</a> generates a list of labels for silent (tau) transtions. 
 

# Example: Temperature Control System (simplified version).
Input state space a <a href="https://github.com/fereidoun-moradi/Abstraction-tool/blob/main/RV-Example.rebeca">Timed Rebeca</a> model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/temp_graph_org.pdf">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/RV-Example.statespace">state space file</a>

The example is a reactive system and its diagram shows that it has recurrent behavior. Each state shows state variables 'temperature', which its value is changed when the action 'tempchange' is executed. The  'time + = 10' denotes that the logical time progresses by 10 units of time. Transitions show the enabled actions at the states and the progress of time. 
The shift equivalence relation exists between states (in blue color in the diagram) and the values of the time shifting are tagged on transitions. The label 'a>>b' indicates that the time value 'a' is shifted by the amount of 'b'.

List of variables:  <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/variables_list">ignore list</a>

LTS: <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfile.aut">aut file</a> (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/temp_graph_LTS.pdf">LTS diagram</a>)

<img width="1152" alt="Screenshot 2023-03-03 at 09 22 10" src="https://user-images.githubusercontent.com/45528113/222669059-1e046e84-7076-4f96-bc9d-a5267f36619a.png">

