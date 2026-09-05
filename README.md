# Furnace_Temp_Project

This data comes from various furnaces used to heat treat aerospace components.  My goal is to understand how furnaces react to a door open event (that will be in a different data set).  Furnace temperature will drop, and will take some period of time to recover to the set point.  I'd like to identify errant thermocouples, furnaces that do not recover to temperature in a reasonable time, what that reasonable time is based on the other furnaces, etc. 

## Data Structure

DATE_TIME
  Date and timestamp of record

DSF
  Currently unsure what this means; but it is "Y" in all records, so not useful information

MACHINE_IDENTIFIER
  Serial number of the furnace

TEMP_SETPOINT
  Desired temperature for the furnace at the given time

CONTROLLER_TC_TEMP
  Temperature reading from one thermocouple - this is the only thermocouple that drives the PID loop to attempt to reach the setpoint

PERCENT_POWER
  Amount of power the system is outputting at the given time, based on current temp, setpoint, and PID loop

ZONE_1_TC_TEMP
ZONE_2_TC_TEMP
ZONE_3_TC_TEMP
ZONE_4_TC_TEMP
ZONE_5_TC_TEMP
  There are (5) "feedback only" thermocouples in each furnace.  These do not affect the PID loop.  The intention is for the furnace to
  have uniform temperature throughout.  When a door open event occurs, it is likely the TC nearest the door will experience the largest
  variability.  We do not know which TC corresponds to this position with the raw data. 
