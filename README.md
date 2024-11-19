Release Notes: 

Cobra Thermal System Version 3 Architecture   

07/28/2024 

Key Features and Improvements 

The cobra code has been reorganized to hold more settings and quickly add new features without causing more bugs. Instead of one large configuration file each head gets its own folder of configuration files and the compressor(s) get their own files as well. 

For Nvidia we have updated the FPGA code to read the TSDs and Tsense on both dies of the new dual die products.  

Support for using a TMP468, eight channel TSD reader. 

Individual die temperature sensors can be selected as feedback or the maximum temperature of all of them can be selected. 

Support for AMD GTIC (generic thermal interface card) 

Hyperlog (high speed datalog of individual tests) 

 

Port and Command Enhancements 

- Added automatic switching between I2C TJ and TCP TJ for NVIDIA. 

- Introduced new 1111 port which is reorganized and easier to support and add features to.  

- Added port 3001 back to the TCP command set. 

  

Temperature Sensor Improvements 

- TMP468 updates to show NaN for TJ readings when the compressor is off. 

- Added TSD n-factor support for TMP468, initially for single or first channels. 

  

 Compressor and Bypass Enhancements 

- Added config settings for high stage compressor: default RPM, min, and max. 

- Added suction pressure logic and adjusted bypass target changes when the compressor turns off. 

- Enhanced Cascade hot gas bypass control and logging. 

- Reduced discharge pressure requirement for water-cooled systems and adjusted pressure balance during warmup. 

- Updated compressor power on command logic for better starting conditions and error handling. 

  

PID and Feedback Control 

- Added heater PID proportional band tied to SS-Ramp threshold. 

- Improved EEV PID control with configurable step limits and updated safetemp operation values. 

  

Data Logging and Error Handling 

- Added detailed datalogging for DC TTV and inverter readings. 

- Improved error logging and handling, ensuring critical issues are recorded before TDMS file closure. 

- Introduced new TCP commands for event, warning, and fault testing, and datalog initiation. 

  

User Interface and Display Enhancements 

- M1 and M2 LCD screens now show IP, comments, and address bottom row display issues. 

- Improved GUI naming conventions for clarity. 

- Added piston force feedback to STATUS2() TCP command as requested by customers. 

  

Miscellaneous Improvements 

- Enabled dual zone pedestal testing and new bypass modes for dual head systems. 

- Introduced a 15-second timeout for T-sense freeze below 0°C. As T-Sense has no decimal value when negative. 

- Added moving average to GTIC and enhanced GTIC setpoint handling. 

- Improved handling of custom piston diameters and dynamic setpoint ramp rates. 

  

System Robustness and Flexibility 

- Added new features for solenoid control, enhanced power box requirements,  

- Adjusted criteria for starting conditions to ensure system reliability. 

- Added functionality for PWMing the SSR for DC power and new pressure regulator feedback. 

 

9.23.2024  

    Added functionality for M2 FTC card so we can run heat load on both heads. 

    Also, features have been added to run multiple commander boards to have more than two thermal heads per system 

    Added FPGA code for customer “GC” to read TMP 431 at address 4D on their board. 

    Added function to use TCP temp feedback and have it supersede priority over TSD so the system would automatically switch to TCP Temp feedback when the TCP temperature was received 
