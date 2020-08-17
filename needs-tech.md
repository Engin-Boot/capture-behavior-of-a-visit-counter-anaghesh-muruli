# Visit-counter technical needs

Scenario: Recover across restarts of the server
that runs the visit-counter

  Given the value of visit-counter
  When the server is about to restart 
  Then put the count value into the central database
  And start the visit-counter from the last count value

Scenario: Reconcile counts if the sensor is offline for a while

  Given the sensor is working
  When the sensor is offline 
  Then restart the sensor from the last count value
