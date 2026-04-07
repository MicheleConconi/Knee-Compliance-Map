# Knee-Compliance-Map
A MATLAB representation of the experimentally derived map of the knee compliance. The map returns the tibio-femoral position and orientation given the flexion angle and the external load (force and torque) applied to the articulation.

## Introduction
This repository contains a MATLAB package that permits to use the Knee-Compliance-Map to obtain the tibio-femoral position and orientation of the knee, given the flexion angle and the external load (force and torque) applied to the articulation.
The spatial kinematics is obtained as the natural (passive) motion of the knee, plus the deformation induced by the applied loads. 

## Reference System
The map is originally expressed as the motion of the femur with respect to the tibia. The coordinates are expressed as a variation of the Grood and Suntay convention, more specifically: the femur is moving with respect to the tibia anatomical reference frame. Position is normalized to consider the full extended position as the null position (each motion component equal 0).

## Versions:
### V1
This version contains two folders:
- *Stiffness map - matlab files/KNEE COMPLIANCE EVALUTATOR*:
   - contains all the MATLAB functions to run the calculation
     - _GeS_Compute_Coordinates_: returns the Grood and Suntay coordinates (GeS) associated to the rototranslational matrix (T).
	 - _T_Move2Position_: Compute the rototranslation matrix (T) from the Grood and Suntay coordinates (GeS).
	 - _compliance_fitting_model_: returns the value calculated through the compliance fitting model (that is: _polinomial of 4<sup>th</sup> grade in flexion, logarithmic in load_).
	 - _knee_compliance_: returns the variation in femur position and orientation with respect to the values observed for the knee natural motion at the considered flexion angle. Displacement are obtained as the linar combination of the displacement induced by each load component separately.
	 - ***knee_loaded_motion***: returns the position and orientation of the tibio-femoral at the given flexion_angle under the effect of the external loads. The coordinate are expressed according to a variation of the Grood and Suntay notation and are evaluated as the sum of femur natural motion (computed trugh the function knee_natural_motion.m) the displacement induced by external loads (computed trugh the function knee_compliance.m)
	 - _knee_natural_motion_: Simply return the position and orientation of the femur with respect to the tibia anatomical reference system at the given flexion_angle.
   - contains all the polinomial coefficients obtained from the fitting procedure.
- *newFigures*: contains .fig and .png files of the map fitting surfaces.
   - Each figure represents the continuos deformation obtained for a monoaxial load envelope (force or torque), through the entire flexion range.