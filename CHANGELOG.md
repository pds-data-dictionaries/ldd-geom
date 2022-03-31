# Modification History

- Note: Comments from the 1.9.3.0 version copied here to preserve them.

- 1.9.5.0 (2022-01-06)
    - Added ORBITAL (upper and title case) to coordinate_space_frame_type for Mars2020.

- 1.9.4.0 (2021-10-25)
    - This version is the first version where ingest to separated into 4 files.

- 1.9.3.0 (2021-04-27)
    - Added seven enumerated values in upper/lower case (PIXL_TOOL WHEEL_RF, WHEEL_LF, WHEEL_RR, WHEEL_LR, WHEEL_RM, WHEEL_LM) to coordinate_space_frame_type for Mars2020.
    - fixed typo traget -> target

- 1.9.3.0 (2021-07-13)
    - Added yet another enumerated value (TURRET_FRAME and title case version) to coordinate_space_frame_type to support Mars2020.

- 1.9.x.0 (2021-04-22)
    - Added three enumerated values (ROVER_FRAME, TOOL_FRAME, and Tool_Frame) to coordinate_space_frame_type to support Mars2020.

- 1.9.2.0 (2021-03-30)
    - Added enumerated value to coordinate_space_frame_type to support Mars2020.

- 1.9.1.0?? (2020-12-16)
    - Added enumerated value to coordinate_space_frame_type to support Mars2020.
    - Added class Device_Pose to Articulation_Device_Parameters to support Mars 2020.

- 1.9.0.0 (2020-10-16 thru 2020-12-09)
    - Made celestial_north_clock_angle and ecliptic_north_clock_angle nillable. 
    - Added enumerated values for reference_type in Body_Identification_Base and Frame_Identification_Base.
    - Added enumerated values for coordinate_space_frame_type.
    - Changed enumerated flag to true for coordinate_space_frame_type

- 1.8.1.0 (2020-08-14 thru 2020-08-28)
    - Added target_name, target_heliocentric_distance, and solar_image_clock_angle to the 
    - Derived_Geometry class in the Geometry_Lander section. 
    - Changed attitude_propagation_counter data type from integer to real for M2020.
    - Added new attribute geometry_state, pds:description, pds:local_identifier to the start of the Geometry_Lander class

- 1.8.0.0 (2020-07-31)
    - Added Vector_Solar_Direction class to Derived_Geometry; made Vector_Axis_X/Y classes a restriction of the Vector_Cartesian_Unit class.
    - Added Coordinate_Space_Quality to Coordinate_Space_Definition.
    - Added Commanded_Geometry to Articulation_Device_Parameters 
    - have to edit schema to fix the "choice bug"

- 1.7.2.0 (2020-05-04; 2020-07-10)
    - Modified definitions for quaternion_measurment_method.
    - Added the Interpolation class to support documentation of camera model interpolation. Included in the Camera_Model_Parameters class.
    - Added PSPH camera model (5 classes and 2 attributes); added enumerated list for model_type relative to camera models.

- 1.7.1.0 (2019-05-06)
    - Added attribute quaternion_measurement_method and included it in the Coordinate_Space_Definition class.
    - Added local_identifier to the Articulation_Device_Parameters

- 1.7.0.0 (2019-04-19)     
    - Set the element_flag to "true" for the Coordinate_Space_Reference class so that the class is exposed for others to use.

- 1.6.1.0 (2018-12-05)
    - Changed the cardinality (maxoccurs) of Object_Orientation_RA_Dec in Image_Display_Geometry from 3 to unlimited to support request for MESSENGER MDIS migration to PDS4.

- 1.6.0.0 (2018-07-27)
    - Changed Optical_Terms to Vector_Optical, reparented it to Vector_Cartesian_Unit, and fixed the definition.
    - Changed Vector_Entrance to Entrance_Terms, reparented it to Polynomial_Coefficients_3, and fixed the definition.
    - Rewrote definitions for CAHV_Model, CAHVOR_Model, CAHVORE_Model, Vector_Center, Vector_Horizontal, Vector_Vertical, and Radial_Terms.
    - Minor revisions to definitions for Camera_Model_Parameters, Coordinate_Space_Present, Coordinate_Space_Reference, instrument_azimuth, instrument_elevation, Quaternion_Plus_Direction, solar_azimuth, geometry_start_time_utc, and geometry_stop_time_utc.
    - Minor changes to definitions of incidence_angle and phase_angle.

