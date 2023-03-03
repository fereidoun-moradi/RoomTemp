# Temperature Control System case study

The developed  <a href="https://github.com/fereidoun-moradi/RoomTemp/blob/main/OneRoomTemp_Github.rebeca">Timed Rebeca model</a> includes the model of main components of a temperature control system that regulates the temperature of a room. 
The initial configuration of the system: the desired temprature value in the controller sets to the value 22. The window in the room is close so that the outside cold air does not blow inside. The temprature value is increasing in the room. 

# ltscast tool (maps the State Space to LTS)

![toolset3](https://user-images.githubusercontent.com/45528113/199219377-742ded4c-0063-4347-8961-4504f5b6f01e.jpg)




The <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfunction_variables">cast function</a> maps a state space genrated by Afra model checker to the state space of the mCRL2. 
It outputs the state space in <a href="https://www.mcrl2.org/web/user_manual/language_reference/lts.html#language-aut-lts">aut (Aldebaran) format</a>. The mapped state space can be used as the input file in mCRL2 tool for abstracting the transtion system based on <a href="https://www.mcrl2.org/web/user_manual/tools/release/ltsconvert.html">difference equivalence relationships</a> and a list of silent (tau) transtions.

The <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfunction_variables.lf">source code</a> of the cast function is developted in c++ and compiled by  <a href="https://www.lf-lang.org/download">Lingua Franca (LF)</a> compiler. 

The <a href="https://github.com/fereidoun-moradi/extraction_Function">extraction function</a> generates a list of labels for silent (tau) transtions. 
 

# Example 1: Temperature Control System (simplified version).
Input state space a <a href="https://github.com/fereidoun-moradi/Abstraction-tool/blob/main/RV-Example.rebeca">Timed Rebeca</a> model (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/temp_graph_org.pdf">state dransition diagram</a>): <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/RV-Example.statespace">state space file</a>

The example is a reactive system and its diagram shows that it has recurrent behavior. Each state shows state variables 'temperature', which its value is changed when the action 'tempchange' is executed. The  'time + = 10' denotes that the logical time progresses by 10 units of time. Transitions show the enabled actions at the states and the progress of time. 
The shift equivalence relation exists between states (in blue color in the diagram) and the values of the time shifting are tagged on transitions. The label 'a>>b' indicates that the time value 'a' is shifted by the amount of 'b'.

List of variables:  <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/variables_list">ignore list</a>

LTS: <a href="https://github.com/fereidoun-moradi/cast_function/blob/main/castfile.aut">aut file</a> (<a href="https://github.com/fereidoun-moradi/cast_function/blob/main/temp_graph_LTS.pdf">LTS diagram</a>)

<img width="1152" alt="Screenshot 2023-03-03 at 09 22 10" src="https://user-images.githubusercontent.com/45528113/222669059-1e046e84-7076-4f96-bc9d-a5267f36619a.png">

