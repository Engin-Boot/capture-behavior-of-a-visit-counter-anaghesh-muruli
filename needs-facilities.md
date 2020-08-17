# Visit-counter for a Facilities Manager

Scenario: Report visitor trends during a week of operation

  Given footfall sensor is working 
  And the visitor counter is set to zero
  When a visitor enters increment the counter
  And when a visitor exits decrement the counter
  Then aggregate the counter value as per need

Scenario: Alert when seating capacity is full

  Given footfall sensor is working 
  And the visitor counter is set to zero
  When a visitor enters increment the counter
  And when a visitor exits decrement the counter
  And if the visitor counter is equal to or greater than maximum seating capacity
  Then alert the manager 