- 1.5.3.0 (2018-07-25)
    - Updated for PDS information model 1.10.1.0

- 1.5.2.0 (2018-07-25)
    - Updated for PDS information model 1.10.0.0
    - In Image_Display_Geometry, moved Object_Orientation_Clock_Angles into the choice statement.

- 1.5.1.0 (2017-09-20)
    - Added index_value_number to List_Index_Temperature to specify DN temperature counts in addition to the EU temperature
    - Updated the definition for List_Index_Temperature to include that
    - Fixed bug with Vector_Entrance to use Vector_Cartesian_Unit instead of Vector_Cartesian_Position_Base
    - Updated for PDS model 1.9.0.0

- 1.5.0.0 (2017-06-19)
    - Regenerated the schema and other files because of a bug in the LDDTool - This changed the classes: Coordinate_Space_Identification, Coordinate_Space_Present, Coordinate_Space_Reference
    - Changed the maxoccurs to unbounded for Coordinate_Space_Index in Coordinate_Space_Indexed
    - Changed the choice in Derived_Geometry to include all optional attributes. This was done to ensure that the class contained at least one attribute when included in a label.

- 1.4.0.1 (2016-11-10)
    - Changed pds:name to geom:name in the schematron rules 

- 1.4.0.0 (2016-09-26)
    - Verified that Internal_Reference and Local_Internal_Reference refer to the PDS namespace in class definitions
    - Edited Schematron rules to change geom:Internal_Reference to pds:Internal_Reference
    - Edited Schematron rules to match Internal_Reference contexts with reference_type rule_test
    - Edited Schematron messages to be more user-friendly
    - Remove reference_type and local_reference_type from Schematron rule contexts
    - Edited Schematron rules to change geom:Local_Internal_Reference to pds:Local_Internal_Reference
    - Edited Schematron rules to match Local_Internal_Reference contexts with local_reference_type rule_text

- 1.3.1.0 (2016-07-29)
    - Added the optional attribute kernel_provenance to the SPICE_Kernel_Identification class.
    - Renamed geometry_reference_time, geometry_start/stop_time, and coordinate_system_time, by appending _utc to the attribute name.
    - Added the optional attribute geometry_reference_time_tdb
    - Changed the cardinality of Quaternion_Plus_To_From in the Image_Display_Geometry to allow multiple instances.
    - Added the optional Expanded_Geometry class to the Geometry class

- 1.3.0.0 (2016-07-15)
    - Updated to IM version 1.6.0.0
    - Changed to four place version number.
    - Added geometry_start_time and geometry_stop_time, and expanded the definitions for the three variations of geometry_*_time.
    - Made geom:Display_Direction required even if the disp:Display_Direction is in the label.
    - Removed the option to use Quaternion_1 from the Image_Display_Geometry class since there is no way to identify the relevant end points in the enclosing class.
    - Revised the definition of right_ascension_angle.
    - Changed the description and units of right_ascension_hour_angle to decimal hours.
    - Revised the definition of declination_angle.
    - In Object_Orientation_Clock_Angles, made Reference_Frame_Identification optional instead of required.
    - Added or modified attributes minimum_*, maximum_*, start_*, stop_*; where * is any of target_geocentric_distance, target_heliocentric_distance, target_ssb_distance, spacecraft_geocentric_distance, spacecraft_heliocentric_distance, spacecraft_to_central_body_distance, spacecraft_to_target_center_distance, spacecraft_to_target_boresight_intercept_distance,  spacecraft_to_target_subspacecraft_distance, emission_angle, incidence_angle, phase_angle, solar_elongation, latitude, longitude, subspacecraft_azimuth, subspacecraft_latitude, subspacecraft_longitude, subsolar_azimuth, subsolar_latitude, or subsolar_longitude.
    - Added the attribute lat_long_description to support start_ and stop_ latitude and longitude.
    - Added the classes *_Specific, *_Min_Max, *_Start_Stop; where * is any of Distances, Illumination, or Surface_Geometry.
    - Removed the classes Illumination_FOV_Range_Values (replaced with the class Illumination_Min_Max), and Illumination_Single_Values (replaced with the class Illumination_Specific).
    - Removed the attribute illumination_range_designation.
    - Changed the names of several specific distance classes from spacecraft_to_*_distance to spacecraft_*_distance.
    - Renamed Specific_Distances to Distances_Specific.
    - Renamed Surface_Geometry to Surface_Geometry_Specific.
    - Renamed Illumination_Single_Values to Illumination_Specific.
    - Renamed Specific_Cartesian_Vectors to Vectors_Cartesian_Specific.
    - Renamed Specific_Planetocentric_Vectors to Vectors_Planetocentric_Specific.
    - Added or redefined several classes for grouping: Orbiter_Identification, Distances, Surface_Geometry, Illumination_Geometry, Vectors.
    - Reorganized the contents of Geometry_Orbiter.
    - Provided Schematron rules to ensure if one member of a min-max or start-stop pair is used, both are used.
    - Renamed lat_long_description to lat_long_method
    - Renamed Quaternion_1 to Quaternion_Plus_Direction
    - Renamed Quaternion_2 to Quaternion_Plus_To_From
    - In List_Index_Base removed Local_Internal_Reference and made the cardinality of the choice to require at least one of the options.
    - Updated the definitions of several attributes supporting the Lander portion of the dictionary.
    - Changed pds:Internal_Reference to geom:Internal_Reference
    - Changed pds:Local_Internal_Reference to geom:Local_Internal_Reference
    - In the Geometry class, removed the choice statement which made one of Geometry_Orbiter and Geometry_Lander required. Now both are optional.

