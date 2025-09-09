# AUTOMATED-CAR-WASHSER-SYSTEM-DESIGN-USING-SYSTEM-VERILOG


1. Car Wash Controller:
•	This is the core of the system, responsible for controlling and sequencing the washing process.
•	It receives external signals like start and reset from the user.
•	Based on these signals, it activates various stages such as:
o	Water Spray
o	Soap Spray
o	Rinse
o	Dry
o	Finish
•	After initiating each stage, the controller waits for confirmation from the corresponding sensor before proceeding to the next one.

2. Sensors Module:
•	Each stage (Water, Soap, Rinse, etc.) is associated with a specific sensor that detects completion of that operation.
•	These sensors send a State Completion Signal back to the Car Wash Controller, confirming that the step has been executed successfully.
•	If a sensor fails to respond within the expected time limit, it raises an Error Signal to the Error and Timing Controller.

3. Error and Timing Controller:
•	This block continuously monitors whether each operation completes within a predefined time.
•	If any operation exceeds the time limit, or if a sensor fails to respond, it generates an Error Signal.
•	This signal is sent to the Car Wash Controller, prompting it to enter an error handling state.
•	The controller may pause or reset the process based on system logic and the user’s error_reset signal.


