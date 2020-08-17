# Visit-counter for a Director

Scenario: Show patient visits during working days and holidays

  Given Patient token issuer is working and token number is set to zero
  When a patient enters the hospital
  And the token is not issued before to the person
  Then issue the token and increment the token number
  And store the number of last token issued at the end of the day

Scenario: Compute parking slots to reserve for visiting specialists

  Given the visiting specialist is visiting the hospital by a vehical
  And requires a parking slot 
  And the person's schedule is known
  And parking slot counter is set to zero
  When the specialist enters the hospital
  Then identify the type of parking slot required based on the vehical
  And increment the parking slot counter
  And display thr result at the end of the day