- 1.2.1 (2015-11-12) (this version not released for review)
    - Inserted a missing ")" in Schematron file to correct a typo.
    - Changed several instances of a double underscore to a single underscore.
    - Removed Local_Reference_Type from geom:Display_Direction.
    - Added Schematron rule for Image_Display_Geometry/Local_Internal_Reference/Reference_Type to verify use of the enumerated value "display_to_data_object".
    - In Geometry_Orbiter, moved the class Geometry_Target_Identification ahead of the class Coordinate_System Identification. This results in placing at the beginning of the class, the items most likely to have multiple values and hence result in multiple instances of the Geometry_Orbiter class.

- 1.2.0 (2015-10-15)
    - Updated to IM version 1.5.0.0
    - Redefined the Display_Direction class and removed the import of the Display dictionary.
    - Designated Body_Identification_Base as 'abstract'
    - Renamed Target_Identification to Geometry_Target_Identification
    - Renamed horizontal/vertical_pixel_size_angular to horizontal/vertical_pixel_field_of_view
    - Renamed horizontal/vertical_pixel_size_projected to horizontal/vertical_pixel_footprint
    - Removed Body_Identification_Base from Image_Display
    - Removed body_positive_pole_clock_angle
    - Added central_body_positive_pole_clock_angle
    - Removed Local_Internal_Reference from several classes
    - Removed horizontal/vertical_pixel_scale_factor
    - Updated horizontal/vertical_pixel_field_of_view descriptions
    - Added new, required attribute pixel_field_of_view_method attribute to Pixel_Dimensions
    - Allow for multiple Pixel_Size_Projected classes to be specified in the Pixel_Dimensions class.
    - Revised the definition of Footprint_Vertices and set the minimum number of vertices to two.
    - Added choice between reference_location and new distance attribute in Pixel_Size_Projected class.
    - Added 'Constant' (or some other applicable term per rationale) as a permissible value to Pixel_Size_Projected and reference_location.
    - Require horizontal_pixel_footprint and vertical_pixel_footprint to be specified in Pixel_Size_Projected class.
    - Added cahvore_model_type and cahvore_model_parameter attributes to CAHVORE_Model 
    - Added new positive_azimuth_direction and positive_elevation_direction attributes to Coordinate_Space_Definition class
    - Added new instrument_azimuth, instrument_elevation attributes to Derived_Geometry
    - Added new selected_instrument_id attribute to Articulation_Device_Parameters for currently selected instrument
    - added new device_phase attribute to Articulation_Device_Parameters
    - added new Quaternion_Model_Transform and Vector_Model_Transform classes to the Camera_Model_Parameters class
    - fixed bug with Vector_Cartesian_No_Units class - local identifier was Vector_Cartesian_Unit and overwriting that class
    - changed parent_of Vector_Axis class to Vector_Cartesian_No_Units
    - changed parent_of Vector_Device_Gravity class to Vector_Cartesian_Unit instead of Position_Cartesion_Vector_Base since it is a unit vector
    - added pds:Local_Internal_Reference to Coordinate_Space_Identification class, specifically for properly defining a Coordinate_Space_Reference. 
    - updated the definition for coordinate_space_frame_type
    - changed ordering of Coordinate_Space_Indexed to make more logical sense
    - changed local_identifier attribute in Coordinate_Space_Definition class to allow for mutliple identifiers for a Coordinate Space
    - removed units from x_pixel, y_pixel, z_pixel
    - changed x_no_units, y_no_units, z_no_units to x,y,z
    - removed Coordinate_Space_Reference from CAHV_Model class. It only needs to be in the Camera_Model_Parameters class
    - north/east_azimuth - expanded definition to clarify direction of measurement.
    - renamed the Distances class to Specific_Distances, removed the Distance_Generic class from that class and added it to Geometry_Orbiter. 
    - removed the Specific_Position_Vectors and Specific_Velocity_Vectors classes. The remaining Vector aggragating classss are Specific_Cartesian_Vectors and Specific_Planetocentric_Vectors.
    - Renamed 59 classes for clarity or to make the order of the class name segments consistent with SR requirements. See the separate class-rename-20151016.txt document for the complete list.

