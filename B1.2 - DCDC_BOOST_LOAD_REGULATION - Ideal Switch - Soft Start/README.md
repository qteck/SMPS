# SMPS: DC DC Boost - Load Regulation Circuitry

Load regulation is implemented to ensure that voltage output remains stable under different loads. 

When the load on on the dcdc boost circuit changes the current that will flow over the load will vary as well. To ensure that the voltage over the cnahged load will remain the same the frequncy of switching of the moesfet switch in the dc dc boost converter needs to be controlled. 

This is done by implementing two comparators

- defined Vt - threshold voltage 
- defined vh - hysteresis

Adding RC - network for soft start to eliminate the initial overshoot 
Interaction with other RLC elements in the circuit
Overshoot attennuation achieved by testing