- 1.1.0 (2015-08-17) 
    - Updated to IM version 1.4.1.0
    - Removed attributes body_spice_id and frame_spice_id. body_spice_name and frame_spice_name are the supported attributes.
    - Geometry_Identification_Base was replaced by Body_Identification_Base and Frame_Identification_Base. 
    - The preceding two changes affect these classes: Central_Body_Identification, Coordinate_System_Origin_Identification, Observer_Identification, Target_Identification.
    - Added the class Coordinate_Space_SPICE. 
    - SPICE_Kernel_Identification was replaced with the new class Coordinate_Space_SPICE in Coordinate_Space_Identification. 
    - Replaced local_spice_kernel_name with spice_kernel_file_name.
    - Changed kernel_type to pds:kernel_type.
    - The preceding four changes affect Coordinate_Space_Present and Coordinate_Space_Reference.
    - horizontal/vertical_pixel_scale_factor now have unit of measure type Units_of_Map_scale (these are all of the form "[length]/pixel").
    - In Geometry_Orbiter class, expanded description to include class use. 
    - Quaternion_non_SPICE_Style contained a double underscore in the class name. That typo has been corrected.
    - Updated a number of the attribute and class definitions/descriptions 
    - In the Geometry_Orbiter class, Reference_Frame_Identification was removed. 
    - Added class Coordinate_Space_Indexed
    - Moved solution_id attribute from Coordinate_Space_Index to Coordinate_Space_Indexed
    - Removed model_desc_file_name from Camera_Model_Parameters
    - Replaced Coordinate_Space_Index with Coordinate_Space_Indexed in Coordinate_Space_Identification
    - Added Local_Internal_Reference to Coordinate_Space_Index
    - Added attribute coordinate_space_frame_type
    - Renamed Device_Motor_Clicks* to Device_Motor_Counts*
    - Renamed Device_Position_Vector to Vector_Device_Gravity
    - Renamed index_value_no_units to index_value_number.
    - Completely revised quaternions, removed all four existing quaternion classes, Quaternion_SPICE, Quaternion_non_SPICE, Rotation_Quaternion, and Device_Orientation_Quaternion. Introduced three new quaternion classes, Quaternion_Base, Quaternion_1, and Quaternion_2. The latter two are extensions of Quaternion_Base. 
    - Revised the definitions of the four components of quaternions.
    - Added the classes Rotate_From, Rotate_To, and the attribute rotation_direction to support the new quaternion classes.
    - Added Coordinate_Space_Present to the Articulation_Device_Parameters class.
    - Renamed Coordinate_System to Coordinate_System_Identification.
    - In Coordinate_Space_Indexed changed Coordinate_Space_Index from parent_of to component_of
    - Removed pds:Local_Internal_Reference from Coordinate_Space_Index, Body_Identification_Base, Frame_Identification_Base.
    - Removed the quaternions from the Articulation_Device_Parameters class.
    - Cleaned up some more definitions.

- 1.0.0 (2015-04-30)
    - Initial release.