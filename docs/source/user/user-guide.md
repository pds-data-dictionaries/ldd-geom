PDS4 Geometry Discipline Data Dictionary User's Guide  
[Last edited](#edit-history): 2026-02-09  
  
# Introduction  
1. Purpose of this User's Guide  
    - This User's Guide provides an overview of the Geometry Discipline Data Dictionary. The guide details how to include the dictionary in a PDS4 label, describes the organization of the dictionary's classes and attributes, provides definitions for these classes and attributes, and lists example excerpts from labels that use them.  
2. Audience  
    - This User's Guide should be useful to data providers intending to archive Geometry data with PDS as well as PDS Nodes who are working with these data providers.  
  
# Overview of the Geometry Discipline Data Dictionary  
The Geometry Discipline Data Dictionary contains classes and attributes specific to the Geometry discipline.  
Steward: Madison N. Hughes, PDS Geosciences Node, mnhughes@wustl.edu  
  
# Document Outline  
1. [How to Include the Geometry Discipline Data Dictionary in a PDS4 Label](#how-to-include-the-Geometry-Discipline-data-dictionary-in-a-pds4-label)  
2. [Organization of Classes and Attributes](#organization-of-classes-and-attributes)  
    1. [Class Organization](#class-organization)  
    2. [Attributes by Class](#attributes-by-class)  
3. [Definitions](#definitions)  
    1. [Classes (in alphabetical order)](#classes-in-alphabetical-order)  
    2. [Attributes (in alphabetical order)](#attributes-in-alphabetical-order)  
4. [Examples](#examples)  
5. [Edit History](#edit-history)  
  
# How to Include the Geometry Discipline Data Dictionary in a PDS4 Label  
The dictionary consists of a set of files with names in the form PDS4_GEOM_xxxx_yyyy.ext, where  
- xxxx = the PDS4 Information Model version, e.g. 1P00  
- yyyy = the Geometry Discipline Data Dictionary version, e.g. 19B0  
  
and the file extensions are  
  
- .csv = A comma-separated value table of dictionary attributes  
- .JSON = The dictionary contents in JSON format  
- .sch = The dictionary "rules" as an XML Schematron file  
- .txt = The report generated when the dictionary was built  
- .xml = The PDS4 label that describes this set of files  
- .xsd = The dictionary contents as an XML schema file  
  
Only the schema and Schematron files are needed for validating a PDS4 label.  
  
The latest version of this dictionary may be found on the PDS web site at https://pds.nasa.gov/datastandards/dictionaries/index.shtml#geom.  
  
The following is an example showing the use of this dictionary in a PDS4 label.  
  
```
<?xml version="1.0" encoding="UTF-8"?>
<?xml-model href="https://pds.nasa.gov/pds4/pds/v1/PDS4_PDS_1P00.sch" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<?xml-model href="https://pds.nasa.gov/pds4/geom/v1/PDS4_GEOM_1P00_19B0.sch" schematypens="http://purl.oclc.org/dsdl/schematron"?>
<Product_Observational xmlns="http://pds.nasa.gov/pds4/pds/v1"
    xmlns:geom="http://pds.nasa.gov/pds4/geom/v1"
    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
    xsi:schemaLocation="https://pds.nasa.gov/pds4/pds/v1/PDS4_PDS_1P00.xsd
                        https://pds.nasa.gov/pds4/geom/v1/PDS4_GEOM_1P00_19B0.xsd">
```  
  
The following is a schematic example showing the location of every Geometry Discipline Data Dictionary class and attribute in a PDS4 label. Note that not all classes and attributes may be mutually compatible, and the example does not include any recursion, even if recursion is allowed.  
```
<Observation_Area>
  ...
  <Discipline_Area>
    <geom:Coordinate_Space_Identification>
      <geom:Coordinate_Space_Indexed>
        <geom:coordinate_space_frame_type/>
        <geom:solution_id/>
        <geom:Coordinate_Space_Index>
          <geom:index_sequence_number/>
          <geom:index_name/>
          <geom:index_id/>
          <geom:index_value_number/>
        </geom:Coordinate_Space_Index>
      </geom:Coordinate_Space_Indexed>
      <geom:Coordinate_Space_SPICE>
        <geom:body_spice_name/>
        <geom:frame_spice_name/>
      </geom:Coordinate_Space_SPICE>
      <geom:Local_Internal_Reference>
      </geom:Local_Internal_Reference>
    </geom:Coordinate_Space_Identification>
    <geom:Geometry>
      <geom:SPICE_Kernel_Files>
        <geom:comment/>
        <geom:SPICE_Kernel_Identification>
          <geom:kernel_type/>
          <geom:spice_kernel_file_name/>
          <geom:kernel_provenance/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:SPICE_Kernel_Identification>
      </geom:SPICE_Kernel_Files>
      <geom:Expanded_Geometry>
        <geom:Local_Internal_Reference>
        </geom:Local_Internal_Reference>
        <geom:Internal_Reference>
        </geom:Internal_Reference>
      </geom:Expanded_Geometry>
      <geom:Image_Display_Geometry>
        <geom:Local_Internal_Reference>
        </geom:Local_Internal_Reference>
        <geom:Display_Direction>
          <geom:comment/>
          <geom:horizontal_display_axis/>
          <geom:horizontal_display_direction/>
          <geom:vertical_display_axis/>
          <geom:vertical_display_direction/>
        </geom:Display_Direction>
        <geom:Central_Body_Identification>
          <geom:local_identifier/>
          <geom:body_spice_name/>
          <geom:name/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Central_Body_Identification>
        <geom:Geometry_Target_Identification>
          <geom:local_identifier/>
          <geom:body_spice_name/>
          <geom:name/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Geometry_Target_Identification>
        <geom:Object_Orientation_North_East>
          <geom:north_azimuth/>
          <geom:east_azimuth/>
          <geom:Reference_Frame_Identification>
            <geom:local_identifier/>
            <geom:frame_spice_name/>
            <geom:name/>
            <geom:comment/>
            <geom:Internal_Reference>
            </geom:Internal_Reference>
          </geom:Reference_Frame_Identification>
        </geom:Object_Orientation_North_East>
        <geom:Object_Orientation_RA_Dec>
          <geom:reference_pixel_location/>
          <geom:right_ascension_hour_angle/>
          <geom:right_ascension_angle/>
          <geom:declination_angle/>
          <geom:celestial_north_clock_angle/>
          <geom:ecliptic_north_clock_angle/>
          <geom:Reference_Pixel>
            <geom:vertical_coordinate_pixel/>
            <geom:horizontal_coordinate_pixel/>
          </geom:Reference_Pixel>
          <geom:Reference_Frame_Identification>
          </geom:Reference_Frame_Identification>
        </geom:Object_Orientation_RA_Dec>
        <geom:Object_Orientation_Clock_Angles>
          <geom:celestial_north_clock_angle/>
          <geom:celestial_east_clock_angle/>
          <geom:ecliptic_north_clock_angle/>
          <geom:ecliptic_east_clock_angle/>
          <geom:central_body_north_pole_clock_angle/>
          <geom:central_body_positive_pole_clock_angle/>
          <geom:target_north_pole_clock_angle/>
          <geom:target_positive_pole_clock_angle/>
          <geom:sun_direction_clock_angle/>
        </geom:Object_Orientation_Clock_Angles>
        <geom:Quaternion_Plus_To_From>
          <geom:qcos/>
          <geom:qsin1/>
          <geom:qsin2/>
          <geom:qsin3/>
          <geom:Rotate_From>
            <geom:local_identifier/>
            <geom:frame_spice_name/>
            <geom:name/>
            <geom:comment/>
            <geom:Internal_Reference>
            </geom:Internal_Reference>
          </geom:Rotate_From>
          <geom:Rotate_To>
            <geom:local_identifier/>
            <geom:frame_spice_name/>
            <geom:name/>
            <geom:comment/>
            <geom:Internal_Reference>
            </geom:Internal_Reference>
          </geom:Rotate_To>
        </geom:Quaternion_Plus_To_From>
      </geom:Image_Display_Geometry>
      <geom:Geometry_Orbiter>
        <geom:geometry_reference_time_utc/>
        <geom:geometry_start_time_utc/>
        <geom:geometry_stop_time_utc/>
        <geom:geometry_reference_time_tdb/>
        <geom:Orbiter_Identification>
          <geom:Central_Body_Identification>
          </geom:Central_Body_Identification>
          <geom:Geometry_Target_Identification>
          </geom:Geometry_Target_Identification>
          <geom:Coordinate_System_Identification>
            <geom:coordinate_system_type/>
            <geom:coordinate_system_time_utc/>
            <geom:comment/>
            <geom:Coordinate_System_Origin_Identification>
              <geom:local_identifier/>
              <geom:body_spice_name/>
              <geom:name/>
              <geom:Internal_Reference>
              </geom:Internal_Reference>
            </geom:Coordinate_System_Origin_Identification>
            <geom:Reference_Frame_Identification>
            </geom:Reference_Frame_Identification>
          </geom:Coordinate_System_Identification>
        </geom:Orbiter_Identification>
        <geom:Pixel_Dimensions>
          <geom:pixel_field_of_view_method/>
          <geom:horizontal_pixel_field_of_view/>
          <geom:vertical_pixel_field_of_view/>
          <geom:Pixel_Size_Projected>
            <geom:reference_location/>
            <geom:distance/>
            <geom:horizontal_pixel_footprint/>
            <geom:vertical_pixel_footprint/>
          </geom:Pixel_Size_Projected>
        </geom:Pixel_Dimensions>
        <geom:Distances>
          <geom:comment/>
          <geom:Distances_Specific>
            <geom:spacecraft_geocentric_distance/>
            <geom:spacecraft_heliocentric_distance/>
            <geom:spacecraft_central_body_distance/>
            <geom:spacecraft_target_center_distance/>
            <geom:spacecraft_target_boresight_intercept_distance/>
            <geom:spacecraft_target_subspacecraft_distance/>
            <geom:target_geocentric_distance/>
            <geom:target_heliocentric_distance/>
            <geom:target_ssb_distance/>
          </geom:Distances_Specific>
          <geom:Distances_Min_Max>
            <geom:minimum_spacecraft_geocentric_distance/>
            <geom:maximum_spacecraft_geocentric_distance/>
            <geom:minimum_spacecraft_heliocentric_distance/>
            <geom:maximum_spacecraft_heliocentric_distance/>
            <geom:minimum_spacecraft_central_body_distance/>
            <geom:maximum_spacecraft_central_body_distance/>
            <geom:minimum_spacecraft_target_center_distance/>
            <geom:maximum_spacecraft_target_center_distance/>
            <geom:minimum_spacecraft_target_boresight_intercept_distance/>
            <geom:maximum_spacecraft_target_boresight_intercept_distance/>
            <geom:minimum_spacecraft_target_subspacecraft_distance/>
            <geom:maximum_spacecraft_target_subspacecraft_distance/>
            <geom:minimum_target_geocentric_distance/>
            <geom:maximum_target_geocentric_distance/>
            <geom:minimum_target_heliocentric_distance/>
            <geom:maximum_target_heliocentric_distance/>
            <geom:minimum_target_ssb_distance/>
            <geom:maximum_target_ssb_distance/>
          </geom:Distances_Min_Max>
          <geom:Distances_Start_Stop>
            <geom:start_spacecraft_geocentric_distance/>
            <geom:stop_spacecraft_geocentric_distance/>
            <geom:start_spacecraft_heliocentric_distance/>
            <geom:stop_spacecraft_heliocentric_distance/>
            <geom:start_spacecraft_central_body_distance/>
            <geom:stop_spacecraft_central_body_distance/>
            <geom:start_spacecraft_target_center_distance/>
            <geom:stop_spacecraft_target_center_distance/>
            <geom:start_spacecraft_target_boresight_intercept_distance/>
            <geom:stop_spacecraft_target_boresight_intercept_distance/>
            <geom:start_spacecraft_target_subspacecraft_distance/>
            <geom:stop_spacecraft_target_subspacecraft_distance/>
            <geom:start_target_geocentric_distance/>
            <geom:stop_target_geocentric_distance/>
            <geom:start_target_heliocentric_distance/>
            <geom:stop_target_heliocentric_distance/>
            <geom:start_target_ssb_distance/>
            <geom:stop_target_ssb_distance/>
          </geom:Distances_Start_Stop>
          <geom:Distance_Generic>
            <geom:distance/>
            <geom:Observer_Identification>
              <geom:local_identifier/>
              <geom:body_spice_name/>
              <geom:name/>
              <geom:Internal_Reference>
              </geom:Internal_Reference>
            </geom:Observer_Identification>
            <geom:Geometry_Target_Identification>
            </geom:Geometry_Target_Identification>
          </geom:Distance_Generic>
        </geom:Distances>
        <geom:Surface_Geometry>
          <geom:comment/>
          <geom:Surface_Geometry_Specific>
            <geom:subsolar_azimuth/>
            <geom:subsolar_latitude/>
            <geom:subsolar_longitude/>
            <geom:subspacecraft_azimuth/>
            <geom:subspacecraft_latitude/>
            <geom:subspacecraft_longitude/>
            <geom:Pixel_Intercept>
              <geom:reference_pixel_location/>
              <geom:pixel_latitude/>
              <geom:pixel_longitude/>
              <geom:Reference_Pixel>
              </geom:Reference_Pixel>
            </geom:Pixel_Intercept>
            <geom:Footprint_Vertices>
              <geom:Pixel_Intercept>
              </geom:Pixel_Intercept>
            </geom:Footprint_Vertices>
          </geom:Surface_Geometry_Specific>
          <geom:Surface_Geometry_Min_Max>
            <geom:minimum_latitude/>
            <geom:maximum_latitude/>
            <geom:minimum_longitude/>
            <geom:maximum_longitude/>
            <geom:minimum_subsolar_azimuth/>
            <geom:maximum_subsolar_azimuth/>
            <geom:minimum_subsolar_latitude/>
            <geom:maximum_subsolar_latitude/>
            <geom:minimum_subsolar_longitude/>
            <geom:maximum_subsolar_longitude/>
            <geom:minimum_subspacecraft_azimuth/>
            <geom:maximum_subspacecraft_azimuth/>
            <geom:minimum_subspacecraft_latitude/>
            <geom:maximum_subspacecraft_latitude/>
            <geom:minimum_subspacecraft_longitude/>
            <geom:maximum_subspacecraft_longitude/>
          </geom:Surface_Geometry_Min_Max>
          <geom:Surface_Geometry_Start_Stop>
            <geom:lat_long_method/>
            <geom:start_latitude/>
            <geom:stop_latitude/>
            <geom:start_longitude/>
            <geom:stop_longitude/>
            <geom:start_subsolar_azimuth/>
            <geom:stop_subsolar_azimuth/>
            <geom:start_subsolar_latitude/>
            <geom:stop_subsolar_latitude/>
            <geom:start_subsolar_longitude/>
            <geom:stop_subsolar_longitude/>
            <geom:start_subspacecraft_azimuth/>
            <geom:stop_subspacecraft_azimuth/>
            <geom:start_subspacecraft_latitude/>
            <geom:stop_subspacecraft_latitude/>
            <geom:start_subspacecraft_longitude/>
            <geom:stop_subspacecraft_longitude/>
          </geom:Surface_Geometry_Start_Stop>
        </geom:Surface_Geometry>
        <geom:Illumination_Geometry>
          <geom:comment/>
          <geom:Illumination_Specific>
            <geom:reference_location/>
            <geom:reference_pixel_location/>
            <geom:emission_angle/>
            <geom:incidence_angle/>
            <geom:phase_angle/>
            <geom:solar_elongation/>
            <geom:Reference_Pixel>
            </geom:Reference_Pixel>
          </geom:Illumination_Specific>
          <geom:Illumination_Min_Max>
            <geom:minimum_emission_angle/>
            <geom:maximum_emission_angle/>
            <geom:minimum_incidence_angle/>
            <geom:maximum_incidence_angle/>
            <geom:minimum_phase_angle/>
            <geom:maximum_phase_angle/>
            <geom:minimum_solar_elongation/>
            <geom:maximum_solar_elongation/>
          </geom:Illumination_Min_Max>
          <geom:Illumination_Start_Stop>
            <geom:start_emission_angle/>
            <geom:stop_emission_angle/>
            <geom:start_incidence_angle/>
            <geom:stop_incidence_angle/>
            <geom:start_phase_angle/>
            <geom:stop_phase_angle/>
            <geom:start_solar_elongation/>
            <geom:stop_solar_elongation/>
          </geom:Illumination_Start_Stop>
        </geom:Illumination_Geometry>
        <geom:Vectors>
          <geom:comment/>
          <geom:Vectors_Cartesian_Specific>
            <geom:Vector_Cartesian_Position_Central_Body_To_Spacecraft>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_Central_Body_To_Spacecraft>
            <geom:Vector_Cartesian_Position_Central_Body_To_Target>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_Central_Body_To_Target>
            <geom:Vector_Cartesian_Position_Spacecraft_To_Target>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_Spacecraft_To_Target>
            <geom:Vector_Cartesian_Position_SSB_To_Central_Body>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_SSB_To_Central_Body>
            <geom:Vector_Cartesian_Position_SSB_To_Spacecraft>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_SSB_To_Spacecraft>
            <geom:Vector_Cartesian_Position_SSB_To_Target>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_SSB_To_Target>
            <geom:Vector_Cartesian_Position_Sun_To_Central_Body>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_Sun_To_Central_Body>
            <geom:Vector_Cartesian_Position_Sun_To_Spacecraft>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_Sun_To_Spacecraft>
            <geom:Vector_Cartesian_Position_Sun_To_Target>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_Sun_To_Target>
            <geom:Vector_Cartesian_Position_Earth_To_Central_Body>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_Earth_To_Central_Body>
            <geom:Vector_Cartesian_Position_Earth_To_Spacecraft>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_Earth_To_Spacecraft>
            <geom:Vector_Cartesian_Position_Earth_To_Target>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Position_Earth_To_Target>
            <geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_Central_Body>
              <geom:x_velocity/>
              <geom:light_time_correction_applied/>
              <geom:y_velocity/>
              <geom:z_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_Central_Body>
            <geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_Target>
              <geom:x_velocity/>
              <geom:light_time_correction_applied/>
              <geom:y_velocity/>
              <geom:z_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_Target>
            <geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_Earth>
              <geom:x_velocity/>
              <geom:light_time_correction_applied/>
              <geom:y_velocity/>
              <geom:z_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_Earth>
            <geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_SSB>
              <geom:x_velocity/>
              <geom:light_time_correction_applied/>
              <geom:y_velocity/>
              <geom:z_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_SSB>
            <geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_Sun>
              <geom:x_velocity/>
              <geom:light_time_correction_applied/>
              <geom:y_velocity/>
              <geom:z_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_Sun>
            <geom:Vector_Cartesian_Velocity_Target_Relative_To_Central_Body>
              <geom:x_velocity/>
              <geom:light_time_correction_applied/>
              <geom:y_velocity/>
              <geom:z_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Velocity_Target_Relative_To_Central_Body>
            <geom:Vector_Cartesian_Velocity_Target_Relative_To_Spacecraft>
              <geom:x_velocity/>
              <geom:light_time_correction_applied/>
              <geom:y_velocity/>
              <geom:z_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Velocity_Target_Relative_To_Spacecraft>
            <geom:Vector_Cartesian_Velocity_Target_Relative_To_Earth>
              <geom:x_velocity/>
              <geom:light_time_correction_applied/>
              <geom:y_velocity/>
              <geom:z_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Velocity_Target_Relative_To_Earth>
            <geom:Vector_Cartesian_Velocity_Target_Relative_To_SSB>
              <geom:x_velocity/>
              <geom:light_time_correction_applied/>
              <geom:y_velocity/>
              <geom:z_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Velocity_Target_Relative_To_SSB>
            <geom:Vector_Cartesian_Velocity_Target_Relative_To_Sun>
              <geom:x_velocity/>
              <geom:light_time_correction_applied/>
              <geom:y_velocity/>
              <geom:z_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Cartesian_Velocity_Target_Relative_To_Sun>
          </geom:Vectors_Cartesian_Specific>
          <geom:Vectors_Planetocentric_Specific>
            <geom:Vector_Planetocentric_Position_Central_Body_To_Spacecraft>
              <geom:radius_position/>
              <geom:light_time_correction_applied/>
              <geom:longitude_position/>
              <geom:latitude_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Planetocentric_Position_Central_Body_To_Spacecraft>
            <geom:Vector_Planetocentric_Position_Central_Body_To_Target>
              <geom:radius_position/>
              <geom:light_time_correction_applied/>
              <geom:longitude_position/>
              <geom:latitude_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Planetocentric_Position_Central_Body_To_Target>
            <geom:Vector_Planetocentric_Position_Spacecraft_To_Target>
              <geom:radius_position/>
              <geom:light_time_correction_applied/>
              <geom:longitude_position/>
              <geom:latitude_position/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Planetocentric_Position_Spacecraft_To_Target>
            <geom:Vector_Planetocentric_Velocity_Spacecraft_Relative_To_Target>
              <geom:radial_velocity/>
              <geom:light_time_correction_applied/>
              <geom:longitude_velocity/>
              <geom:latitude_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Planetocentric_Velocity_Spacecraft_Relative_To_Target>
            <geom:Vector_Planetocentric_Velocity_Target_Relative_To_Central_Body>
              <geom:radial_velocity/>
              <geom:light_time_correction_applied/>
              <geom:longitude_velocity/>
              <geom:latitude_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Planetocentric_Velocity_Target_Relative_To_Central_Body>
            <geom:Vector_Planetocentric_Velocity_Target_Relative_To_Spacecraft>
              <geom:radial_velocity/>
              <geom:light_time_correction_applied/>
              <geom:longitude_velocity/>
              <geom:latitude_velocity/>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
            </geom:Vector_Planetocentric_Velocity_Target_Relative_To_Spacecraft>
          </geom:Vectors_Planetocentric_Specific>
          <geom:Generic_Vectors>
            <geom:comment/>
            <geom:Vector_Cartesian_Position_Generic>
              <geom:x_position/>
              <geom:light_time_correction_applied/>
              <geom:y_position/>
              <geom:z_position/>
              <geom:Observer_Identification>
              </geom:Observer_Identification>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
              <geom:Geometry_Target_Identification>
              </geom:Geometry_Target_Identification>
            </geom:Vector_Cartesian_Position_Generic>
            <geom:Vector_Cartesian_Velocity_Generic>
              <geom:x_velocity/>
              <geom:light_time_correction_applied/>
              <geom:y_velocity/>
              <geom:z_velocity/>
              <geom:Observer_Identification>
              </geom:Observer_Identification>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
              <geom:Geometry_Target_Identification>
              </geom:Geometry_Target_Identification>
            </geom:Vector_Cartesian_Velocity_Generic>
            <geom:Vector_Cartesian_Acceleration_Generic>
              <geom:x_acceleration/>
              <geom:light_time_correction_applied/>
              <geom:y_acceleration/>
              <geom:z_acceleration/>
              <geom:Observer_Identification>
              </geom:Observer_Identification>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
              <geom:Geometry_Target_Identification>
              </geom:Geometry_Target_Identification>
            </geom:Vector_Cartesian_Acceleration_Generic>
            <geom:Vector_Planetocentric_Position_Generic>
              <geom:radius_position/>
              <geom:light_time_correction_applied/>
              <geom:longitude_position/>
              <geom:latitude_position/>
              <geom:Observer_Identification>
              </geom:Observer_Identification>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
              <geom:Geometry_Target_Identification>
              </geom:Geometry_Target_Identification>
            </geom:Vector_Planetocentric_Position_Generic>
            <geom:Vector_Planetocentric_Velocity_Generic>
              <geom:radial_velocity/>
              <geom:light_time_correction_applied/>
              <geom:longitude_velocity/>
              <geom:latitude_velocity/>
              <geom:Observer_Identification>
              </geom:Observer_Identification>
              <geom:Coordinate_System_Identification>
              </geom:Coordinate_System_Identification>
              <geom:Geometry_Target_Identification>
              </geom:Geometry_Target_Identification>
            </geom:Vector_Planetocentric_Velocity_Generic>
          </geom:Generic_Vectors>
        </geom:Vectors>
        <geom:Quaternion_Plus_To_From>
        </geom:Quaternion_Plus_To_From>
      </geom:Geometry_Orbiter>
      <geom:Geometry_Lander>
        <geom:geometry_state/>
        <geom:description/>
        <geom:local_identifier/>
        <geom:Articulation_Device_Parameters>
          <geom:local_identifier/>
          <geom:device_id/>
          <geom:device_name/>
          <geom:device_mode/>
          <geom:device_phase/>
          <geom:selected_instrument_id/>
          <geom:Device_Angle>
            <geom:local_identifier/>
            <geom:Device_Angle_Index>
              <geom:index_value_angle/>
              <geom:index_sequence_number/>
              <geom:index_name/>
              <geom:index_id/>
            </geom:Device_Angle_Index>
          </geom:Device_Angle>
          <geom:Device_Component_State>
            <geom:local_identifier/>
            <geom:Device_Component_State_Index>
              <geom:index_sequence_number/>
              <geom:index_name/>
              <geom:index_id/>
              <geom:index_value_string/>
            </geom:Device_Component_State_Index>
          </geom:Device_Component_State>
          <geom:Device_Motor_Counts>
            <geom:local_identifier/>
            <geom:Device_Motor_Counts_Index>
              <geom:index_sequence_number/>
              <geom:index_name/>
              <geom:index_id/>
              <geom:index_value_number/>
            </geom:Device_Motor_Counts_Index>
          </geom:Device_Motor_Counts>
          <geom:Device_Pose>
            <geom:name/>
            <geom:Quaternion_Plus_Direction>
              <geom:qcos/>
              <geom:qsin1/>
              <geom:rotation_direction/>
              <geom:qsin2/>
              <geom:qsin3/>
            </geom:Quaternion_Plus_Direction>
            <geom:Vector_Origin_Offset>
              <geom:x_position/>
              <geom:y_position/>
              <geom:z_position/>
            </geom:Vector_Origin_Offset>
          </geom:Device_Pose>
          <geom:Vector_Device_Gravity>
            <geom:x_unit/>
            <geom:y_unit/>
            <geom:z_unit/>
          </geom:Vector_Device_Gravity>
          <geom:Vector_Device_Gravity_Magnitude>
            <geom:x_acceleration/>
            <geom:y_acceleration/>
            <geom:z_acceleration/>
          </geom:Vector_Device_Gravity_Magnitude>
          <geom:Device_Temperature>
            <geom:local_identifier/>
            <geom:Device_Temperature_Index>
              <geom:index_sequence_number/>
              <geom:index_name/>
              <geom:index_id/>
              <geom:index_value_temperature/>
              <geom:index_value_number/>
            </geom:Device_Temperature_Index>
          </geom:Device_Temperature>
          <geom:Coordinate_Space_Present>
            <geom:Coordinate_Space_Indexed>
              <geom:coordinate_space_frame_type/>
              <geom:solution_id/>
              <geom:Coordinate_Space_Index>
                <geom:index_sequence_number/>
                <geom:index_name/>
                <geom:index_id/>
                <geom:index_value_number/>
              </geom:Coordinate_Space_Index>
            </geom:Coordinate_Space_Indexed>
            <geom:Coordinate_Space_SPICE>
              <geom:body_spice_name/>
              <geom:frame_spice_name/>
            </geom:Coordinate_Space_SPICE>
            <geom:Local_Internal_Reference>
            </geom:Local_Internal_Reference>
          </geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Reference>
            <geom:Coordinate_Space_Indexed>
            </geom:Coordinate_Space_Indexed>
            <geom:Coordinate_Space_SPICE>
            </geom:Coordinate_Space_SPICE>
            <geom:Local_Internal_Reference>
            </geom:Local_Internal_Reference>
          </geom:Coordinate_Space_Reference>
          <geom:Commanded_Geometry>
            <geom:command_type/>
            <geom:Device_Angle>
            </geom:Device_Angle>
            <geom:Commanded_Position>
              <geom:x_position/>
              <geom:y_position/>
              <geom:z_position/>
            </geom:Commanded_Position>
            <geom:Coordinate_Space_Reference>
            </geom:Coordinate_Space_Reference>
          </geom:Commanded_Geometry>
        </geom:Articulation_Device_Parameters>
        <geom:Camera_Model_Parameters>
          <geom:model_type/>
          <geom:calibration_source_id/>
          <geom:solution_id/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
          <geom:CAHV_Model>
            <geom:Vector_Center>
              <geom:x_position/>
              <geom:y_position/>
              <geom:z_position/>
            </geom:Vector_Center>
            <geom:Vector_Axis>
              <geom:x_unit/>
              <geom:y_unit/>
              <geom:z_unit/>
            </geom:Vector_Axis>
            <geom:Vector_Horizontal>
              <geom:x_pixel/>
              <geom:y_pixel/>
              <geom:z_pixel/>
            </geom:Vector_Horizontal>
            <geom:Vector_Vertical>
              <geom:x_pixel/>
              <geom:y_pixel/>
              <geom:z_pixel/>
            </geom:Vector_Vertical>
          </geom:CAHV_Model>
          <geom:CAHVOR_Model>
            <geom:Vector_Center>
            </geom:Vector_Center>
            <geom:Vector_Optical>
              <geom:x_unit/>
              <geom:y_unit/>
              <geom:z_unit/>
            </geom:Vector_Optical>
            <geom:Radial_Terms>
              <geom:c0/>
              <geom:c1/>
              <geom:c2/>
            </geom:Radial_Terms>
            <geom:Vector_Axis>
            </geom:Vector_Axis>
            <geom:Vector_Horizontal>
            </geom:Vector_Horizontal>
            <geom:Vector_Vertical>
            </geom:Vector_Vertical>
          </geom:CAHVOR_Model>
          <geom:CAHVORE_Model>
            <geom:cahvore_model_type/>
            <geom:cahvore_model_parameter/>
            <geom:Entrance_Terms>
              <geom:c0/>
              <geom:c1/>
              <geom:c2/>
            </geom:Entrance_Terms>
            <geom:Vector_Center>
            </geom:Vector_Center>
            <geom:Vector_Optical>
            </geom:Vector_Optical>
            <geom:Radial_Terms>
            </geom:Radial_Terms>
            <geom:Vector_Axis>
            </geom:Vector_Axis>
            <geom:Vector_Horizontal>
            </geom:Vector_Horizontal>
            <geom:Vector_Vertical>
            </geom:Vector_Vertical>
          </geom:CAHVORE_Model>
          <geom:PSPH_Model>
            <geom:psph_model_scale_x/>
            <geom:psph_model_scale_y/>
            <geom:Vector_Center>
            </geom:Vector_Center>
            <geom:Vector_Axis_X>
              <geom:x_unit/>
              <geom:y_unit/>
              <geom:z_unit/>
            </geom:Vector_Axis_X>
            <geom:Vector_Axis_Y>
              <geom:x_unit/>
              <geom:y_unit/>
              <geom:z_unit/>
            </geom:Vector_Axis_Y>
            <geom:Vector_Normal_X>
              <geom:x_unit/>
              <geom:y_unit/>
              <geom:z_unit/>
            </geom:Vector_Normal_X>
            <geom:Vector_Normal_Y>
              <geom:x_unit/>
              <geom:y_unit/>
              <geom:z_unit/>
            </geom:Vector_Normal_Y>
          </geom:PSPH_Model>
          <geom:Reference_Frame_Identification>
          </geom:Reference_Frame_Identification>
          <geom:Coordinate_Space_Reference>
          </geom:Coordinate_Space_Reference>
          <geom:Quaternion_Model_Transform>
            <geom:qcos/>
            <geom:qsin1/>
            <geom:qsin2/>
            <geom:qsin3/>
          </geom:Quaternion_Model_Transform>
          <geom:Vector_Model_Transform>
            <geom:x/>
            <geom:y/>
            <geom:z/>
          </geom:Vector_Model_Transform>
          <geom:Interpolation>
            <geom:interpolation_algorithm/>
            <geom:interpolation_variable/>
            <geom:interpolation_value/>
            <geom:interpolation_sequence/>
          </geom:Interpolation>
        </geom:Camera_Model_Parameters>
        <geom:Coordinate_Space_Definition>
          <geom:local_identifier/>
          <geom:positive_azimuth_direction/>
          <geom:positive_elevation_direction/>
          <geom:quaternion_measurement_method/>
          <geom:Coordinate_Space_Present>
          </geom:Coordinate_Space_Present>
          <geom:Vector_Origin_Offset>
          </geom:Vector_Origin_Offset>
          <geom:Quaternion_Plus_Direction>
          </geom:Quaternion_Plus_Direction>
          <geom:Coordinate_Space_Reference>
          </geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Quality>
            <geom:quaternion_measurement_method/>
            <geom:attitude_propagation_counter/>
            <geom:attitude_propagation_duration/>
          </geom:Coordinate_Space_Quality>
        </geom:Coordinate_Space_Definition>
        <geom:Derived_Geometry>
          <geom:target_name/>
          <geom:incidence_angle/>
          <geom:emission_angle/>
          <geom:phase_angle/>
          <geom:instrument_azimuth/>
          <geom:instrument_elevation/>
          <geom:solar_azimuth/>
          <geom:solar_elevation/>
          <geom:start_azimuth/>
          <geom:stop_azimuth/>
          <geom:target_heliocentric_distance/>
          <geom:solar_image_clock_angle/>
          <geom:Vector_Solar_Direction>
            <geom:x_unit/>
            <geom:y_unit/>
            <geom:z_unit/>
          </geom:Vector_Solar_Direction>
          <geom:Coordinate_Space_Reference>
          </geom:Coordinate_Space_Reference>
        </geom:Derived_Geometry>
        <geom:Motion_Counter>
          <geom:name/>
          <geom:local_identifier/>
          <geom:Motion_Counter_Index>
            <geom:index_sequence_number/>
            <geom:index_name/>
            <geom:index_id/>
            <geom:index_value_number/>
          </geom:Motion_Counter_Index>
        </geom:Motion_Counter>
      </geom:Geometry_Lander>
    </geom:Geometry>
    <geom:List_Index_Angle>
      <geom:index_value_angle/>
      <geom:index_sequence_number/>
      <geom:index_name/>
      <geom:index_id/>
    </geom:List_Index_Angle>
    <geom:List_Index_Base>
      <geom:index_sequence_number/>
      <geom:index_name/>
      <geom:index_id/>
    </geom:List_Index_Base>
    <geom:List_Index_Length>
      <geom:index_sequence_number/>
      <geom:index_name/>
      <geom:index_id/>
      <geom:index_value_length/>
    </geom:List_Index_Length>
    <geom:List_Index_No_Units>
      <geom:index_sequence_number/>
      <geom:index_name/>
      <geom:index_id/>
      <geom:index_value_number/>
    </geom:List_Index_No_Units>
    <geom:List_Index_Temperature>
      <geom:index_sequence_number/>
      <geom:index_name/>
      <geom:index_id/>
      <geom:index_value_temperature/>
      <geom:index_value_number/>
    </geom:List_Index_Temperature>
    <geom:List_Index_Text>
      <geom:index_sequence_number/>
      <geom:index_name/>
      <geom:index_id/>
      <geom:index_value_string/>
    </geom:List_Index_Text>
    <geom:Polynomial_Coefficients_1>
      <geom:c0/>
    </geom:Polynomial_Coefficients_1>
    <geom:Polynomial_Coefficients_2>
      <geom:c0/>
      <geom:c1/>
    </geom:Polynomial_Coefficients_2>
    <geom:Polynomial_Coefficients_3>
      <geom:c0/>
      <geom:c1/>
      <geom:c2/>
    </geom:Polynomial_Coefficients_3>
    <geom:Vector_Cartesian_Acceleration_Base>
      <geom:x_acceleration/>
      <geom:y_acceleration/>
      <geom:z_acceleration/>
    </geom:Vector_Cartesian_Acceleration_Base>
    <geom:Vector_Cartesian_Acceleration_Extended_Base>
      <geom:x_acceleration/>
      <geom:light_time_correction_applied/>
      <geom:y_acceleration/>
      <geom:z_acceleration/>
      <geom:Coordinate_System_Identification>
        <geom:coordinate_system_type/>
        <geom:coordinate_system_time_utc/>
        <geom:comment/>
        <geom:Coordinate_System_Origin_Identification>
          <geom:local_identifier/>
          <geom:body_spice_name/>
          <geom:name/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Coordinate_System_Origin_Identification>
        <geom:Reference_Frame_Identification>
          <geom:local_identifier/>
          <geom:frame_spice_name/>
          <geom:name/>
          <geom:comment/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Reference_Frame_Identification>
      </geom:Coordinate_System_Identification>
    </geom:Vector_Cartesian_Acceleration_Extended_Base>
    <geom:Vector_Cartesian_No_Units>
      <geom:x/>
      <geom:y/>
      <geom:z/>
    </geom:Vector_Cartesian_No_Units>
    <geom:Vector_Cartesian_Pixel>
      <geom:x_pixel/>
      <geom:y_pixel/>
      <geom:z_pixel/>
    </geom:Vector_Cartesian_Pixel>
    <geom:Vector_Cartesian_Position_Base>
      <geom:x_position/>
      <geom:y_position/>
      <geom:z_position/>
    </geom:Vector_Cartesian_Position_Base>
    <geom:Vector_Cartesian_Position_Extended_Base>
      <geom:x_position/>
      <geom:light_time_correction_applied/>
      <geom:y_position/>
      <geom:z_position/>
      <geom:Coordinate_System_Identification>
        <geom:coordinate_system_type/>
        <geom:coordinate_system_time_utc/>
        <geom:comment/>
        <geom:Coordinate_System_Origin_Identification>
          <geom:local_identifier/>
          <geom:body_spice_name/>
          <geom:name/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Coordinate_System_Origin_Identification>
        <geom:Reference_Frame_Identification>
          <geom:local_identifier/>
          <geom:frame_spice_name/>
          <geom:name/>
          <geom:comment/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Reference_Frame_Identification>
      </geom:Coordinate_System_Identification>
    </geom:Vector_Cartesian_Position_Extended_Base>
    <geom:Vector_Cartesian_Unit>
      <geom:x_unit/>
      <geom:y_unit/>
      <geom:z_unit/>
    </geom:Vector_Cartesian_Unit>
    <geom:Vector_Cartesian_Velocity_Base>
      <geom:x_velocity/>
      <geom:y_velocity/>
      <geom:z_velocity/>
    </geom:Vector_Cartesian_Velocity_Base>
    <geom:Vector_Cartesian_Velocity_Extended_Base>
      <geom:x_velocity/>
      <geom:light_time_correction_applied/>
      <geom:y_velocity/>
      <geom:z_velocity/>
      <geom:Coordinate_System_Identification>
        <geom:coordinate_system_type/>
        <geom:coordinate_system_time_utc/>
        <geom:comment/>
        <geom:Coordinate_System_Origin_Identification>
          <geom:local_identifier/>
          <geom:body_spice_name/>
          <geom:name/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Coordinate_System_Origin_Identification>
        <geom:Reference_Frame_Identification>
          <geom:local_identifier/>
          <geom:frame_spice_name/>
          <geom:name/>
          <geom:comment/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Reference_Frame_Identification>
      </geom:Coordinate_System_Identification>
    </geom:Vector_Cartesian_Velocity_Extended_Base>
    <geom:Vector_Planetocentric_Position_Base>
      <geom:radius_position/>
      <geom:longitude_position/>
      <geom:latitude_position/>
    </geom:Vector_Planetocentric_Position_Base>
    <geom:Vector_Planetocentric_Position_Extended_Base>
      <geom:radius_position/>
      <geom:light_time_correction_applied/>
      <geom:longitude_position/>
      <geom:latitude_position/>
      <geom:Coordinate_System_Identification>
        <geom:coordinate_system_type/>
        <geom:coordinate_system_time_utc/>
        <geom:comment/>
        <geom:Coordinate_System_Origin_Identification>
          <geom:local_identifier/>
          <geom:body_spice_name/>
          <geom:name/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Coordinate_System_Origin_Identification>
        <geom:Reference_Frame_Identification>
          <geom:local_identifier/>
          <geom:frame_spice_name/>
          <geom:name/>
          <geom:comment/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Reference_Frame_Identification>
      </geom:Coordinate_System_Identification>
    </geom:Vector_Planetocentric_Position_Extended_Base>
    <geom:Vector_Planetocentric_Velocity_Base>
      <geom:radial_velocity/>
      <geom:longitude_velocity/>
      <geom:latitude_velocity/>
    </geom:Vector_Planetocentric_Velocity_Base>
    <geom:Vector_Planetocentric_Velocity_Extended_Base>
      <geom:radial_velocity/>
      <geom:light_time_correction_applied/>
      <geom:longitude_velocity/>
      <geom:latitude_velocity/>
      <geom:Coordinate_System_Identification>
        <geom:coordinate_system_type/>
        <geom:coordinate_system_time_utc/>
        <geom:comment/>
        <geom:Coordinate_System_Origin_Identification>
          <geom:local_identifier/>
          <geom:body_spice_name/>
          <geom:name/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Coordinate_System_Origin_Identification>
        <geom:Reference_Frame_Identification>
          <geom:local_identifier/>
          <geom:frame_spice_name/>
          <geom:name/>
          <geom:comment/>
          <geom:Internal_Reference>
          </geom:Internal_Reference>
        </geom:Reference_Frame_Identification>
      </geom:Coordinate_System_Identification>
    </geom:Vector_Planetocentric_Velocity_Extended_Base>
  </Discipline_Area>
  ...
</Observation_Area>
```  
  
The namespace for the Geometry Discipline Data Dictionary is http://pds.nasa.gov/pds4/geom/v1, abbreviated "geom:".  
  
# Organization of Classes and Attributes  
  
## Class Organization  
Below is a structured list showing the organization of classes, ordered by appearance in the PDS4 label. Each class name is linked to its complete definition in the [Definitions](#definitions) section.  
- [Coordinate_Space_Identification](#coordinate_space_identification)  
  - [Coordinate_Space_Indexed](#coordinate_space_indexed)  
    - [Coordinate_Space_Index](#coordinate_space_index)  
  - [Coordinate_Space_SPICE](#coordinate_space_spice)  
  - [Local_Internal_Reference](#local_internal_reference)  
- [Geometry](#geometry)  
  - [SPICE_Kernel_Files](#spice_kernel_files)  
    - [SPICE_Kernel_Identification](#spice_kernel_identification)  
      - [Internal_Reference](#internal_reference)  
  - [Expanded_Geometry](#expanded_geometry)  
    - [Local_Internal_Reference](#local_internal_reference)  
    - [Internal_Reference](#internal_reference)  
  - [Image_Display_Geometry](#image_display_geometry)  
    - [Local_Internal_Reference](#local_internal_reference)  
    - [Display_Direction](#display_direction)  
    - [Central_Body_Identification](#central_body_identification)  
      - [Internal_Reference](#internal_reference)  
    - [Geometry_Target_Identification](#geometry_target_identification)  
      - [Internal_Reference](#internal_reference)  
    - [Object_Orientation_North_East](#object_orientation_north_east)  
      - [Reference_Frame_Identification](#reference_frame_identification)  
        - [Internal_Reference](#internal_reference)  
    - [Object_Orientation_RA_Dec](#object_orientation_ra_dec)  
      - [Reference_Pixel](#reference_pixel)  
      - [Reference_Frame_Identification](#reference_frame_identification)  
    - [Object_Orientation_Clock_Angles](#object_orientation_clock_angles)  
    - [Quaternion_Plus_To_From](#quaternion_plus_to_from)  
      - [Rotate_From](#rotate_from)  
        - [Internal_Reference](#internal_reference)  
      - [Rotate_To](#rotate_to)  
        - [Internal_Reference](#internal_reference)  
  - [Geometry_Orbiter](#geometry_orbiter)  
    - [Orbiter_Identification](#orbiter_identification)  
      - [Central_Body_Identification](#central_body_identification)  
      - [Geometry_Target_Identification](#geometry_target_identification)  
      - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Coordinate_System_Origin_Identification](#coordinate_system_origin_identification)  
          - [Internal_Reference](#internal_reference)  
        - [Reference_Frame_Identification](#reference_frame_identification)  
    - [Pixel_Dimensions](#pixel_dimensions)  
      - [Pixel_Size_Projected](#pixel_size_projected)  
    - [Distances](#distances)  
      - [Distances_Specific](#distances_specific)  
      - [Distances_Min_Max](#distances_min_max)  
      - [Distances_Start_Stop](#distances_start_stop)  
      - [Distance_Generic](#distance_generic)  
        - [Observer_Identification](#observer_identification)  
          - [Internal_Reference](#internal_reference)  
        - [Geometry_Target_Identification](#geometry_target_identification)  
    - [Surface_Geometry](#surface_geometry)  
      - [Surface_Geometry_Specific](#surface_geometry_specific)  
        - [Pixel_Intercept](#pixel_intercept)  
          - [Reference_Pixel](#reference_pixel)  
        - [Footprint_Vertices](#footprint_vertices)  
          - [Pixel_Intercept](#pixel_intercept)  
      - [Surface_Geometry_Min_Max](#surface_geometry_min_max)  
      - [Surface_Geometry_Start_Stop](#surface_geometry_start_stop)  
    - [Illumination_Geometry](#illumination_geometry)  
      - [Illumination_Specific](#illumination_specific)  
        - [Reference_Pixel](#reference_pixel)  
      - [Illumination_Min_Max](#illumination_min_max)  
      - [Illumination_Start_Stop](#illumination_start_stop)  
    - [Vectors](#vectors)  
      - [Vectors_Cartesian_Specific](#vectors_cartesian_specific)  
        - [Vector_Cartesian_Position_Central_Body_To_Spacecraft](#vector_cartesian_position_central_body_to_spacecraft)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Position_Central_Body_To_Target](#vector_cartesian_position_central_body_to_target)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Position_Spacecraft_To_Target](#vector_cartesian_position_spacecraft_to_target)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Position_SSB_To_Central_Body](#vector_cartesian_position_ssb_to_central_body)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Position_SSB_To_Spacecraft](#vector_cartesian_position_ssb_to_spacecraft)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Position_SSB_To_Target](#vector_cartesian_position_ssb_to_target)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Position_Sun_To_Central_Body](#vector_cartesian_position_sun_to_central_body)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Position_Sun_To_Spacecraft](#vector_cartesian_position_sun_to_spacecraft)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Position_Sun_To_Target](#vector_cartesian_position_sun_to_target)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Position_Earth_To_Central_Body](#vector_cartesian_position_earth_to_central_body)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Position_Earth_To_Spacecraft](#vector_cartesian_position_earth_to_spacecraft)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Position_Earth_To_Target](#vector_cartesian_position_earth_to_target)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Velocity_Spacecraft_Relative_To_Central_Body](#vector_cartesian_velocity_spacecraft_relative_to_central_body)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Velocity_Spacecraft_Relative_To_Target](#vector_cartesian_velocity_spacecraft_relative_to_target)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Velocity_Spacecraft_Relative_To_Earth](#vector_cartesian_velocity_spacecraft_relative_to_earth)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Velocity_Spacecraft_Relative_To_SSB](#vector_cartesian_velocity_spacecraft_relative_to_ssb)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Velocity_Spacecraft_Relative_To_Sun](#vector_cartesian_velocity_spacecraft_relative_to_sun)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Velocity_Target_Relative_To_Central_Body](#vector_cartesian_velocity_target_relative_to_central_body)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Velocity_Target_Relative_To_Spacecraft](#vector_cartesian_velocity_target_relative_to_spacecraft)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Velocity_Target_Relative_To_Earth](#vector_cartesian_velocity_target_relative_to_earth)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Velocity_Target_Relative_To_SSB](#vector_cartesian_velocity_target_relative_to_ssb)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Cartesian_Velocity_Target_Relative_To_Sun](#vector_cartesian_velocity_target_relative_to_sun)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
      - [Vectors_Planetocentric_Specific](#vectors_planetocentric_specific)  
        - [Vector_Planetocentric_Position_Central_Body_To_Spacecraft](#vector_planetocentric_position_central_body_to_spacecraft)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Planetocentric_Position_Central_Body_To_Target](#vector_planetocentric_position_central_body_to_target)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Planetocentric_Position_Spacecraft_To_Target](#vector_planetocentric_position_spacecraft_to_target)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Planetocentric_Velocity_Spacecraft_Relative_To_Target](#vector_planetocentric_velocity_spacecraft_relative_to_target)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Planetocentric_Velocity_Target_Relative_To_Central_Body](#vector_planetocentric_velocity_target_relative_to_central_body)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
        - [Vector_Planetocentric_Velocity_Target_Relative_To_Spacecraft](#vector_planetocentric_velocity_target_relative_to_spacecraft)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
      - [Generic_Vectors](#generic_vectors)  
        - [Vector_Cartesian_Position_Generic](#vector_cartesian_position_generic)  
          - [Observer_Identification](#observer_identification)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
          - [Geometry_Target_Identification](#geometry_target_identification)  
        - [Vector_Cartesian_Velocity_Generic](#vector_cartesian_velocity_generic)  
          - [Observer_Identification](#observer_identification)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
          - [Geometry_Target_Identification](#geometry_target_identification)  
        - [Vector_Cartesian_Acceleration_Generic](#vector_cartesian_acceleration_generic)  
          - [Observer_Identification](#observer_identification)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
          - [Geometry_Target_Identification](#geometry_target_identification)  
        - [Vector_Planetocentric_Position_Generic](#vector_planetocentric_position_generic)  
          - [Observer_Identification](#observer_identification)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
          - [Geometry_Target_Identification](#geometry_target_identification)  
        - [Vector_Planetocentric_Velocity_Generic](#vector_planetocentric_velocity_generic)  
          - [Observer_Identification](#observer_identification)  
          - [Coordinate_System_Identification](#coordinate_system_identification)  
          - [Geometry_Target_Identification](#geometry_target_identification)  
    - [Quaternion_Plus_To_From](#quaternion_plus_to_from)  
  - [Geometry_Lander](#geometry_lander)  
    - [Articulation_Device_Parameters](#articulation_device_parameters)  
      - [Device_Angle](#device_angle)  
        - [Device_Angle_Index](#device_angle_index)  
      - [Device_Component_State](#device_component_state)  
        - [Device_Component_State_Index](#device_component_state_index)  
      - [Device_Motor_Counts](#device_motor_counts)  
        - [Device_Motor_Counts_Index](#device_motor_counts_index)  
      - [Device_Pose](#device_pose)  
        - [Quaternion_Plus_Direction](#quaternion_plus_direction)  
        - [Vector_Origin_Offset](#vector_origin_offset)  
      - [Vector_Device_Gravity](#vector_device_gravity)  
      - [Vector_Device_Gravity_Magnitude](#vector_device_gravity_magnitude)  
      - [Device_Temperature](#device_temperature)  
        - [Device_Temperature_Index](#device_temperature_index)  
      - [Coordinate_Space_Present](#coordinate_space_present)  
        - [Coordinate_Space_Indexed](#coordinate_space_indexed)  
          - [Coordinate_Space_Index](#coordinate_space_index)  
        - [Coordinate_Space_SPICE](#coordinate_space_spice)  
        - [Local_Internal_Reference](#local_internal_reference)  
      - [Coordinate_Space_Reference](#coordinate_space_reference)  
        - [Coordinate_Space_Indexed](#coordinate_space_indexed)  
        - [Coordinate_Space_SPICE](#coordinate_space_spice)  
        - [Local_Internal_Reference](#local_internal_reference)  
      - [Commanded_Geometry](#commanded_geometry)  
        - [Device_Angle](#device_angle)  
        - [Commanded_Position](#commanded_position)  
        - [Coordinate_Space_Reference](#coordinate_space_reference)  
    - [Camera_Model_Parameters](#camera_model_parameters)  
      - [Internal_Reference](#internal_reference)  
      - [CAHV_Model](#cahv_model)  
        - [Vector_Center](#vector_center)  
        - [Vector_Axis](#vector_axis)  
        - [Vector_Horizontal](#vector_horizontal)  
        - [Vector_Vertical](#vector_vertical)  
      - [CAHVOR_Model](#cahvor_model)  
        - [Vector_Center](#vector_center)  
        - [Vector_Optical](#vector_optical)  
        - [Radial_Terms](#radial_terms)  
        - [Vector_Axis](#vector_axis)  
        - [Vector_Horizontal](#vector_horizontal)  
        - [Vector_Vertical](#vector_vertical)  
      - [CAHVORE_Model](#cahvore_model)  
        - [Entrance_Terms](#entrance_terms)  
        - [Vector_Center](#vector_center)  
        - [Vector_Optical](#vector_optical)  
        - [Radial_Terms](#radial_terms)  
        - [Vector_Axis](#vector_axis)  
        - [Vector_Horizontal](#vector_horizontal)  
        - [Vector_Vertical](#vector_vertical)  
      - [PSPH_Model](#psph_model)  
        - [Vector_Center](#vector_center)  
        - [Vector_Axis_X](#vector_axis_x)  
        - [Vector_Axis_Y](#vector_axis_y)  
        - [Vector_Normal_X](#vector_normal_x)  
        - [Vector_Normal_Y](#vector_normal_y)  
      - [Reference_Frame_Identification](#reference_frame_identification)  
      - [Coordinate_Space_Reference](#coordinate_space_reference)  
      - [Quaternion_Model_Transform](#quaternion_model_transform)  
      - [Vector_Model_Transform](#vector_model_transform)  
      - [Interpolation](#interpolation)  
    - [Coordinate_Space_Definition](#coordinate_space_definition)  
      - [Coordinate_Space_Present](#coordinate_space_present)  
      - [Vector_Origin_Offset](#vector_origin_offset)  
      - [Quaternion_Plus_Direction](#quaternion_plus_direction)  
      - [Coordinate_Space_Reference](#coordinate_space_reference)  
      - [Coordinate_Space_Quality](#coordinate_space_quality)  
    - [Derived_Geometry](#derived_geometry)  
      - [Vector_Solar_Direction](#vector_solar_direction)  
      - [Coordinate_Space_Reference](#coordinate_space_reference)  
    - [Motion_Counter](#motion_counter)  
      - [Motion_Counter_Index](#motion_counter_index)  
- [List_Index_Angle](#list_index_angle)  
- [List_Index_Base](#list_index_base)  
- [List_Index_Length](#list_index_length)  
- [List_Index_No_Units](#list_index_no_units)  
- [List_Index_Temperature](#list_index_temperature)  
- [List_Index_Text](#list_index_text)  
- [Polynomial_Coefficients_1](#polynomial_coefficients_1)  
- [Polynomial_Coefficients_2](#polynomial_coefficients_2)  
- [Polynomial_Coefficients_3](#polynomial_coefficients_3)  
- [Vector_Cartesian_Acceleration_Base](#vector_cartesian_acceleration_base)  
- [Vector_Cartesian_Acceleration_Extended_Base](#vector_cartesian_acceleration_extended_base)  
  - [Coordinate_System_Identification](#coordinate_system_identification)  
    - [Coordinate_System_Origin_Identification](#coordinate_system_origin_identification)  
      - [Internal_Reference](#internal_reference)  
    - [Reference_Frame_Identification](#reference_frame_identification)  
      - [Internal_Reference](#internal_reference)  
- [Vector_Cartesian_No_Units](#vector_cartesian_no_units)  
- [Vector_Cartesian_Pixel](#vector_cartesian_pixel)  
- [Vector_Cartesian_Position_Base](#vector_cartesian_position_base)  
- [Vector_Cartesian_Position_Extended_Base](#vector_cartesian_position_extended_base)  
  - [Coordinate_System_Identification](#coordinate_system_identification)  
    - [Coordinate_System_Origin_Identification](#coordinate_system_origin_identification)  
      - [Internal_Reference](#internal_reference)  
    - [Reference_Frame_Identification](#reference_frame_identification)  
      - [Internal_Reference](#internal_reference)  
- [Vector_Cartesian_Unit](#vector_cartesian_unit)  
- [Vector_Cartesian_Velocity_Base](#vector_cartesian_velocity_base)  
- [Vector_Cartesian_Velocity_Extended_Base](#vector_cartesian_velocity_extended_base)  
  - [Coordinate_System_Identification](#coordinate_system_identification)  
    - [Coordinate_System_Origin_Identification](#coordinate_system_origin_identification)  
      - [Internal_Reference](#internal_reference)  
    - [Reference_Frame_Identification](#reference_frame_identification)  
      - [Internal_Reference](#internal_reference)  
- [Vector_Planetocentric_Position_Base](#vector_planetocentric_position_base)  
- [Vector_Planetocentric_Position_Extended_Base](#vector_planetocentric_position_extended_base)  
  - [Coordinate_System_Identification](#coordinate_system_identification)  
    - [Coordinate_System_Origin_Identification](#coordinate_system_origin_identification)  
      - [Internal_Reference](#internal_reference)  
    - [Reference_Frame_Identification](#reference_frame_identification)  
      - [Internal_Reference](#internal_reference)  
- [Vector_Planetocentric_Velocity_Base](#vector_planetocentric_velocity_base)  
- [Vector_Planetocentric_Velocity_Extended_Base](#vector_planetocentric_velocity_extended_base)  
  - [Coordinate_System_Identification](#coordinate_system_identification)  
    - [Coordinate_System_Origin_Identification](#coordinate_system_origin_identification)  
      - [Internal_Reference](#internal_reference)  
    - [Reference_Frame_Identification](#reference_frame_identification)  
      - [Internal_Reference](#internal_reference)  
  
## Attributes by Class  
The attributes immediately under each class (if any) are listed below. Both classes and attributes are ordered by appearance in the PDS4 label; however, each class is listed only once, even if that class can appear in more than one place in a PDS4 label. Each class and attribute name is linked to its complete definition in the [Definitions](#definitions) section.  
  
### [Coordinate_Space_Identification](#coordinate_space_identification) (attribute list)  
  
### [Coordinate_Space_Indexed](#coordinate_space_indexed) (attribute list)  
- [coordinate_space_frame_type](#coordinate_space_frame_type)  
- [solution_id](#solution_id)  
  
### [Coordinate_Space_Index](#coordinate_space_index) (attribute list)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
- [index_value_number](#index_value_number)  
  
### [Coordinate_Space_SPICE](#coordinate_space_spice) (attribute list)  
- [body_spice_name](#body_spice_name)  
- [frame_spice_name](#frame_spice_name)  
  
### [Local_Internal_Reference](#local_internal_reference) (attribute list)  
  
### [Geometry](#geometry) (attribute list)  
  
### [SPICE_Kernel_Files](#spice_kernel_files) (attribute list)  
- [comment](#comment)  
  
### [SPICE_Kernel_Identification](#spice_kernel_identification) (attribute list)  
- [kernel_type](#kernel_type)  
- [spice_kernel_file_name](#spice_kernel_file_name)  
- [kernel_provenance](#kernel_provenance)  
  
### [Internal_Reference](#internal_reference) (attribute list)  
  
### [Expanded_Geometry](#expanded_geometry) (attribute list)  
  
### [Image_Display_Geometry](#image_display_geometry) (attribute list)  
  
### [Display_Direction](#display_direction) (attribute list)  
- [comment](#comment)  
- [horizontal_display_axis](#horizontal_display_axis)  
- [horizontal_display_direction](#horizontal_display_direction)  
- [vertical_display_axis](#vertical_display_axis)  
- [vertical_display_direction](#vertical_display_direction)  
  
### [Central_Body_Identification](#central_body_identification) (attribute list)  
- [local_identifier](#local_identifier)  
- [body_spice_name](#body_spice_name)  
- [name](#name)  
  
### [Geometry_Target_Identification](#geometry_target_identification) (attribute list)  
- [local_identifier](#local_identifier)  
- [body_spice_name](#body_spice_name)  
- [name](#name)  
  
### [Object_Orientation_North_East](#object_orientation_north_east) (attribute list)  
- [north_azimuth](#north_azimuth)  
- [east_azimuth](#east_azimuth)  
  
### [Reference_Frame_Identification](#reference_frame_identification) (attribute list)  
- [local_identifier](#local_identifier)  
- [frame_spice_name](#frame_spice_name)  
- [name](#name)  
- [comment](#comment)  
  
### [Object_Orientation_RA_Dec](#object_orientation_ra_dec) (attribute list)  
- [reference_pixel_location](#reference_pixel_location)  
- [right_ascension_hour_angle](#right_ascension_hour_angle)  
- [right_ascension_angle](#right_ascension_angle)  
- [declination_angle](#declination_angle)  
- [celestial_north_clock_angle](#celestial_north_clock_angle)  
- [ecliptic_north_clock_angle](#ecliptic_north_clock_angle)  
  
### [Reference_Pixel](#reference_pixel) (attribute list)  
- [vertical_coordinate_pixel](#vertical_coordinate_pixel)  
- [horizontal_coordinate_pixel](#horizontal_coordinate_pixel)  
  
### [Object_Orientation_Clock_Angles](#object_orientation_clock_angles) (attribute list)  
- [celestial_north_clock_angle](#celestial_north_clock_angle)  
- [celestial_east_clock_angle](#celestial_east_clock_angle)  
- [ecliptic_north_clock_angle](#ecliptic_north_clock_angle)  
- [ecliptic_east_clock_angle](#ecliptic_east_clock_angle)  
- [central_body_north_pole_clock_angle](#central_body_north_pole_clock_angle)  
- [central_body_positive_pole_clock_angle](#central_body_positive_pole_clock_angle)  
- [target_north_pole_clock_angle](#target_north_pole_clock_angle)  
- [target_positive_pole_clock_angle](#target_positive_pole_clock_angle)  
- [sun_direction_clock_angle](#sun_direction_clock_angle)  
  
### [Quaternion_Plus_To_From](#quaternion_plus_to_from) (attribute list)  
- [qcos](#qcos)  
- [qsin1](#qsin1)  
- [qsin2](#qsin2)  
- [qsin3](#qsin3)  
  
### [Rotate_From](#rotate_from) (attribute list)  
- [local_identifier](#local_identifier)  
- [frame_spice_name](#frame_spice_name)  
- [name](#name)  
- [comment](#comment)  
  
### [Rotate_To](#rotate_to) (attribute list)  
- [local_identifier](#local_identifier)  
- [frame_spice_name](#frame_spice_name)  
- [name](#name)  
- [comment](#comment)  
  
### [Geometry_Orbiter](#geometry_orbiter) (attribute list)  
- [geometry_reference_time_utc](#geometry_reference_time_utc)  
- [geometry_start_time_utc](#geometry_start_time_utc)  
- [geometry_stop_time_utc](#geometry_stop_time_utc)  
- [geometry_reference_time_tdb](#geometry_reference_time_tdb)  
  
### [Orbiter_Identification](#orbiter_identification) (attribute list)  
  
### [Coordinate_System_Identification](#coordinate_system_identification) (attribute list)  
- [coordinate_system_type](#coordinate_system_type)  
- [coordinate_system_time_utc](#coordinate_system_time_utc)  
- [comment](#comment)  
  
### [Coordinate_System_Origin_Identification](#coordinate_system_origin_identification) (attribute list)  
- [local_identifier](#local_identifier)  
- [body_spice_name](#body_spice_name)  
- [name](#name)  
  
### [Pixel_Dimensions](#pixel_dimensions) (attribute list)  
- [pixel_field_of_view_method](#pixel_field_of_view_method)  
- [horizontal_pixel_field_of_view](#horizontal_pixel_field_of_view)  
- [vertical_pixel_field_of_view](#vertical_pixel_field_of_view)  
  
### [Pixel_Size_Projected](#pixel_size_projected) (attribute list)  
- [reference_location](#reference_location)  
- [distance](#distance)  
- [horizontal_pixel_footprint](#horizontal_pixel_footprint)  
- [vertical_pixel_footprint](#vertical_pixel_footprint)  
  
### [Distances](#distances) (attribute list)  
- [comment](#comment)  
  
### [Distances_Specific](#distances_specific) (attribute list)  
- [spacecraft_geocentric_distance](#spacecraft_geocentric_distance)  
- [spacecraft_heliocentric_distance](#spacecraft_heliocentric_distance)  
- [spacecraft_central_body_distance](#spacecraft_central_body_distance)  
- [spacecraft_target_center_distance](#spacecraft_target_center_distance)  
- [spacecraft_target_boresight_intercept_distance](#spacecraft_target_boresight_intercept_distance)  
- [spacecraft_target_subspacecraft_distance](#spacecraft_target_subspacecraft_distance)  
- [target_geocentric_distance](#target_geocentric_distance)  
- [target_heliocentric_distance](#target_heliocentric_distance)  
- [target_ssb_distance](#target_ssb_distance)  
  
### [Distances_Min_Max](#distances_min_max) (attribute list)  
- [minimum_spacecraft_geocentric_distance](#minimum_spacecraft_geocentric_distance)  
- [maximum_spacecraft_geocentric_distance](#maximum_spacecraft_geocentric_distance)  
- [minimum_spacecraft_heliocentric_distance](#minimum_spacecraft_heliocentric_distance)  
- [maximum_spacecraft_heliocentric_distance](#maximum_spacecraft_heliocentric_distance)  
- [minimum_spacecraft_central_body_distance](#minimum_spacecraft_central_body_distance)  
- [maximum_spacecraft_central_body_distance](#maximum_spacecraft_central_body_distance)  
- [minimum_spacecraft_target_center_distance](#minimum_spacecraft_target_center_distance)  
- [maximum_spacecraft_target_center_distance](#maximum_spacecraft_target_center_distance)  
- [minimum_spacecraft_target_boresight_intercept_distance](#minimum_spacecraft_target_boresight_intercept_distance)  
- [maximum_spacecraft_target_boresight_intercept_distance](#maximum_spacecraft_target_boresight_intercept_distance)  
- [minimum_spacecraft_target_subspacecraft_distance](#minimum_spacecraft_target_subspacecraft_distance)  
- [maximum_spacecraft_target_subspacecraft_distance](#maximum_spacecraft_target_subspacecraft_distance)  
- [minimum_target_geocentric_distance](#minimum_target_geocentric_distance)  
- [maximum_target_geocentric_distance](#maximum_target_geocentric_distance)  
- [minimum_target_heliocentric_distance](#minimum_target_heliocentric_distance)  
- [maximum_target_heliocentric_distance](#maximum_target_heliocentric_distance)  
- [minimum_target_ssb_distance](#minimum_target_ssb_distance)  
- [maximum_target_ssb_distance](#maximum_target_ssb_distance)  
  
### [Distances_Start_Stop](#distances_start_stop) (attribute list)  
- [start_spacecraft_geocentric_distance](#start_spacecraft_geocentric_distance)  
- [stop_spacecraft_geocentric_distance](#stop_spacecraft_geocentric_distance)  
- [start_spacecraft_heliocentric_distance](#start_spacecraft_heliocentric_distance)  
- [stop_spacecraft_heliocentric_distance](#stop_spacecraft_heliocentric_distance)  
- [start_spacecraft_central_body_distance](#start_spacecraft_central_body_distance)  
- [stop_spacecraft_central_body_distance](#stop_spacecraft_central_body_distance)  
- [start_spacecraft_target_center_distance](#start_spacecraft_target_center_distance)  
- [stop_spacecraft_target_center_distance](#stop_spacecraft_target_center_distance)  
- [start_spacecraft_target_boresight_intercept_distance](#start_spacecraft_target_boresight_intercept_distance)  
- [stop_spacecraft_target_boresight_intercept_distance](#stop_spacecraft_target_boresight_intercept_distance)  
- [start_spacecraft_target_subspacecraft_distance](#start_spacecraft_target_subspacecraft_distance)  
- [stop_spacecraft_target_subspacecraft_distance](#stop_spacecraft_target_subspacecraft_distance)  
- [start_target_geocentric_distance](#start_target_geocentric_distance)  
- [stop_target_geocentric_distance](#stop_target_geocentric_distance)  
- [start_target_heliocentric_distance](#start_target_heliocentric_distance)  
- [stop_target_heliocentric_distance](#stop_target_heliocentric_distance)  
- [start_target_ssb_distance](#start_target_ssb_distance)  
- [stop_target_ssb_distance](#stop_target_ssb_distance)  
  
### [Distance_Generic](#distance_generic) (attribute list)  
- [distance](#distance)  
  
### [Observer_Identification](#observer_identification) (attribute list)  
- [local_identifier](#local_identifier)  
- [body_spice_name](#body_spice_name)  
- [name](#name)  
  
### [Surface_Geometry](#surface_geometry) (attribute list)  
- [comment](#comment)  
  
### [Surface_Geometry_Specific](#surface_geometry_specific) (attribute list)  
- [subsolar_azimuth](#subsolar_azimuth)  
- [subsolar_latitude](#subsolar_latitude)  
- [subsolar_longitude](#subsolar_longitude)  
- [subspacecraft_azimuth](#subspacecraft_azimuth)  
- [subspacecraft_latitude](#subspacecraft_latitude)  
- [subspacecraft_longitude](#subspacecraft_longitude)  
  
### [Pixel_Intercept](#pixel_intercept) (attribute list)  
- [reference_pixel_location](#reference_pixel_location)  
- [pixel_latitude](#pixel_latitude)  
- [pixel_longitude](#pixel_longitude)  
  
### [Footprint_Vertices](#footprint_vertices) (attribute list)  
  
### [Surface_Geometry_Min_Max](#surface_geometry_min_max) (attribute list)  
- [minimum_latitude](#minimum_latitude)  
- [maximum_latitude](#maximum_latitude)  
- [minimum_longitude](#minimum_longitude)  
- [maximum_longitude](#maximum_longitude)  
- [minimum_subsolar_azimuth](#minimum_subsolar_azimuth)  
- [maximum_subsolar_azimuth](#maximum_subsolar_azimuth)  
- [minimum_subsolar_latitude](#minimum_subsolar_latitude)  
- [maximum_subsolar_latitude](#maximum_subsolar_latitude)  
- [minimum_subsolar_longitude](#minimum_subsolar_longitude)  
- [maximum_subsolar_longitude](#maximum_subsolar_longitude)  
- [minimum_subspacecraft_azimuth](#minimum_subspacecraft_azimuth)  
- [maximum_subspacecraft_azimuth](#maximum_subspacecraft_azimuth)  
- [minimum_subspacecraft_latitude](#minimum_subspacecraft_latitude)  
- [maximum_subspacecraft_latitude](#maximum_subspacecraft_latitude)  
- [minimum_subspacecraft_longitude](#minimum_subspacecraft_longitude)  
- [maximum_subspacecraft_longitude](#maximum_subspacecraft_longitude)  
  
### [Surface_Geometry_Start_Stop](#surface_geometry_start_stop) (attribute list)  
- [lat_long_method](#lat_long_method)  
- [start_latitude](#start_latitude)  
- [stop_latitude](#stop_latitude)  
- [start_longitude](#start_longitude)  
- [stop_longitude](#stop_longitude)  
- [start_subsolar_azimuth](#start_subsolar_azimuth)  
- [stop_subsolar_azimuth](#stop_subsolar_azimuth)  
- [start_subsolar_latitude](#start_subsolar_latitude)  
- [stop_subsolar_latitude](#stop_subsolar_latitude)  
- [start_subsolar_longitude](#start_subsolar_longitude)  
- [stop_subsolar_longitude](#stop_subsolar_longitude)  
- [start_subspacecraft_azimuth](#start_subspacecraft_azimuth)  
- [stop_subspacecraft_azimuth](#stop_subspacecraft_azimuth)  
- [start_subspacecraft_latitude](#start_subspacecraft_latitude)  
- [stop_subspacecraft_latitude](#stop_subspacecraft_latitude)  
- [start_subspacecraft_longitude](#start_subspacecraft_longitude)  
- [stop_subspacecraft_longitude](#stop_subspacecraft_longitude)  
  
### [Illumination_Geometry](#illumination_geometry) (attribute list)  
- [comment](#comment)  
  
### [Illumination_Specific](#illumination_specific) (attribute list)  
- [reference_location](#reference_location)  
- [reference_pixel_location](#reference_pixel_location)  
- [emission_angle](#emission_angle)  
- [incidence_angle](#incidence_angle)  
- [phase_angle](#phase_angle)  
- [solar_elongation](#solar_elongation)  
  
### [Illumination_Min_Max](#illumination_min_max) (attribute list)  
- [minimum_emission_angle](#minimum_emission_angle)  
- [maximum_emission_angle](#maximum_emission_angle)  
- [minimum_incidence_angle](#minimum_incidence_angle)  
- [maximum_incidence_angle](#maximum_incidence_angle)  
- [minimum_phase_angle](#minimum_phase_angle)  
- [maximum_phase_angle](#maximum_phase_angle)  
- [minimum_solar_elongation](#minimum_solar_elongation)  
- [maximum_solar_elongation](#maximum_solar_elongation)  
  
### [Illumination_Start_Stop](#illumination_start_stop) (attribute list)  
- [start_emission_angle](#start_emission_angle)  
- [stop_emission_angle](#stop_emission_angle)  
- [start_incidence_angle](#start_incidence_angle)  
- [stop_incidence_angle](#stop_incidence_angle)  
- [start_phase_angle](#start_phase_angle)  
- [stop_phase_angle](#stop_phase_angle)  
- [start_solar_elongation](#start_solar_elongation)  
- [stop_solar_elongation](#stop_solar_elongation)  
  
### [Vectors](#vectors) (attribute list)  
- [comment](#comment)  
  
### [Vectors_Cartesian_Specific](#vectors_cartesian_specific) (attribute list)  
  
### [Vector_Cartesian_Position_Central_Body_To_Spacecraft](#vector_cartesian_position_central_body_to_spacecraft) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_Central_Body_To_Target](#vector_cartesian_position_central_body_to_target) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_Spacecraft_To_Target](#vector_cartesian_position_spacecraft_to_target) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_SSB_To_Central_Body](#vector_cartesian_position_ssb_to_central_body) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_SSB_To_Spacecraft](#vector_cartesian_position_ssb_to_spacecraft) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_SSB_To_Target](#vector_cartesian_position_ssb_to_target) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_Sun_To_Central_Body](#vector_cartesian_position_sun_to_central_body) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_Sun_To_Spacecraft](#vector_cartesian_position_sun_to_spacecraft) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_Sun_To_Target](#vector_cartesian_position_sun_to_target) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_Earth_To_Central_Body](#vector_cartesian_position_earth_to_central_body) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_Earth_To_Spacecraft](#vector_cartesian_position_earth_to_spacecraft) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_Earth_To_Target](#vector_cartesian_position_earth_to_target) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Velocity_Spacecraft_Relative_To_Central_Body](#vector_cartesian_velocity_spacecraft_relative_to_central_body) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Cartesian_Velocity_Spacecraft_Relative_To_Target](#vector_cartesian_velocity_spacecraft_relative_to_target) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Cartesian_Velocity_Spacecraft_Relative_To_Earth](#vector_cartesian_velocity_spacecraft_relative_to_earth) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Cartesian_Velocity_Spacecraft_Relative_To_SSB](#vector_cartesian_velocity_spacecraft_relative_to_ssb) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Cartesian_Velocity_Spacecraft_Relative_To_Sun](#vector_cartesian_velocity_spacecraft_relative_to_sun) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Cartesian_Velocity_Target_Relative_To_Central_Body](#vector_cartesian_velocity_target_relative_to_central_body) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Cartesian_Velocity_Target_Relative_To_Spacecraft](#vector_cartesian_velocity_target_relative_to_spacecraft) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Cartesian_Velocity_Target_Relative_To_Earth](#vector_cartesian_velocity_target_relative_to_earth) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Cartesian_Velocity_Target_Relative_To_SSB](#vector_cartesian_velocity_target_relative_to_ssb) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Cartesian_Velocity_Target_Relative_To_Sun](#vector_cartesian_velocity_target_relative_to_sun) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vectors_Planetocentric_Specific](#vectors_planetocentric_specific) (attribute list)  
  
### [Vector_Planetocentric_Position_Central_Body_To_Spacecraft](#vector_planetocentric_position_central_body_to_spacecraft) (attribute list)  
- [radius_position](#radius_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [longitude_position](#longitude_position)  
- [latitude_position](#latitude_position)  
  
### [Vector_Planetocentric_Position_Central_Body_To_Target](#vector_planetocentric_position_central_body_to_target) (attribute list)  
- [radius_position](#radius_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [longitude_position](#longitude_position)  
- [latitude_position](#latitude_position)  
  
### [Vector_Planetocentric_Position_Spacecraft_To_Target](#vector_planetocentric_position_spacecraft_to_target) (attribute list)  
- [radius_position](#radius_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [longitude_position](#longitude_position)  
- [latitude_position](#latitude_position)  
  
### [Vector_Planetocentric_Velocity_Spacecraft_Relative_To_Target](#vector_planetocentric_velocity_spacecraft_relative_to_target) (attribute list)  
- [radial_velocity](#radial_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [longitude_velocity](#longitude_velocity)  
- [latitude_velocity](#latitude_velocity)  
  
### [Vector_Planetocentric_Velocity_Target_Relative_To_Central_Body](#vector_planetocentric_velocity_target_relative_to_central_body) (attribute list)  
- [radial_velocity](#radial_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [longitude_velocity](#longitude_velocity)  
- [latitude_velocity](#latitude_velocity)  
  
### [Vector_Planetocentric_Velocity_Target_Relative_To_Spacecraft](#vector_planetocentric_velocity_target_relative_to_spacecraft) (attribute list)  
- [radial_velocity](#radial_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [longitude_velocity](#longitude_velocity)  
- [latitude_velocity](#latitude_velocity)  
  
### [Generic_Vectors](#generic_vectors) (attribute list)  
- [comment](#comment)  
  
### [Vector_Cartesian_Position_Generic](#vector_cartesian_position_generic) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Velocity_Generic](#vector_cartesian_velocity_generic) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Cartesian_Acceleration_Generic](#vector_cartesian_acceleration_generic) (attribute list)  
- [x_acceleration](#x_acceleration)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_acceleration](#y_acceleration)  
- [z_acceleration](#z_acceleration)  
  
### [Vector_Planetocentric_Position_Generic](#vector_planetocentric_position_generic) (attribute list)  
- [radius_position](#radius_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [longitude_position](#longitude_position)  
- [latitude_position](#latitude_position)  
  
### [Vector_Planetocentric_Velocity_Generic](#vector_planetocentric_velocity_generic) (attribute list)  
- [radial_velocity](#radial_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [longitude_velocity](#longitude_velocity)  
- [latitude_velocity](#latitude_velocity)  
  
### [Geometry_Lander](#geometry_lander) (attribute list)  
- [geometry_state](#geometry_state)  
- [description](#description)  
- [local_identifier](#local_identifier)  
  
### [Articulation_Device_Parameters](#articulation_device_parameters) (attribute list)  
- [local_identifier](#local_identifier)  
- [device_id](#device_id)  
- [device_name](#device_name)  
- [device_mode](#device_mode)  
- [device_phase](#device_phase)  
- [selected_instrument_id](#selected_instrument_id)  
  
### [Device_Angle](#device_angle) (attribute list)  
- [local_identifier](#local_identifier)  
  
### [Device_Angle_Index](#device_angle_index) (attribute list)  
- [index_value_angle](#index_value_angle)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
  
### [Device_Component_State](#device_component_state) (attribute list)  
- [local_identifier](#local_identifier)  
  
### [Device_Component_State_Index](#device_component_state_index) (attribute list)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
- [index_value_string](#index_value_string)  
  
### [Device_Motor_Counts](#device_motor_counts) (attribute list)  
- [local_identifier](#local_identifier)  
  
### [Device_Motor_Counts_Index](#device_motor_counts_index) (attribute list)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
- [index_value_number](#index_value_number)  
  
### [Device_Pose](#device_pose) (attribute list)  
- [name](#name)  
  
### [Quaternion_Plus_Direction](#quaternion_plus_direction) (attribute list)  
- [qcos](#qcos)  
- [qsin1](#qsin1)  
- [rotation_direction](#rotation_direction)  
- [qsin2](#qsin2)  
- [qsin3](#qsin3)  
  
### [Vector_Origin_Offset](#vector_origin_offset) (attribute list)  
- [x_position](#x_position)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Device_Gravity](#vector_device_gravity) (attribute list)  
- [x_unit](#x_unit)  
- [y_unit](#y_unit)  
- [z_unit](#z_unit)  
  
### [Vector_Device_Gravity_Magnitude](#vector_device_gravity_magnitude) (attribute list)  
- [x_acceleration](#x_acceleration)  
- [y_acceleration](#y_acceleration)  
- [z_acceleration](#z_acceleration)  
  
### [Device_Temperature](#device_temperature) (attribute list)  
- [local_identifier](#local_identifier)  
  
### [Device_Temperature_Index](#device_temperature_index) (attribute list)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
- [index_value_temperature](#index_value_temperature)  
- [index_value_number](#index_value_number)  
  
### [Coordinate_Space_Present](#coordinate_space_present) (attribute list)  
  
### [Coordinate_Space_Reference](#coordinate_space_reference) (attribute list)  
  
### [Commanded_Geometry](#commanded_geometry) (attribute list)  
- [command_type](#command_type)  
  
### [Commanded_Position](#commanded_position) (attribute list)  
- [x_position](#x_position)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Camera_Model_Parameters](#camera_model_parameters) (attribute list)  
- [model_type](#model_type)  
- [calibration_source_id](#calibration_source_id)  
- [solution_id](#solution_id)  
  
### [CAHV_Model](#cahv_model) (attribute list)  
  
### [Vector_Center](#vector_center) (attribute list)  
- [x_position](#x_position)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Axis](#vector_axis) (attribute list)  
- [x_unit](#x_unit)  
- [y_unit](#y_unit)  
- [z_unit](#z_unit)  
  
### [Vector_Horizontal](#vector_horizontal) (attribute list)  
- [x_pixel](#x_pixel)  
- [y_pixel](#y_pixel)  
- [z_pixel](#z_pixel)  
  
### [Vector_Vertical](#vector_vertical) (attribute list)  
- [x_pixel](#x_pixel)  
- [y_pixel](#y_pixel)  
- [z_pixel](#z_pixel)  
  
### [CAHVOR_Model](#cahvor_model) (attribute list)  
  
### [Vector_Optical](#vector_optical) (attribute list)  
- [x_unit](#x_unit)  
- [y_unit](#y_unit)  
- [z_unit](#z_unit)  
  
### [Radial_Terms](#radial_terms) (attribute list)  
- [c0](#c0)  
- [c1](#c1)  
- [c2](#c2)  
  
### [CAHVORE_Model](#cahvore_model) (attribute list)  
- [cahvore_model_type](#cahvore_model_type)  
- [cahvore_model_parameter](#cahvore_model_parameter)  
  
### [Entrance_Terms](#entrance_terms) (attribute list)  
- [c0](#c0)  
- [c1](#c1)  
- [c2](#c2)  
  
### [PSPH_Model](#psph_model) (attribute list)  
- [psph_model_scale_x](#psph_model_scale_x)  
- [psph_model_scale_y](#psph_model_scale_y)  
  
### [Vector_Axis_X](#vector_axis_x) (attribute list)  
- [x_unit](#x_unit)  
- [y_unit](#y_unit)  
- [z_unit](#z_unit)  
  
### [Vector_Axis_Y](#vector_axis_y) (attribute list)  
- [x_unit](#x_unit)  
- [y_unit](#y_unit)  
- [z_unit](#z_unit)  
  
### [Vector_Normal_X](#vector_normal_x) (attribute list)  
- [x_unit](#x_unit)  
- [y_unit](#y_unit)  
- [z_unit](#z_unit)  
  
### [Vector_Normal_Y](#vector_normal_y) (attribute list)  
- [x_unit](#x_unit)  
- [y_unit](#y_unit)  
- [z_unit](#z_unit)  
  
### [Quaternion_Model_Transform](#quaternion_model_transform) (attribute list)  
- [qcos](#qcos)  
- [qsin1](#qsin1)  
- [qsin2](#qsin2)  
- [qsin3](#qsin3)  
  
### [Vector_Model_Transform](#vector_model_transform) (attribute list)  
- [x](#x)  
- [y](#y)  
- [z](#z)  
  
### [Interpolation](#interpolation) (attribute list)  
- [interpolation_algorithm](#interpolation_algorithm)  
- [interpolation_variable](#interpolation_variable)  
- [interpolation_value](#interpolation_value)  
- [interpolation_sequence](#interpolation_sequence)  
  
### [Coordinate_Space_Definition](#coordinate_space_definition) (attribute list)  
- [local_identifier](#local_identifier)  
- [positive_azimuth_direction](#positive_azimuth_direction)  
- [positive_elevation_direction](#positive_elevation_direction)  
- [quaternion_measurement_method](#quaternion_measurement_method)  
  
### [Coordinate_Space_Quality](#coordinate_space_quality) (attribute list)  
- [quaternion_measurement_method](#quaternion_measurement_method)  
- [attitude_propagation_counter](#attitude_propagation_counter)  
- [attitude_propagation_duration](#attitude_propagation_duration)  
  
### [Derived_Geometry](#derived_geometry) (attribute list)  
- [target_name](#target_name)  
- [incidence_angle](#incidence_angle)  
- [emission_angle](#emission_angle)  
- [phase_angle](#phase_angle)  
- [instrument_azimuth](#instrument_azimuth)  
- [instrument_elevation](#instrument_elevation)  
- [solar_azimuth](#solar_azimuth)  
- [solar_elevation](#solar_elevation)  
- [start_azimuth](#start_azimuth)  
- [stop_azimuth](#stop_azimuth)  
- [target_heliocentric_distance](#target_heliocentric_distance)  
- [solar_image_clock_angle](#solar_image_clock_angle)  
  
### [Vector_Solar_Direction](#vector_solar_direction) (attribute list)  
- [x_unit](#x_unit)  
- [y_unit](#y_unit)  
- [z_unit](#z_unit)  
  
### [Motion_Counter](#motion_counter) (attribute list)  
- [name](#name)  
- [local_identifier](#local_identifier)  
  
### [Motion_Counter_Index](#motion_counter_index) (attribute list)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
- [index_value_number](#index_value_number)  
  
### [List_Index_Angle](#list_index_angle) (attribute list)  
- [index_value_angle](#index_value_angle)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
  
### [List_Index_Base](#list_index_base) (attribute list)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
  
### [List_Index_Length](#list_index_length) (attribute list)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
- [index_value_length](#index_value_length)  
  
### [List_Index_No_Units](#list_index_no_units) (attribute list)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
- [index_value_number](#index_value_number)  
  
### [List_Index_Temperature](#list_index_temperature) (attribute list)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
- [index_value_temperature](#index_value_temperature)  
- [index_value_number](#index_value_number)  
  
### [List_Index_Text](#list_index_text) (attribute list)  
- [index_sequence_number](#index_sequence_number)  
- [index_name](#index_name)  
- [index_id](#index_id)  
- [index_value_string](#index_value_string)  
  
### [Polynomial_Coefficients_1](#polynomial_coefficients_1) (attribute list)  
- [c0](#c0)  
  
### [Polynomial_Coefficients_2](#polynomial_coefficients_2) (attribute list)  
- [c0](#c0)  
- [c1](#c1)  
  
### [Polynomial_Coefficients_3](#polynomial_coefficients_3) (attribute list)  
- [c0](#c0)  
- [c1](#c1)  
- [c2](#c2)  
  
### [Vector_Cartesian_Acceleration_Base](#vector_cartesian_acceleration_base) (attribute list)  
- [x_acceleration](#x_acceleration)  
- [y_acceleration](#y_acceleration)  
- [z_acceleration](#z_acceleration)  
  
### [Vector_Cartesian_Acceleration_Extended_Base](#vector_cartesian_acceleration_extended_base) (attribute list)  
- [x_acceleration](#x_acceleration)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_acceleration](#y_acceleration)  
- [z_acceleration](#z_acceleration)  
  
### [Vector_Cartesian_No_Units](#vector_cartesian_no_units) (attribute list)  
- [x](#x)  
- [y](#y)  
- [z](#z)  
  
### [Vector_Cartesian_Pixel](#vector_cartesian_pixel) (attribute list)  
- [x_pixel](#x_pixel)  
- [y_pixel](#y_pixel)  
- [z_pixel](#z_pixel)  
  
### [Vector_Cartesian_Position_Base](#vector_cartesian_position_base) (attribute list)  
- [x_position](#x_position)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Position_Extended_Base](#vector_cartesian_position_extended_base) (attribute list)  
- [x_position](#x_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_position](#y_position)  
- [z_position](#z_position)  
  
### [Vector_Cartesian_Unit](#vector_cartesian_unit) (attribute list)  
- [x_unit](#x_unit)  
- [y_unit](#y_unit)  
- [z_unit](#z_unit)  
  
### [Vector_Cartesian_Velocity_Base](#vector_cartesian_velocity_base) (attribute list)  
- [x_velocity](#x_velocity)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Cartesian_Velocity_Extended_Base](#vector_cartesian_velocity_extended_base) (attribute list)  
- [x_velocity](#x_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [y_velocity](#y_velocity)  
- [z_velocity](#z_velocity)  
  
### [Vector_Planetocentric_Position_Base](#vector_planetocentric_position_base) (attribute list)  
- [radius_position](#radius_position)  
- [longitude_position](#longitude_position)  
- [latitude_position](#latitude_position)  
  
### [Vector_Planetocentric_Position_Extended_Base](#vector_planetocentric_position_extended_base) (attribute list)  
- [radius_position](#radius_position)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [longitude_position](#longitude_position)  
- [latitude_position](#latitude_position)  
  
### [Vector_Planetocentric_Velocity_Base](#vector_planetocentric_velocity_base) (attribute list)  
- [radial_velocity](#radial_velocity)  
- [longitude_velocity](#longitude_velocity)  
- [latitude_velocity](#latitude_velocity)  
  
### [Vector_Planetocentric_Velocity_Extended_Base](#vector_planetocentric_velocity_extended_base) (attribute list)  
- [radial_velocity](#radial_velocity)  
- [light_time_correction_applied](#light_time_correction_applied)  
- [longitude_velocity](#longitude_velocity)  
- [latitude_velocity](#latitude_velocity)  
  
# Definitions  
  
## Classes (in alphabetical order)  
  
### Articulation_Device_Parameters  
The Articulation_Device_Parameters class contains those attributes and sub-classes that describe an articulation device. An articulation device is anything that can move independently of the spacecraft to which it is attached. Examples include mast heads, wheel bogies, arms, filter wheel, scan platforms.  
- [go to attribute list](#articulation_device_parameters-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### CAHVORE_Model  
The CAHVORE model is built upon CAHVOR (see CAHVOR_Model), adding support for fisheye lenses. It adds one more 3-vector and two scalars to CAHVOR. E (Entrance_Terms) contains the coefficients of a polynomial function used to model movement of the entrance pupil. The two scalars, cahvore_model_type and cahvore_model_parameter, together specify the type of lens being modeled.  
- [go to attribute list](#cahvore_model-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### CAHVOR_Model  
The CAHVOR model is built upon CAHV (see CAHV_Model), adding radial (barrel or pincushion) distortion to the linear model. It adds two more 3-vectors to CAHV. O (Vector_Optical) is a unit vector representing the axis of symmetry for the radial distortion. R (Radial_Terms) contains the coefficients of a polynomial function that describes the radial distortion.  
- [go to attribute list](#cahvor_model-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### CAHV_Model  
The CAHV model is a linear, perspective-projection camera model (equivalent to a pinhole camera). It consists of four 3-vectors (C,A,H,V) that describe the internal and external camera model parameters needed to translate between 2D image coordinates and 3D world coordinates. C (Vector_Center) is the 3D position of the pinhole (center of the entrance pupil). A (Vector_Axis) is a unit vector normal to the image plane pointing outward. H (Vector_Horizontal) is a composite vector encoding three quantities: H' (a vector in the image plane perpendicular to the vertical columns), Hs (the distance between the lens center and image plane, measured in horizontal pixels), and Hc (the horizontal image coordinate directly under C when moving parallel to A). V (Vector_Vertical) similarly composites the analogous V', Vs, and Vc in the vertical direction.  
- [go to attribute list](#cahv_model-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Camera_Model_Parameters  
A camera model describes the mathematical relationship between the coordinates of a point in 3-dimensional space and its projection onto a 2-dimensional image plane. There are numerous types of camera models.  
- [go to attribute list](#camera_model_parameters-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Central_Body_Identification  
The Central_Body_Identification class uniquely identifies the body that is the central body associated with an observation (e.g., Saturn for Saturn system observations).  
- [go to attribute list](#central_body_identification-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Commanded_Geometry  
 Specifies how the device was commanded in order to achieve the state represented in the enclosing Articulation_Device_Parameters. Commands are often at a higher level, e.g. point at this location or move to this XYZ, which is translated by flight software to the actual pose of the device. Certain forms of command are measured in a coordinate frame; this is specified by the Coordinate_Space_Reference in this class (if not present, the Coordinate_Space_Reference in the Articulation_Device_Parameters parent should be assumed).  
- [go to attribute list](#commanded_geometry-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Commanded_Position  
 Specifies a Cartesian position used in commanding the device.  
- [go to attribute list](#commanded_position-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Coordinate_Space_Definition  
The Coordinate_Space classes are typically used for lander/rover geometry while the Coordinate_System construction is used for orbiter/flyby geometry.  
- [go to attribute list](#coordinate_space_definition-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Coordinate_Space_Identification  
The Coordinate_Space_Identification class uniquely identifies a coordinate space (i.e., reference frame + position) with respect to which the values of the attributes in the containing class are defined.  
- [go to attribute list](#coordinate_space_identification-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Coordinate_Space_Index  
Identifies a coordinate space using an index value given in an identified list.  
- [go to attribute list](#coordinate_space_index-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Coordinate_Space_Indexed  
The Coordinate_Space_Indexed class contains the attributes and classes identifying the indexed coordinate space.  
- [go to attribute list](#coordinate_space_indexed-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Coordinate_Space_Present  
The Coordinate_Space_Present class includes the attributes that identifies the coordinate space presently being defined.  
- [go to attribute list](#coordinate_space_present-attribute-list)  
- in [Articulation_Device_Parameters](#articulation_device_parameters):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
- in [Coordinate_Space_Definition](#coordinate_space_definition):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
  
### Coordinate_Space_Quality  
Parameters that indicate the quality of the coordinate space knowledge.  
- [go to attribute list](#coordinate_space_quality-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Coordinate_Space_Reference  
The Coordinate_Space_Reference class includes the attributes that identify the coordinate space being used to express coordinates in the class in which it appears.  
- [go to attribute list](#coordinate_space_reference-attribute-list)  
- in [Articulation_Device_Parameters](#articulation_device_parameters):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
- in [Camera_Model_Parameters](#camera_model_parameters):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Commanded_Geometry](#commanded_geometry):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Coordinate_Space_Definition](#coordinate_space_definition):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Derived_Geometry](#derived_geometry):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### Coordinate_Space_SPICE  
Identifies a coordinate space using SPICE names for the frame and origin.  
- [go to attribute list](#coordinate_space_spice-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Coordinate_System_Identification  
The Coordinate_System_Identification class fully describes a coordinate system. This class is typically used for orbiter/flyby geometry while the Coordinate_Space construction is used for lander/rover geometry. Coordinate_System_Identification provides the reference frame, coordinate system type (cartesian, planetocentric, etc.), origin, and the instantiation time of the system when appropriate. The instantiation time (coordinate_system_time_utc) is used when a rotating frame has been 'frozen' at a particular epoch. Instantiation time is not needed for inertial or rotating frames.  
- [go to attribute list](#coordinate_system_identification-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Coordinate_System_Origin_Identification  
The Coordinate_System_Origin_Identification class uniquely identifies the "body" that is the origin of a coordinate system. Typically body centered coordinate systems place the origin at the center of mass of the body. In addition to physical bodies, the origin may be defined at a point in space such as a system barycenter. Note that the origin of coordinate system does not necessarily correspond to either end point of a vector.  
- [go to attribute list](#coordinate_system_origin_identification-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Derived_Geometry  
The Derived_Geometry class is a container for surface based observations (lander or rover). It is used to provide some geometric quantities relative to a specific Reference Coordinate Space.  
- [go to attribute list](#derived_geometry-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Device_Angle  
The Device_Angle class is a container for the set of angles between the various components or devices of the spacecraft.  
- [go to attribute list](#device_angle-attribute-list)  
- in [Articulation_Device_Parameters](#articulation_device_parameters):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
- in [Commanded_Geometry](#commanded_geometry):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### Device_Angle_Index  
The Device_Angle class is a container for the set of angles the spacecraft device specified in the parent Articulation_Device_Parameters class.  
- [go to attribute list](#device_angle_index-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Component_State  
The Device_Component_State class is a container for the states of the various components of the articulation device.  
- [go to attribute list](#device_component_state-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Component_State_Index  
The Device_Component_State_Index class is a container for one state of a component of the articulation device.  
- [go to attribute list](#device_component_state_index-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Motor_Counts  
The Device_Motor_Counts class is a container for the classes that describe the motor step count information for device components.  
- [go to attribute list](#device_motor_counts-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Motor_Counts_Index  
The Device_Motor_Counts_Index class is a container for the attributes that describe the motor step count information for a single motor on a device.  
- [go to attribute list](#device_motor_counts_index-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Pose  
Defines the pose of this articulation device. The name indicates what exactly is being measured and how, and disambiguates if there is more than one Device_Pose. For example, Mars 2020 has "arm_attitude_reference", which indicates the pose of the rover that was used to calculate gravity droop of the arm. The interpretation of the pose is mission-specific; see the mission documentation.  
- [go to attribute list](#device_pose-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Temperature  
The Device_Temperature class is a container for all available device temperatures of an articulated device and/or part(s) of a device.  
- [go to attribute list](#device_temperature-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Device_Temperature_Index  
The Device_Temperature_Index class specifies the attributes describing the temperature of one device or some part of a device.  
- [go to attribute list](#device_temperature_index-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Display_Direction  
Note: For all image objects, the expectation is that the image orientation will be given using the disp:Display_Direction class. In the unusual case where an image object does not have an associated disp:Display_Direction class, then, and only then, Display_Direction class defined here should be present. The Display_Direction class specifies which two of the dimensions of an Array object should be displayed and how they should be displayed in the vertical (line) and horizontal (sample) dimensions of a display device. This class is essentially the same as the class of the same name in the Display Dictionary, and is redefined here for convenience.  
- [go to attribute list](#display_direction-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Distance_Generic  
The distance between the two objects, both of which must be specified.  
- [go to attribute list](#distance_generic-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Distances  
The Distances class is a container of distance classes.  
- [go to attribute list](#distances-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Distances_Min_Max  
The Distances_Min_Max class is a container class for named distances given as minimum-maximum pairs. For distance, if either the minimum or maximum parameter is given, both must be provided.  
- [go to attribute list](#distances_min_max-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Distances_Specific  
The Distances_Specific class is a container class for specific distances defined in this dictionary.  
- [go to attribute list](#distances_specific-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Distances_Start_Stop  
The Distances_Start_Stop class is a container class for named distances given as pairs corresponding to the beginning and end of the observation. For a distance, if either the start or stop parameter is given, both must be provided. If any values from this class are included in the label, the parameters geometry_start_time_utc and geometry_stop_time_utc must be given in the enclosing Geometry_Orbiter class.  
- [go to attribute list](#distances_start_stop-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Entrance_Terms  
The Entrance_Terms contains the coefficients of a polynomial function used to model movement of the entrance pupil.  
- [go to attribute list](#entrance_terms-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Expanded_Geometry  
The Expanded_Geometry class provides a mechanism to reference additional geometric metadata contained in a separate object or product (e.g., a table of metadata).  
- [go to attribute list](#expanded_geometry-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Footprint_Vertices  
The Footprint_Vertices class provides a set of latitude and longitude pairs which are the vertices of a polygon representing the projected footprint of the field of view on the target surface (or on a map). Note this is intended for products such as maps, or where the target fills the field of view. The vertices should be listed either in clockwise or counterclockwise order.  
- [go to attribute list](#footprint_vertices-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Generic_Vectors  
The Generic_Vectors class is a container class for all of the build your own vector templates.  
- [go to attribute list](#generic_vectors-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Geometry  
The Geometry class is a container for all geometric information in the label. The Image_Display_Geometry class should have one instance if the primary data object is an Array object for which two of the dimensions are suitable for display in the vertical (line) and horizontal (sample) dimensions of a display device. Multiple instances of the Image_Display_Geometry class are only appropriate if the data product contains multiple Array objects and the orientations of the various objects are not the same.  
- [go to attribute list](#geometry-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Geometry_Lander  
The Geometry_Lander class is a container for all geometric information in the label relating to a landed spacecraft, including rovers.  
- [go to attribute list](#geometry_lander-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Geometry_Orbiter  
The Geometry_Orbiter class is a container for geometric information (positions, velocities, orientations, etc.) relevant to orbiter or flyby spacecraft observations. If any of the contained classes or attributes have central body, and or target in the class or attribute name (e.g., spacecraft_to_central_body_distance, Vector_Planetocentric_Position_Spacecraft_To_Target), then the central body and or target must be identified in this class. If more than one geometry_reference_time_utc, target or central body need to be identified to fully describe the data, use multiple instances of the Geometry_Orbiter class. Do not use Coordinate_System at this level if more than one coordinate system is used in the contained classes. If more than one coordinate system is used, specify Coordinate_System in each of the subordinate classes where it is appropriate.  
- [go to attribute list](#geometry_orbiter-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Geometry_Target_Identification  
The object to which the associated set of geometric parameters are given. Within the Geometry dictionary context, a "Target" is the body on the "to" end of a vector, or other translation through space.  
- [go to attribute list](#geometry_target_identification-attribute-list)  
- in [Distance_Generic](#distance_generic):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Image_Display_Geometry](#image_display_geometry):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Orbiter_Identification](#orbiter_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Vector_Cartesian_Acceleration_Generic](#vector_cartesian_acceleration_generic):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Vector_Cartesian_Position_Generic](#vector_cartesian_position_generic):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Vector_Cartesian_Velocity_Generic](#vector_cartesian_velocity_generic):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Vector_Planetocentric_Position_Generic](#vector_planetocentric_position_generic):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Vector_Planetocentric_Velocity_Generic](#vector_planetocentric_velocity_generic):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
  
### Illumination_Geometry  
The Illumination_Geometry class is a container for illumination geometry classes.  
- [go to attribute list](#illumination_geometry-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Illumination_Min_Max  
The Illumination_Min_Max class contains attributes providing illumination parameters as minimum/maximum pairs. For any given illumination parameter if one of minimum or maximum is given, both must be given. If a target is specified using the Geometry_Target_Identification class in the Orbiter_Identification class under the same parent Geometry_Orbiter class, the min-max pairs for each illumination parameter provide the range of that parameter in the observation on that target. Otherwise the pair provides the range for the entire field of view.  
- [go to attribute list](#illumination_min_max-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Illumination_Specific  
The Illumination_Specific class contains attributes providing illumination parameters at a single location in the field of view. That location is specified by using one, and only one of reference_location, reference_pixel_location, or Reference_Pixel, If reference_location is used, and indicates a point on a target, the target must be the one specified using Geometry_Target_Identification in the parent Geometry_Orbiter class. The provided value for each illumination attribute must correspond to the time given by geometry_reference_time_utc.  
- [go to attribute list](#illumination_specific-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Illumination_Start_Stop  
The Illumination_Start_Stop class contains attributes providing illumination parameters as pairs corresponding to the beginning and end of the observation. If either the start or stop parameter is given, both must be provided. If any values from this class are included in the label, the parameters geometry_start_time_utc and geometry_stop_time_utc must be given in the enclosing Geometry_Orbiter class. If a target is specified using the Geometry_Target_Identification class in the Orbiter_Identification class under the parent Geometry_Orbiter class, the start-stop pairs for each illumination parameter provide the range of that parameter in the observation on that target. Otherwise the pair provides the range for the entire field of view.  
- [go to attribute list](#illumination_start_stop-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Image_Display_Geometry  
Image_Display_Geometry class provides an unambiguous description of the orientation of the image contents. This class assumes an image is displayed as described by a disp:Display_Direction class elsewhere in the label. In the unusual case where an image object does not have an associated disp:Display_Direction class, then, and only then, the optionalgeom:Display_Direction class in this class should be present. Coupled with the information in the associated Display_Direction class, any one of the Object_Orientation_* classes should allow unambiguous orientation of the contents of the image. The Local_Internal_Reference class is used to identify the object to which this instance of the Image_Display_Geometry class applies, and must be used if there is more than one instance of Image_Display_Geometry in the label. The appropriate value for local_reference_type is image_display_to_object. The Object_Orientation_North_East class is typically used for instruments for which the entire field of view is a portion of the target surface (e.g., instruments on Mars orbital spacecraft); otherwise use Object_Orientation_RA_Dec (e.g., flyby missions, missions with orbit radii much larger than the target radius such as Voyager or Cassini). At least one of these must be used. The two *_Identification classes used here are Central_Body (e.g., Saturn if you are using Planetocentric or planetographic coordinates in the Saturn system) and Target when the described object in the FoV is not the Central_Body. For example giving the orientation of the pole of Enceladus in Saturn Planetocentric coordinates, Central_Body = Saturn, Target = Enceladus. Bottom line: put in enough information so someone else can figure out the orientation of the field of view. We also offer an option to provide the pointing information as a quaternion.  
- [go to attribute list](#image_display_geometry-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Internal_Reference  
The Internal_Reference class is used to cross-reference other products in PDS4-compliant registries of PDS and its recognized international partners.  
- [go to attribute list](#internal_reference-attribute-list)  
- in [Camera_Model_Parameters](#camera_model_parameters):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
- in [Central_Body_Identification](#central_body_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Coordinate_System_Origin_Identification](#coordinate_system_origin_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Expanded_Geometry](#expanded_geometry):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
- in [Geometry_Target_Identification](#geometry_target_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Observer_Identification](#observer_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Reference_Frame_Identification](#reference_frame_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Rotate_From](#rotate_from):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Rotate_To](#rotate_to):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [SPICE_Kernel_Identification](#spice_kernel_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### Interpolation  
The Interpolation class defines how the camera model was interpolated from the calibration models. Interpolation is used to create models in a variable space (e.g., focus, zoom) between points at which calibration was performed. If more than one dimension of variables were interpolated, multiple Interpolation objects can exist, with interpolation_sequence defining the order.  
- [go to attribute list](#interpolation-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### List_Index_Angle  
Used when the list values are angles.  
- [go to attribute list](#list_index_angle-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### List_Index_Base  
The List_Index class is an abstract class designed to enable the use of indexed lists. The minimum requirement is at least one of sequence number, name or "id", plus the set of values themselves.  
- [go to attribute list](#list_index_base-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### List_Index_Length  
Used when the list values are lengths.  
- [go to attribute list](#list_index_length-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### List_Index_No_Units  
Used when the list values have no units.  
- [go to attribute list](#list_index_no_units-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### List_Index_Temperature  
Used when the list values are temperatures. They may also have accompanying temperature counts using index_value_number.  
- [go to attribute list](#list_index_temperature-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### List_Index_Text  
Used when the list values are strings.  
- [go to attribute list](#list_index_text-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Local_Internal_Reference  
The Local Internal_Reference class is used to cross-reference other Description Objects in a PDS4 label.  
- [go to attribute list](#local_internal_reference-attribute-list)  
- in [Coordinate_Space_Identification](#coordinate_space_identification):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
- in [Coordinate_Space_Present](#coordinate_space_present):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
- in [Coordinate_Space_Reference](#coordinate_space_reference):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
- in [Expanded_Geometry](#expanded_geometry):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
- in [Image_Display_Geometry](#image_display_geometry):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### Motion_Counter  
The Motion_Counter class provides a set of integers that describe a (potentially) unique location (position / orientation) for a rover or other movable object. Each time an event occurs that results in a movement, a new motion counter value is created. This includes intentional motion due to drive commands, as well as potential motion due to other articulating devices, such as arms or antennae. This motion counter (or part of it) is used as a reference to define instances of coordinate systems that can move such as SITE or ROVER frames. The motion counter is defined in a mission-specific manner. Although the original intent was to have incrementing indices (e.g., MER), the motion counter could also contain any integer values that conform to the above definition, such as time or spacecraft clock values.  
- [go to attribute list](#motion_counter-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Motion_Counter_Index  
The Motion_Counter_Index class identifies and populates one element of a Motion_Counter list. The class should be repeated for each element of the list.  
- [go to attribute list](#motion_counter_index-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Object_Orientation_Clock_Angles  
The Object_Orientation_Clock_Angles class provides several clock angles which can be used to describe the orientation of the field of view with respect to various external references such as Celestial or Equatorial North.  
- [go to attribute list](#object_orientation_clock_angles-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Object_Orientation_North_East  
The Object_Orientation_North_East class provides the parameters needed to describe the orientation of an external coordinate system relative to the image coordinate frame as described by the Display_Direction class.  
- [go to attribute list](#object_orientation_north_east-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Object_Orientation_RA_Dec  
The Object_Orientation_RA_Dec class provides the parameters needed to describe the orientation of the celestial reference frame relative to the image coordinate frame as described by the Display_Direction class.  
- [go to attribute list](#object_orientation_ra_dec-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Observer_Identification  
Within the Geometry dictionary context, an "Observer" is the body on the "from" end of a vector, or other translation through space.  
- [go to attribute list](#observer_identification-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Orbiter_Identification  
The Orbiter_Identification class is a container of classes used to establish global identifications for the Geometry_Orbiter class.  
- [go to attribute list](#orbiter_identification-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### PSPH_Model  
 A new camera model designed to perform better fisheye-image rectification prior to 1D stereo correlation. The primary innovation is the use of a unit projection sphere rather than an image plane. For epipolar alignment between stereo cameras the rows (for a left/right pair) or the columns (for an up/down pair) of both must lie along the same plane. Thus we use a pair of planes to define the rows and columns. Each plane will rotate around a static dedicated axis passing through the sphere center. Pixels will be located where the planes intersect with each other and the unit sphere.  
- [go to attribute list](#psph_model-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Pixel_Dimensions  
The Pixel_Dimensions class contains information regarding pixel size.  
- [go to attribute list](#pixel_dimensions-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Pixel_Intercept  
The Pixel_Intercept class provides the latitude and longitude on the surface of the target for the projection of the specified pixel. The pixel is specified using either reference_pixel_location or Reference_Pixel. Although each of these is optional, one must be used.  
- [go to attribute list](#pixel_intercept-attribute-list)  
- in [Footprint_Vertices](#footprint_vertices):  
  - Minimum occurrences: 2  
  - Maximum occurrences: unbounded  
- in [Surface_Geometry_Specific](#surface_geometry_specific):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
  
### Pixel_Size_Projected  
The Pixel_Size_Projected class gives the size, in units of length (e.g., kilometers) of the projection of a pixel onto the surface of the target which is specified in the parent Geometry_Orbiter class. The reference_location attribute is used to identify the specific point on the target.  
- [go to attribute list](#pixel_size_projected-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### Polynomial_Coefficients_1  
The Polynomial_Coefficients_1 class provides a one polynomial coefficient.  
- [go to attribute list](#polynomial_coefficients_1-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Polynomial_Coefficients_2  
The Polynomial_Coefficients_2 class provides two polynomial coefficients.  
- [go to attribute list](#polynomial_coefficients_2-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Polynomial_Coefficients_3  
The Polynomial_Coefficients_3 class provides three polynomial coefficients.  
- [go to attribute list](#polynomial_coefficients_3-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Quaternion_Model_Transform  
The Quaternion_Model_Transform class specifies, along with Vector_Model_Transform class, the transform used for the camera model in an image. Camera models created by the calibration process have associated with them a pose, comprised of the position (offset) and orientation (quaternion) of the camera at the time it was calibrated. The model is transformed ("pointed") for a specific image by computing, generally using articulation device kinematics, a final pose for the image. The camera model is then translated and rotated from the calibration to final pose. This class specifies the quaternion portion of the final pose.  
- [go to attribute list](#quaternion_model_transform-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Quaternion_Plus_Direction  
Quaternion_Plus_Direction provides the four elements of a quaternion and its direction of rotation. The two end point frames must be identified in the enclosing class. See the definition of Quaternion_Base for more details on the quaternion classes in this dictionary.  
- [go to attribute list](#quaternion_plus_direction-attribute-list)  
- in [Coordinate_Space_Definition](#coordinate_space_definition):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Device_Pose](#device_pose):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### Quaternion_Plus_To_From  
Quaternion_Plus_To_From provides the four elements of a quaternion, plus attributes which identify the initial (Rotate_From) and final (Rotate_To) frames of the rotation. See the defintion of Quaternion_Base for more details on the quaternion classes in this dictionary.  
- [go to attribute list](#quaternion_plus_to_from-attribute-list)  
- in [Geometry_Orbiter](#geometry_orbiter):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Image_Display_Geometry](#image_display_geometry):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
  
### Radial_Terms  
Radial_Terms contains the coefficients of a polynomial function used to describe the radial distortion of the camera.  
- [go to attribute list](#radial_terms-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Reference_Frame_Identification  
The Reference_Frame_Identification class is a base class for identifying reference frames. These are frames in the NAIF sense, i.e., three orthogonal axes with a specified orientation, but without a fixed origin.  
- [go to attribute list](#reference_frame_identification-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Reference_Pixel  
The Reference_Pixel class provides the pixel coordinates, line and sample, to which values in the containing class apply. Integer values indicate the center of the pixel. Sub-pixel values are permitted. For pixel_sample, the leading edge (left edge for sample increasing to the right) has a value 0.5 less than the integer value at the center, and the value for the trailing edge is the center integer value + 0.5. For pixel_line, the leading and trailing edges (top and bottom respectively for line increasing downward) again are -0.5 and +0.5 with respect to the center integer value.  
- [go to attribute list](#reference_pixel-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Rotate_From  
A quaternion rotates one reference frame to another reference frame. The Rotate_From class identifies the initial frame.  
- [go to attribute list](#rotate_from-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Rotate_To  
A quaternion rotates a one reference frame to another reference frame. The Rotate_To class identifies the destination frame.  
- [go to attribute list](#rotate_to-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### SPICE_Kernel_Files  
The SPICE_Kernel_Files class provides references to the SPICE files used when calculating geometric values.  
- [go to attribute list](#spice_kernel_files-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### SPICE_Kernel_Identification  
The SPICE_Kernel_Identification class optionally includes the SPICE kernel type and provides two alternatives for identifying the product: LIDVID using Internal_Reference, and the file name of the kernel file. Although optional, LIDVID should be given if one is available. The optional kernel_provenance attribute indicates whether the kernel is a predict or reconstructed kernel, or some combination of the two, or if it is a kernel type for which such distinctions do not apply.  
- [go to attribute list](#spice_kernel_identification-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Surface_Geometry  
The Surface_Geometry class is a container for surface geometry classes.  
- [go to attribute list](#surface_geometry-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Surface_Geometry_Min_Max  
The Surface_Geometry_Min_Max class contains attributes providing surface geometry parameters as minimum/maximum pairs. For any given parameter if one of minimum or maximum is given, both must be given. The min-max pairs for each parameter provide the range of that parameter in the observation for the target specified using the Geometry_Target_Identification class in the Orbiter_Identification class under the parent Geometry_Orbiter class.  
- [go to attribute list](#surface_geometry_min_max-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Surface_Geometry_Specific  
The Surface_Geometry_Specific class contains classes and attributes for various points on the surface of the target designated in the enclosing Geometry_Orbiter.  
- [go to attribute list](#surface_geometry_specific-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Surface_Geometry_Start_Stop  
The Surface_Geometry_Start_Stop class contains attributes providing surface geometry parameters given as pairs corresponding to the beginning and end of the observation. For a parameter, if either the start or stop parameter is given, both must be provided. If any values from this class are included in the label, the parameters geometry_start_time_utc and geometry_stop_time_utc must be given in the enclosing Geometry_Orbiter class.  
- [go to attribute list](#surface_geometry_start_stop-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Vector_Axis  
The Vector_Axis is a unit vector that describes the axis of the camera, defined as the normal to the image plane.  
- [go to attribute list](#vector_axis-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Axis_X  
 Unit column-plane rotation axis, passing through the sphere center, typically vertical and pointing down so that positive rotations (by the right-hand rule) will rotate the forward half of the plane in the (rightward) direction of increasing column (as projected on the forward hemisphere).  
- [go to attribute list](#vector_axis_x-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Axis_Y  
 Unit row-plane rotation axis, passing through the sphere center, typically horizontal and pointing left so that positive rotations (by the right-hand rule) will rotate the forward half of the plane in the (downward) direction of increasing row (as projected on the forward hemisphere).  
- [go to attribute list](#vector_axis_y-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Cartesian_Acceleration_Base  
The Vector_Cartesian_Acceleration_Base is a three dimensional, rectangular coordinates vector. Uses units of linear acceleration. The included attributes are not sufficient to identify the endpoints of the vector.  
- [go to attribute list](#vector_cartesian_acceleration_base-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Cartesian_Acceleration_Extended_Base  
The Vector_Cartesian_Acceleration_Extended_Base is a three dimensional, rectangular coordinates vector. Uses units of linear acceleration. The included attributes are not sufficient to identify the endpoints of the vector. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_acceleration_extended_base-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Cartesian_Acceleration_Generic  
Vector_Cartesian_Acceleration_Generic is a three dimensional, rectangular coordinates vector. Uses units of linear acceleration. Includes attributes to identify the endpoints of the vector. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_acceleration_generic-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_No_Units  
This is a generic vector in Cartesian space. The "x", "y", and "z" component have no units.  
- [go to attribute list](#vector_cartesian_no_units-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Cartesian_Pixel  
This a Cartesian pixel vector generally used in camera models.  
- [go to attribute list](#vector_cartesian_pixel-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Cartesian_Position_Base  
The Vector_Cartesian_Position_Base is a three dimensional, rectangular coordinates vector. Uses units of length. The included attributes are not sufficient to identify the endpoints of the vector.  
- [go to attribute list](#vector_cartesian_position_base-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Cartesian_Position_Central_Body_To_Spacecraft  
The Vector_Cartesian_Position_Central_Body_To_Spacecraft is a linear, rectangular coordinates vector from the center of mass of the central body (e.g., planet) to the spacecraft. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_central_body_to_spacecraft-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_Central_Body_To_Target  
The Vector_Cartesian_Position_Central_Body_To_Target is a linear, rectangular coordinates vector from the center of mass of the central body (e.g., planet) to the target specified in the parent Geometry_Orbiter class. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_central_body_to_target-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_Earth_To_Central_Body  
The Vector_Cartesian_Position_Earth_To_Central_Body is a linear, rectangular coordinates vector from the Earth to the central body (e.g., planet). While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_earth_to_central_body-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_Earth_To_Spacecraft  
The Vector_Cartesian_Position_Earth_To_Spacecraft is a linear, rectangular coordinates vector from the Earth to the spacecraft. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_earth_to_spacecraft-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_Earth_To_Target  
The Vector_Cartesian_Position_Earth_To_Target is a linear, rectangular coordinates vector from the Earth to the target specified in the parent Geometry_Orbiter class. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_earth_to_target-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_Extended_Base  
The Vector_Cartesian_Position_Extended_Base is a three dimensional, rectangular coordinates vector. Uses units of length. The included attributes are not sufficient to identify the endpoints of the vector. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_extended_base-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Cartesian_Position_Generic  
Vector_Cartesian_Position_Generic is a three dimensional, rectangular coordinates vector. Uses units of length. Includes attributes to identify the endpoints of the vector. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_generic-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_SSB_To_Central_Body  
The Vector_Cartesian_Position_SSB_To_Central_Body is a linear, rectangular coordinates vector from the Solar System Barycenter to the central body (e.g., planet). While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_ssb_to_central_body-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_SSB_To_Spacecraft  
The Vector_Cartesian_Position_SSB_To_Spacecraft is a linear, rectangular coordinates vector from the Solar System Barycenter to the spacecraft. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_ssb_to_spacecraft-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_SSB_To_Target  
The Vector_Cartesian_Position_SSB_To_Target is a linear, rectangular coordinates vector from the Solar System Barycenter to the target specified in the parent Geometry_Orbiter class. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_ssb_to_target-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_Spacecraft_To_Target  
The Vector_Cartesian_Position_Spacecraft_To_Target is a linear, rectangular coordinates vector from the spacecraft to the target specified in the parent Geometry_Orbiter class. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_spacecraft_to_target-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_Sun_To_Central_Body  
The Vector_Cartesian_Position_Sun_To_Central_Body is a linear, rectangular coordinates vector from the Sun to the central body (e.g., planet). While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_sun_to_central_body-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_Sun_To_Spacecraft  
The Vector_Cartesian_Position_Sun_To_Spacecraft is a linear, rectangular coordinates vector from the Sun to the spacecraft. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_sun_to_spacecraft-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Position_Sun_To_Target  
The Vector_Cartesian_Position_Sun_To_Target is a linear, rectangular coordinates vector from the Sun to the target specified in the parent Geometry_Orbiter class. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_position_sun_to_target-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Unit  
This is a generic unit vector in Cartesian space. The "x", "y", and "z" component have no units and are restricted to values between -1.0 and 1.0 inclusive. Further the length of the vector square root of the (sum of the squares of the components) must be 1.0.  
- [go to attribute list](#vector_cartesian_unit-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Cartesian_Velocity_Base  
The Vector_Cartesian_Velocity_Base is a three dimensional, rectangular coordinates vector. Uses units of linear velocity. The included attributes are not sufficient to identify the endpoints of the vector.  
- [go to attribute list](#vector_cartesian_velocity_base-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Cartesian_Velocity_Extended_Base  
The Vector_Cartesian_Velocity_Extended_Base is a three dimensional, rectangular coordinates vector. Uses units of linear velocity. The included attributes are not sufficient to identify the endpoints of the vector. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_extended_base-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Cartesian_Velocity_Generic  
Vector_Cartesian_Velocity_Generic is a three dimensional, rectangular coordinates vector. Uses units of linear velocity. Includes attributes to identify the endpoints of the vector. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_generic-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Velocity_Spacecraft_Relative_To_Central_Body  
The Vector_Cartesian_Velocity_Spacecraft_Relative_To_Central_Body is a velocity vector in rectangular coordinates that gives the velocity of the spacecraft with respect to the central body (e.g., planet). While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_spacecraft_relative_to_central_body-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Velocity_Spacecraft_Relative_To_Earth  
The Vector_Cartesian_Velocity_Spacecraft_Relative_To_Earth is a velocity vector in rectangular coordinates that gives the velocity of the spacecraft with respect to Earth. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_spacecraft_relative_to_earth-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Velocity_Spacecraft_Relative_To_SSB  
The Vector_Cartesian_Velocity_Spacecraft_Relative_To_SSB is a velocity vector in rectangular coordinates that gives the velocity of the spacecraft with respect to the Solar System Barycenter. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_spacecraft_relative_to_ssb-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Velocity_Spacecraft_Relative_To_Sun  
 Vector_Cartesian_Velocity_Spacecraft_Relative_To_Sun is a velocity vector in rectangular coordinates that gives the velocity of the spacecraft with respect to the center of the Sun. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_spacecraft_relative_to_sun-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Velocity_Spacecraft_Relative_To_Target  
The Vector_Cartesian_Velocity_Spacecraft_Relative_To_Target is a velocity vector in rectangular coordinates that gives the velocity of the spacecraft with respect to the target specified in the parent Geometry_Orbiter class. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_spacecraft_relative_to_target-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Velocity_Target_Relative_To_Central_Body  
The Vector_Cartesian_Velocity_Target_Relative_To_Central_Body is a velocity vector in rectangular coordinates that gives the velocity of the designated target with respect to the central body (e.g., planet). While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_target_relative_to_central_body-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Velocity_Target_Relative_To_Earth  
The Vector_Cartesian_Velocity_Target_Relative_To_Earth is a velocity vector in rectangular coordinates that gives the velocity of the designated target with respect to Earth. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_target_relative_to_earth-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Velocity_Target_Relative_To_SSB  
The Vector_Cartesian_Velocity_Target_Relative_To_SSB is a velocity vector in rectangular coordinates that gives the velocity of the designated target with respect to the Solar System Barycenter. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_target_relative_to_ssb-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Velocity_Target_Relative_To_Spacecraft  
The Vector_Cartesian_Velocity_Target_Relative_To_Spacecraft is a velocity vector in rectangular coordinates that gives the velocity of the designated target with respect to the spacecraft. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_target_relative_to_spacecraft-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Cartesian_Velocity_Target_Relative_To_Sun  
 Vector_Cartesian_Velocity_Target_Relative_To_Sun is a velocity vector in rectangular coordinates that gives the velocity of the designated target with respect to the center of the sun. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_cartesian_velocity_target_relative_to_sun-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Center  
The Vector_Center describes the location of the entrance pupil of a camera.  
- [go to attribute list](#vector_center-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Device_Gravity  
The Vector_Device_Gravity class is a unit vector that specifies the direction of an external force acting on the articulation device, in the spacecraft's coordinate system, at the time the pose was computed.  
- [go to attribute list](#vector_device_gravity-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Device_Gravity_Magnitude  
The Vector_Device_Gravity_Magnitude class is a vector (with magnitude) that specifies the direction of an external force acting on the articulation device, in the spacecraft's coordinate system, at the time the pose was computed.  
- [go to attribute list](#vector_device_gravity_magnitude-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Horizontal  
The Vector_Horizonal is a composite vector encoding three quantities: H' (a vector in the image plane perpendicular to the vertical columns), Hs (the distance between the lens center and image plane, measured in horizontal pixels), and Hc (the horizontal image coordinate directly under C when moving parallel to A). H' is often thought of as describing the orientation of rows in space, but is actually perpendicular to the columns.  
- [go to attribute list](#vector_horizontal-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Model_Transform  
The Vector_Model_Transform class specifies, along with the Quaternion_Model_Transform class, the transform used for the camera model in this image. Camera models created by the calibration process have associated with them a pose, comprised of the position (offset) and orientation (quaternion) of the camera at the time it was calibrated. The model is transformed ("pointed") for a specific image by computing, generally using articulation device kinematics, a final pose for the image. The camera model is then translated and rotated from the calibration to final pose. This class specifies the offset portion of the final pose.  
- [go to attribute list](#vector_model_transform-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Vector_Normal_X  
 Unit normal vector to the column plane when x equals zero, pointing in the same direction as the cross product of axis x with an outward-pointing vector that also lies in the plane.  
- [go to attribute list](#vector_normal_x-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Normal_Y  
 Unit normal vector to the row plane when y equals zero, pointing in the same direction as the cross product of axis x with an outward-pointing vector that also lies in the plane.  
- [go to attribute list](#vector_normal_y-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Optical  
The Vector_Optical is a unit vector that describes the axis of symmetry for radial distortion in the camera.  
- [go to attribute list](#vector_optical-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Origin_Offset  
The Vector_Origin_Offset class contains attributes that specify the offset from the reference coordinate system's origin to the origin of the coordinate system. It is the location of the current system's origin as measured in the reference system.  
- [go to attribute list](#vector_origin_offset-attribute-list)  
- in [Coordinate_Space_Definition](#coordinate_space_definition):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Device_Pose](#device_pose):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### Vector_Planetocentric_Position_Base  
The Vector_Planetocentric_Position_Base is a three dimensional spherical vector (radius, longitude, latitude) with the angular coordinates defined to be consistent with the Planetocentric coordinate system. Uses linear units for the radius dimension, and angular units for the other two dimensions. The included attributes are not sufficient to identify the endpoints of the vector.  
- [go to attribute list](#vector_planetocentric_position_base-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Planetocentric_Position_Central_Body_To_Spacecraft  
The Vector_Planetocentric_Position_Central_Body_To_Spacecraft is a spherical position vector in Planetocentric coordinates. It extends from the center of mass of the central body (e.g., planet) to the spacecraft. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_planetocentric_position_central_body_to_spacecraft-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Planetocentric_Position_Central_Body_To_Target  
The Vector_Planetocentric_Position_Central_Body_To_Target is a spherical position vector in Planetocentric coordinates. It extends from the center of mass of the central body (e.g., planet) to the target specified in the parent Geometry_Orbiter class. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_planetocentric_position_central_body_to_target-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Planetocentric_Position_Extended_Base  
The Vector_Planetocentric_Position_Extended_Base is a three dimensional spherical vector (radius, longitude, latitude) with the angular coordinates defined to be consistent with the Planetocentric coordinate system. Uses linear units for the radius dimension, and angular units for the other two dimensions. The included attributes are not sufficient to identify the endpoints of the vector. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_planetocentric_position_extended_base-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Planetocentric_Position_Generic  
The Vector_Planetocentric_Position_Generic is a three dimensional spherical vector (radius, longitude, latitude) with the angular coordinates defined to be consistent with the Planetocentric coordinate system. Uses linear units for the radius dimension, and angular units for the other two dimensions. Includes attributes to identify the endpoints of the vector. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_planetocentric_position_generic-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Planetocentric_Position_Spacecraft_To_Target  
The Vector_Planetocentric_Position_Spacecraft_To_Target is a spherical position vector in Planetocentric coordinates. It extends from the spacecraft to the target specified in the parent Geometry_Orbiter class. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_planetocentric_position_spacecraft_to_target-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Planetocentric_Velocity_Base  
The Vector_Planetocentric_Velocity_Base is a three dimensional spherical vector (radius, longitude, latitude) with the angular coordinates defined to be consistent with the Planetocentric coordinate system. Uses linear velocity units for the radius dimension, and angular velocity units for the other two dimensions. The included attributes are not sufficient to identify the endpoints of the vector.  
- [go to attribute list](#vector_planetocentric_velocity_base-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Planetocentric_Velocity_Extended_Base  
The Vector_Planetocentric_Velocity_Extended_Base is a three dimensional spherical vector (radius, longitude, latitude) with the angular coordinates defined to be consistent with the Planetocentric coordinate system. Uses linear velocity units for the radius dimension, and angular velocity units for the other two dimensions. The included attributes are not sufficient to identify the endpoints of the vector. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_planetocentric_velocity_extended_base-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vector_Planetocentric_Velocity_Generic  
The Vector_Planetocentric_Velocity_Generic is a three dimensional spherical vector (radius, longitude, latitude) with the angular coordinates defined to be consistent with the Planetocentric coordinate system. Uses linear velocity units for the radius dimension, and angular velocity units for the other two dimensions. Includes attributes to identify the endpoints of the vector. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_planetocentric_velocity_generic-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Planetocentric_Velocity_Spacecraft_Relative_To_Target  
The Vector_Planetocentric_Velocity_Spacecraft_Relative_To_Target is a spherical velocity vector in Planetocentric coordinates that gives the velocity of the spacecraft with respect to the designated target. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_planetocentric_velocity_spacecraft_relative_to_target-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Planetocentric_Velocity_Target_Relative_To_Central_Body  
The Vector_Planetocentric_Velocity_Target_Relative_To_Central_Body is a spherical velocity vector in Planetocentric coordinates that gives the velocity of the target with respect to the central body. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_planetocentric_velocity_target_relative_to_central_body-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Planetocentric_Velocity_Target_Relative_To_Spacecraft  
The Vector_Planetocentric_Velocity_Target_Relative_To_Spacecraft is a spherical velocity vector in Planetocentric coordinates that gives the velocity of the target with respect to the spacecraft. While the class Coordinate_System_Identification is optional, it must be used here if the coordinate system has not been specified in the enclosing class.  
- [go to attribute list](#vector_planetocentric_velocity_target_relative_to_spacecraft-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### Vector_Solar_Direction  
 Unit vector pointing in the direction of the Sun at the time of the observation.  
- [go to attribute list](#vector_solar_direction-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Vector_Vertical  
The Vector_Vertical is a composite vector encoding three quantities: V' (a vector in the image plane perpendicular to the horizontal rows), Vs (the distance between the lens center and image plane, measured in vertical pixels), and Vc (the vertical image coordinate directly under C when moving parallel to A). V' is often thought of as describing the orientation of columns in space, but is actually perpendicular to the rows.  
- [go to attribute list](#vector_vertical-attribute-list)  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### Vectors  
The Vectors class is a container of vector classes.  
- [go to attribute list](#vectors-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Vectors_Cartesian_Specific  
The Vectors_Cartesian_Specific class is a container class for all cartesian vectors with pre-identified endpoints.  
- [go to attribute list](#vectors_cartesian_specific-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### Vectors_Planetocentric_Specific  
The Vectors_Planetocentric_Specific class is a container class for all planetocentric vectors with pre-identified endpoints.  
- [go to attribute list](#vectors_planetocentric_specific-attribute-list)  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
## Attributes (in alphabetical order)  
  
### *attitude_propagation_counter*  
Count in clock units of how long it has been since the last IMU reset, which relates to how good the attitude measurement is due to IMU drift.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *attitude_propagation_duration*  
The number of seconds for how long it has been since the last IMU reset, which relates to how good the attitude measurement is due to IMU drift.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *body_spice_name*  
The body_spice_name attribute is a NAIF-recognized string identifier for a physical object (spacecraft, planet, instrument transmitter, system barycenter, etc.), associated with the data.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- in [Central_Body_Identification](#central_body_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Coordinate_System_Origin_Identification](#coordinate_system_origin_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Geometry_Target_Identification](#geometry_target_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Observer_Identification](#observer_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Coordinate_Space_SPICE](#coordinate_space_spice):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
  
### *c0*  
The first coefficient of a polynomial.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *c1*  
The second coefficient of a polynomial.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *c2*  
The third coefficient of a polynomial.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *cahvore_model_parameter*  
The cahvore_parameter_type attribute is a scalar floating-point number used for CAHVORE Type 3 models (see cahvore_model_type). If the parameter is 1.0, the model is identical to type 1; if 0.0, it is identical to type 2. Most fish-eye lenses use a value in between.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *cahvore_model_type*  
The cahvore_model_type attribute indicates which variant of the CAHVORE model to use. Type 1 is a perspective-projection model, similar to CAHV and CAHVOR except for the moving entrance pupil. Type 2 is a fish-eye lens model reflecting fundamentally different geometry. Type 3 is a generalization that includes the first two, and is used for most fisheye-type lenses (see cahvore_model_parameter).  
- PDS4 data type: ASCII_Integer  
- Valid values:  
  - 1  
    - Description: A perspective-projection model, similar to CAHV and CAHVOR except for the moving entrance pupil  
  - 2  
    - Description: A fish-eye lens model reflecting fundamentally different geometry  
  - 3  
    - Description: A generalization that includes the first two, and is used for most fisheye-type lenses  
- Minimum value: -9223372036854775808  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *calibration_source_id*  
The calibration_source_id is used to identify the source used in calibrating the instrument.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *celestial_east_clock_angle*  
The celestial_east_clock_angle attribute specifies the direction of celestial east at the center of an image. It is measured from the 'upward' direction, clockwise to the direction toward celestial east, assuming the image is displayed as defined by the Display_Direction class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *celestial_north_clock_angle*  
The celestial_north_clock_angle attribute specifies the direction of celestial north at the center of an image. It is measured from the 'upward' direction, clockwise to the direction toward celestial north, assuming the image is displayed as defined by the Display_Direction class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: Yes  
- in [Object_Orientation_RA_Dec](#object_orientation_ra_dec):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 2  
- in [Object_Orientation_Clock_Angles](#object_orientation_clock_angles):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
  
### *central_body_north_pole_clock_angle*  
The central_body_north_pole_clock_angle element specifies the direction of the central body's (e.g., planet's)rotation axis in an image. It is measured from the 'upward' direction in the image, clockwise to the direction of the northern rotational pole as projected into the image plane, assuming the image is displayed as defined by the Display_Direction class. The north pole of a planet or any of its satellites in the solar system is the pole of the rotation axis that is in the same celestial hemisphere relative to the invariable plane of the solar system as Earth's North pole.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *central_body_positive_pole_clock_angle*  
The central_body_positive_pole_clock_angle element specifies the direction of the central body's rotation axis in an image. It is measured from the 'upward' direction in the image, clockwise to the direction of the positive rotational pole as projected into the image plane, assuming the image is displayed as defined by the Display_Direction class. The positive pole is defined as the pole toward which the thumb points when the fingers of the right hand are curled in the body's direction of rotation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *command_type*  
 Specifies how the device was commanded.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Angle_Absolute  
    - Description:  Specifies an absolute pointing direction for the device. This is distinct from Joint_Absolute in that the angle is measured in a coordinate frame rather than direct joint angles.  
  - Angle_Relative  
    - Description:  Specifies a pointing direction change relative to the prior pointing. This is distinct from Joint_Relative in that the angle is measured in a coordinate frame rather than direct joint angles.  
  - Joint_Absolute  
    - Description:  Specifies absolute joint angles.  
  - Joint_Relative  
    - Description:  Specifies joint angles as a delta relative to the prior pointing..  
  - No_Motion  
    - Description:  Specifies no motion from the previous observation.  
  - No_Motion_No_Arb  
    - Description:  Specifies no motion from the previous observation, but also does not reserve the resource (thus no arbitration).  
  - None  
    - Description:  Unspecified commanding.  
  - XYZ  
    - Description:  Specifies a pointing target as an XYZ coordinate in a given coordinate frame.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *comment*  
The comment attribute is a character string expressing one or more remarks or thoughts relevant to the object.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- in [Surface_Geometry](#surface_geometry):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [SPICE_Kernel_Files](#spice_kernel_files):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
- in [Vectors](#vectors):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Illumination_Geometry](#illumination_geometry):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Reference_Frame_Identification](#reference_frame_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Rotate_From](#rotate_from):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Rotate_To](#rotate_to):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Generic_Vectors](#generic_vectors):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Distances](#distances):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Display_Direction](#display_direction):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Coordinate_System_Identification](#coordinate_system_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### *coordinate_space_frame_type*  
The coordinate_space_frame_type attribute identifies the type of frame being described, such as SITE, LOCAL_LEVEL, LANDER, ROVER, ARM, etc. When combined with Coordinate_Space_Index and the optional solution_id in the Coordinate_Space_Indexed class, this serves to fully name an instance of a coordinate space.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - AEGIS_1  
    - Description: AEGIS target number 1. AEGIS is a component of rover software that selects targets for further investigation based on user defined parameters.  
  - AEGIS_2  
    - Description: AEGIS target number 2. AEGIS is a component of rover software that selects targets for further investigation based on user defined parameters.  
  - AEGIS_3  
    - Description: AEGIS target number 3. AEGIS is a component of rover software that selects targets for further investigation based on user defined parameters.  
  - AEGIS_4  
    - Description: AEGIS target number 4. AEGIS is a component of rover software that selects targets for further investigation based on user defined parameters.  
  - AEGIS_5  
    - Description: AEGIS target number 5. AEGIS is a component of rover software that selects targets for further investigation based on user defined parameters.  
  - APXS_Frame  
    - Description: Frame defining the APXS instrument on a movable arm.  
  - ARM_CUSTOM_TCP_FRAME  
    - Description: Frame describing a user-defined Tool Control Point for a movable arm.  
  - ARM_DOCKING_POST_FRAME  
    - Description: Frame describing the docking post on a movable arm.  
  - ARM_DRILL_FRAME  
    - Description: Frame describing the drill on a movable arm.  
  - ARM_DRT_FRAME  
    - Description: Frame describing the Dust Removal Tool on a movable arm.  
  - ARM_FCS_FRAME  
    - Description: Frame describing the FCS (Facility Contact Switch) device on a movable arm.  
  - ARM_FRAME  
    - Description: Frame describing a defined portion of a movable arm.  
  - ARM_GDRT_FRAME  
    - Description: Frame describing the GDRT (Gaseous Dust Removal Tool) device on a movable arm.  
  - ARM_MAHLI_FRAME  
    - Description: Frame describing the MAHLI instrument on a movable arm.  
  - ARM_PIXL_FRAME  
    - Description: Frame describing the PIXL instrument on a movable arm.  
  - ARM_PORTION_FRAME  
    - Description: Frame describing the sample portioner device on a movable arm.  
  - ARM_SCOOP_TCP_FRAME  
    - Description: Frame describing the Tool Control Point for the scoop on a movable arm.  
  - ARM_SCOOP_TIP_FRAME  
    - Description: Frame describing the tip of a scoop on a movable arm.  
  - ARM_SHERLOC_FRAME  
    - Description: Frame describing the SHERLOC instrument on a movable arm.  
  - ARM_TURRET_FRAME  
    - Description: Frame describing the turret on a movable arm.  
  - ARM_WATSON_FRAME  
    - Description: Frame describing the Watson instrument component on a movable arm.  
  - Arm_Custom_TCP_Frame  
    - Description: Frame describing a user-defined Tool Control Point for a movable arm.  
  - Arm_DRT_Frame  
    - Description: Frame describing the Dust Removal Tool on a movable arm.  
  - Arm_Docking_Post_Frame  
    - Description: Frame describing the docking post on a movable arm.  
  - Arm_Drill_Frame  
    - Description: Frame describing the drill on a movable arm.  
  - Arm_FCS_Frame  
    - Description: Frame describing the FCS (Facility Contact Switch) device on a movable arm.  
  - Arm_Frame  
    - Description: Frame describing a defined portion of a movable arm.  
  - Arm_GDRT_Frame  
    - Description: Frame describing the GDRT (Gaseous Dust Removal Tool) device on a movable arm.  
  - Arm_MAHLI_Frame  
    - Description: Frame describing the MAHLI instrument on a movable arm.  
  - Arm_PIXL_Frame  
    - Description: Frame describing the PIXL instrument on a movable arm.  
  - Arm_Portion_Frame  
    - Description: Frame describing the sample portioner device on a movable arm.  
  - Arm_SHERLOC_Frame  
    - Description: Frame describing the SHERLOC instrument on a movable arm.  
  - Arm_Scoop_TCP_Frame  
    - Description: Frame describing the Tool Control Point for the scoop on a movable arm.  
  - Arm_Scoop_TIP_Frame  
    - Description: Frame describing the tip of a scoop on a movable arm.  
  - Arm_Turret_Frame  
    - Description: Frame describing the turret on a movable arm.  
  - Arm_WATSON_Frame  
    - Description: Frame describing the Watson instrument component on a movable arm.  
  - CINT_FRAME  
    - Description: Frame describing the LVS camera during descent.  
  - CINT_Frame  
    - Description: Frame describing the LVS camera during descent.  
  - DRILL_BIT_TIP  
    - Description: Frame centered on the tip of the drill.  
  - HELI_G_FRAME  
    - Description: Helicopter frame defined attached to the ground at takeoff.  
  - HELI_M_FRAME  
    - Description: Helicopter frame roughly analogous to ROVER_MECH_FRAME.  
  - HELI_S1_FRAME  
    - Description: Helicopter frame roughly analogous to ROVER_NAV_FRAME defined for IMU #1.  
  - HELI_S2_FRAME  
    - Description: Helicopter frame roughly analogous to ROVER_NAV_FRAME defined for IMU #2.  
  - Heli_G_Frame  
    - Description: Helicopter frame defined attached to the ground at takeoff.  
  - Heli_M_Frame  
    - Description: Helicopter frame roughly analogous to ROVER_MECH_FRAME.  
  - Heli_S1_Frame  
    - Description: Helicopter frame roughly analogous to ROVER_NAV_FRAME defined for IMU #1.  
  - Heli_S2_Frame  
    - Description: Helicopter frame roughly analogous to ROVER_NAV_FRAME defined for IMU #2.  
  - LANDER_FRAME  
    - Description: Analogous to ROVER_NAV_FRAME for non-mobile missions.  
  - LOCAL_LEVEL_FRAME  
    - Description: Frame coincident with ROVER_NAV/LANDER_FRAME that is oriented according to cartographic directions and gravity.  
  - Lander_Frame  
    - Description: Analogous to ROVER_NAV_FRAME for non-mobile missions.  
  - Local_Level_Frame  
    - Description: Frame coincident with ROVER_NAV/LANDER_FRAME that is oriented according to cartographic directions and gravity.  
  - MB_Frame  
    - Description: None  
  - MCMF_FRAME  
    - Description: Mars Centered Mars Fixed Frame defined with origin at the planet center.  
  - MCMF_Frame  
    - Description: Mars Centered Mars Fixed Frame defined with origin at the planet center.  
  - MCZ_CAL_PRIMARY  
    - Description: Primary Mastcam-Z calibration target.  
  - MEDA_RDS  
    - Description: Radiation and Dust Sensor for the MEDA instruments.  
  - MI_Frame  
    - Description: None  
  - Mast_Frame  
    - Description: None  
  - ORBITAL  
    - Description: A surface frame for use with orbital images, where the origin is defined relative to the equator and prime meridan or another orbital frame.  
  - Orbital  
    - Description: A surface frame for use with orbital images, where the origin is defined relative to the equator and prime meridan or another orbital frame.  
  - PIXL_BASE_FRAME  
    - Description: Frame describing the base of the PIXL instrument.  
  - PIXL_Base_Frame  
    - Description: Frame describing the base of the PIXL instrument.  
  - PIXL_SENSOR_FRAME  
    - Description: Frame describing the movable sensor head of the PIXL instrument.  
  - PIXL_Sensor_Frame  
    - Description: Frame describing the movable sensor head of the PIXL instrument.  
  - PIXL_TOOL  
    - Description: Frame for PIXL instrument.  
  - PIXL_Tool  
    - Description: Frame for PIXL instrument.  
  - ROVER_FRAME  
    - Description: Frame that is attached to the rover and moves with the rover (in both position and orientation). Often synonymous with ROVER_NAV_FRAME.  
  - ROVER_MECH_FRAME  
    - Description: Frame generally similar to ROVER_NAV_FRAME but with different origin and possibly axis orientation that is more conducive to mechanical operations ("MECH" for "Mechanical"). The origin is typically (but not necessarily) tied to a specific bit of hardware.  
  - ROVER_NAV_FRAME  
    - Description: Frame attached to the rover oriented with respect to the rover that moves with the rover ("NAV" for "Navigation"). The origin is generally in a location conducive to navigation (e.g. at the center of turning between the middle wheels at nominal ground level on MSL/M20 type rovers) which may not be attached to any physical hardware.  
  - RSM_FRAME  
    - Description: Frame defining a Remote Sensing Mast.  
  - RSM_Frame  
    - Description: Frame defining a Remote Sensing Mast.  
  - RSM_HEAD_FRAME  
    - Description: Frame defining a Remote Sensing Mast.  
  - RSM_Head_Frame  
    - Description: Frame defining a Remote Sensing Mast.  
  - Rat_Frame  
    - Description: None  
  - Rover_Frame  
    - Description: None  
  - Rover_Mech_Frame  
    - Description: Frame generally similar to ROVER_NAV_FRAME but with different origin and possibly axis orientation that is more conducive to mechanical operations ("MECH" for "Mechanical"). The origin is typically (but not necessarily) tied to a specific bit of hardware.  
  - Rover_Nav_Frame  
    - Description: Frame attached to the rover oriented with respect to the rover that moves with the rover ("NAV" for "Navigation"). The origin is generally in a location conducive to navigation (e.g. at the center of turning between the middle wheels at nominal ground level on MSL/M20 type rovers) which may not be attached to any physical hardware.  
  - SAM1  
    - Description: Sample Analysis at Mars frame 1 (used by MSL)  
  - SAM2  
    - Description: Sample Analysis at Mars frame 2 (used by MSL)  
  - SITE_FRAME  
    - Description: Instance of LOCAL_LEVEL_FRAME that is fixed to the ground. Used for local operations to reduce error propagation due to position uncertainty.  
  - SUN  
    - Description: Frame centered on the sun. Generally used for pointing instruments at the sun, rather than 3D position.  
  - Site_Frame  
    - Description: Instance of LOCAL_LEVEL_FRAME that is fixed to the ground. Used for local operations to reduce error propagation due to position uncertainty.  
  - TOOL_FRAME  
    - Description: Tool frame is used to indicate the frame associated with the currently selected (or activated) "tool", in contexts where the specific frame is unknown or does not matter. "Tools" are typically devices on an arm such as a drill, microscopic imager, contact spectrometer, etc.  
  - TURRET_FRAME  
    - Description: Frame based on a turret mechanism.  
  - Tool_Frame  
    - Description: Tool frame is used to indicate the frame associated with the currently selected (or activated) "tool", in contexts where the specific frame is unknown or does not matter. "Tools" are typically devices on an arm such as a drill, microscopic imager, contact spectrometer, etc.  
  - Turret_Frame  
    - Description: Frame based on a turret mechanism.  
  - WHEEL_LF  
    - Description: Frame for left front wheel.  
  - WHEEL_LM  
    - Description: Frame for left middle wheel.  
  - WHEEL_LR  
    - Description: Frame for left rear wheel.  
  - WHEEL_RF  
    - Description: Frame for right front wheel.  
  - WHEEL_RM  
    - Description: Frame for right middle wheel.  
  - WHEEL_RR  
    - Description: Frame for right rear wheel.  
  - Wheel_LF  
    - Description: Frame for left front wheel.  
  - Wheel_LM  
    - Description: Frame for left middle wheel.  
  - Wheel_LR  
    - Description: Frame for left rear wheel.  
  - Wheel_RF  
    - Description: Frame for right front wheel.  
  - Wheel_RM  
    - Description: Frame for right middle wheel.  
  - Wheel_RR  
    - Description: Frame for right rear wheel.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *coordinate_system_time_utc*  
The coordinate_system_time_utc provides the instantiation time for the coordinate system.  
- PDS4 data type: ASCII_Date_Time_YMD_UTC  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *coordinate_system_type*  
The coordinate_system_type distinguishes between options such as rectangular, spherical, planetocentric, etc.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Azimuth-Elevation  
    - Description: The coordinate system uses azimuth-elevation coordinates. Azimuth: angle from +X axis to projection of position vector on x-y plane increases in clockwise direction (-180 to +180). Elevation: angle between position vector and x-y plane (-90 to +90).  
  - Cartesian  
    - Description: The coordinate system uses rectangular coordinates.  
  - Planetocentric  
    - Description: The coordinate system uses planetocentric coordinates. Planetocentric longitude increases positively eastward (-180 to +180). Planetocentric latitude increases positively northward (-90 to +90). For planets and their satellites the +Z axis (+90 latitude) always points to the north side of the invariable plane (the plane whose normal vector is the angular momentum vector of the solar system). For dwarf planets, asteroids and comets the IAU defines their positive pole such that their spin is in the right hand sense about their positive pole. The positive pole may point above or below the invariable plane of the solar system. This revision by the IAU Working Group (2006) inverts what had been the direction of the north pole for Pluto, Charon and Ida.  
  - Planetodetic  
    - Description: The coordinate system uses planetodetic coordinates. For planets and their satellites the +Z axis (+90 latitude) always points to the north side of the invariable plane (the plane whose normal vector is the angular momentum vector of the solar system). Planetodetic longitude increases positively eastward (-180 to +180). Planetodetic latitude is tied to a reference ellipsoid. For a point, P, on a reference ellipsoid, angle measured from X-Y plane to the surface normal at the point of interest. For other points, equals latitude at the nearest point on the reference ellipsoid. Increases positively northward (-90 to +90).  
  - Planetographic  
    - Description: The coordinate system uses planetographic coordinates. For planet and satellite planetographic coordinate systems: Planetographic longitude is usually defined such that the sub-observer longitude increases with time as seen by a distant, fixed observer (0 to 360). The earth, moon and sun are exceptions; planetographic longitude is positive east by default (0 to 360). Planetographic latitude is planetodetic latitude (-90 to +90). For dwarf planets, asteroids and comets: there are multiple, inconsistent standards. Currently, for these objects, PDS permits planetographic coordinates to be provided in addition to, not in lieu of, either planetocentric or planetodetic coordinates.  
  - Spherical  
    - Description: The coordinate system uses spherical coordinates. Longitude: angle from +X axis to projection of position vector on X-Y plane increases in clockwise direction (0 to 360). Colatitude: angle between +Z axis and position vector (0 to 180).  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *declination_angle*  
The declination_angle (Dec) attribute provides the value of an angle on the celestial sphere, measured north from the celestial equator to the point in question. (For points south of the celestial equator, negative values are used.) Declination is used in conjunction with right ascension (right_ascension_angle or right_ascension_hour_angle) to specify a point on the sky.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *description*  
The description attribute provides a statement, picture in words, or account that describes or is otherwise relevant to the object.  
- PDS4 data type: UTF8_Text_Preserved  
- Valid values: N/A  
- Minimum Length: 1  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *device_id*  
The device_id attribute specifies the abbreviated identification of an articulation device.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *device_mode*  
The device_mode attribute specifies the deployment state (i.e., physical configuration) of an articulation device at the time of data acquisition. Examples include 'Arm Vibe', 'Deployed', 'Free Space', 'Stowed'. Note: the value set for this attribute is mission-specific and should be declared in a mission-specific dictionary.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *device_name*  
The device_name attribute specifies the common name of an articulation device.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *device_phase*  
The device_phase attribute specifies the current phase of the mission, from an articulation-device-centric point of view.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *distance*  
The distance attribute provides the scalar distance between to objects or points.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *east_azimuth*  
Assuming the image is displayed as defined by the Display_Direction class, the east_azimuth attribute provides the value of the angle between a line from the image center to the east and a reference line in the image plane. The reference line is a horizontal line from the image center to the middle right edge of the image. This angle is measured from the reference line and increases in a clockwise direction.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *ecliptic_east_clock_angle*  
The ecliptic_east_clock_angle attribute specifies the direction of ecliptic east at the center of an image. It is measured from the 'upward' direction, clockwise to the direction toward ecliptic east, assuming the image is displayed as defined by the Display_Direction class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *ecliptic_north_clock_angle*  
The ecliptic_north_clock_angle attribute specifies the direction of ecliptic north at the center of an image. It is measured from the 'upward' direction, clockwise to the direction toward ecliptic north, assuming the image is displayed as defined by the Display_Direction class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: Yes  
- in [Object_Orientation_RA_Dec](#object_orientation_ra_dec):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 2  
- in [Object_Orientation_Clock_Angles](#object_orientation_clock_angles):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
  
### *emission_angle*  
The emission_angle element provides a measure of the relationship between the instrument viewing position and the surface normal vector at the intercept point. Specifically, it is the angle, measured at the intercept point, between the local surface normal vector and a vector in the direction of the outgoing photon to the observing instrument. The emission_angle varies from 0 degrees when the spacecraft is viewing the subspacecraft point (nadir viewing) to 90 degrees when the intercept is tangent to the surface of the target body. Thus, higher values of emission_angle indicate more oblique viewing of the target. In the context of planetary rings, the local surface normal vector is always on the side of the ring plane illuminated by the light source. Thus, the emission_angle varies from 0 degrees when the spacecraft is viewing the illuminated side of the rings face-on, to 90 degrees when viewing the rings edge-on (that is, the spacecraft is in the ring plane), to 180 degrees when the spacecraft is viewing the unlit side of the rings face-on.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- in [Illumination_Specific](#illumination_specific):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 4  
- in [Derived_Geometry](#derived_geometry):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
  
### *frame_spice_name*  
The frame_spice_name attribute is a NAIF-recognized string identifier for a reference frame associated with the data.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- in [Reference_Frame_Identification](#reference_frame_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Rotate_From](#rotate_from):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Rotate_To](#rotate_to):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Coordinate_Space_SPICE](#coordinate_space_spice):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
  
### *geometry_reference_time_tdb*  
The geometry reference time given in the 'Barycentric Dynamical Time' system, as a number of elapsed seconds since the J2000 epoch. This is consistent with the definition of 'ephemeris time' as used in the SPICE toolkit. The value must correspond to the time specified in the geometry_reference_time_utc attribute.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *geometry_reference_time_utc*  
For some observations, geometric parameters are given as instantaneous values at a specific time. Another set of instantaneous parameters are the parameters which give the minimum and maximum values in the product. In some cases, these range values are all calculated for the same time. If the label includes single valued geometric parameters or min/max range parameters determined for a specific time, geometry_reference_time_utc gives the time for which these values were calculated and must be given in the label. For some instruments, particularly those with relatively large exposure durations, (e.g., push broom cameras, many imaging spectrometers), many geometric quantities are given as ranges. If those range parameters are associated with the beginning and end of the observation (start_parameter/stop_parameter), geometry_start_time_utc/stop_time must be given. Comments within the label should be used to ensure the parameter vs. time association is unambiguous.  
- PDS4 data type: ASCII_Date_Time_YMD_UTC  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 3  
  
### *geometry_start_time_utc*  
The pair of geometry_start_time_utc/geometry_stop_time_utc may be given in the label for any observation. The pair is generally used for fairly long duration observations (a substantial portion of an hour to several hours). geometry_start_time_utc gives the time at the beginning of the observation. When either geometry_start_time_utc or geometry_stop_time_utc is given, both must be provided. Within the Geometry discipline, there are two options for providing geometric parameters as a range of values. A parameter may be given as a pair where the parameter values are those at the beginning and end of the observation (start_parameter, stop_parameter). If a (start_parameter, stop_parameter) pair is used for any geometric parameter, the pair (geometry_start_time_utc/geometry_stop_time_utc) must be given. Another option to provide geometric parameters as a pair is (minimum_parameter, maximum_parameter) defining a range of values where the values are the minimum and maximum values of that parameter for the entire observation. Comments within the label should be used to ensure the parameter vs. time association is unambiguous.  
- PDS4 data type: ASCII_Date_Time_YMD_UTC  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 3  
  
### *geometry_state*  
Specifies the state or configuration of this instance of Geometry_Lander applies. Use of this attribute enables multiple instances of Geometry_Lander, describing the geometry under different conditions. Note that it is legal for more than one instance to have the same geometry_state, in which case the local_identifier should be used to differentiate the instances, along with description. If not present, the semantics of "Telemetry" should be assumed. It is not required that instances be retained; a derived product may have an Adjusted instance but remove the Telemetry one, for example.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *geometry_stop_time_utc*  
The pair of geometry_start_time_utc/geometry_stop_time_utc may be given in the label for any observation. The pair is generally used for fairly long duration observations (a substantial portion of an hour to several hours). geometry_stop_time_utc gives the time at the end of the observation. When either geometry_start_time_utc or geometry_stop_time_utc is given, both must be provided. Within the Geometry discipline, there are two options for providing geometric parameters as a range of values. A parameter may be given as a pair where the parameter values are those at the beginning and end of the observation (start_parameter, stop_parameter). If a (start_parameter, stop_parameter) pair is used for any geometric parameter, the pair (geometry_start_time_utc/geometry_stop_time_utc) must be given. Another option to provide geometric parameters as a pair is (minimum_parameter, maximum_parameter) defining a range of values where the values are the minimum and maximum values of that parameter for the entire observation. Comments within the label should be used to ensure the parameter vs. time association is unambiguous.  
- PDS4 data type: ASCII_Date_Time_YMD_UTC  
- Valid values: N/A  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 3  
  
### *horizontal_coordinate_pixel*  
horizontal_coordinate_pixel (sample) is the horizontal coordinate of a specific pixel.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *horizontal_display_axis*  
The horizontal_display_axis attribute identifies, by name, the axis of an Array (or Array subclass) that is intended to be displayed in the horizontal or "sample" dimension on a display device. The value of this attribute must match the value of one, and only one, axis_name attribute in an Axis_Array class of the associated Array.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *horizontal_display_direction*  
The horizontal_display_direction attribute specifies the direction across the screen of a display device that data along the horizontal axis of an Array is supposed to be displayed.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Left to Right  
    - Description: Data along the horizontal axis of an array should be displayed from left to right.  
  - Right to Left  
    - Description: Data along the horizontal axis of an array should be displayed from right to left.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *horizontal_pixel_field_of_view*  
The horizontal_pixel_field_of_view provides the angular measure of the horizontal field of view of a single pixel, and is sometimes referred to as the instantaneous field of view. The pixel_field_of_view_method attribute will designate the method used to determine this value. If the pixel_field_of_view_method attribute is not specified, see the camera documentation for more details.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *horizontal_pixel_footprint*  
The horizontal_pixel_footprint provides the the size of the horizontal field of view of a single pixel projected onto the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *incidence_angle*  
The incidence_angle element provides a measure of the lighting condition at the intercept point. Specifically, it is the angle, measured at the intercept point, between a vector in the direction of an incoming photon from the illumination source and the local surface normal vector. The incidence_angle varies from 0 degrees when the intercept point coincides with the subsolar point to 90 degrees when the intercept is tangent to the surface of the target body. In the context of planetary rings, the local surface normal vector is always on the side of the ring plane illuminated by the light source. Thus, the incidence_angle varies from 0 degrees if the light source illuminates the rings face-on, to 90 degrees if the light source illuminates the rings edge-on.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- in [Illumination_Specific](#illumination_specific):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 4  
- in [Derived_Geometry](#derived_geometry):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
  
### *index_id*  
The index_id attribute supplies a short name (identifier) for the associated value in a group of related values.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 3  
  
### *index_name*  
The index_name attribute supplies the formal name for the associated value in a group of related values.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 3  
  
### *index_sequence_number*  
The index_sequence_number attribute supplies the sequence identifier for the associated value in a group of related values.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 3  
  
### *index_value_angle*  
The index_value_angle attribute provides the value of an angle as named by the associated index_id, index_name, or index_sequence_number.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### *index_value_length*  
The index_value_length attribute provides the value of a length as named by the associated index_id or index_name.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### *index_value_number*  
The index_value_number attribute provides the value with no applicable units as named by the associated index_id or index_name.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### *index_value_string*  
The index_value attribute provides the string value as named by the associated index_id or index_name.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### *index_value_temperature*  
The index_value_temperature attribute provides the value of a temperature as named by the associated index_id or index_name.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: unbounded  
  
### *instrument_azimuth*  
The instrument_azimuth attribute specifies the value for an instrument's rotation in the horizontal direction. It may be measured from a low hard stop, or relative to a coordinate frame. Although it may be used for any instrument where it makes sense, it is primarily intended for use in surface-based instruments that measure pointing in terms of azimuth and elevation. If this value is expressed using a coordinate system, the coordinate system is specified by the Coordinate_Space_Reference class. The interpretation of exactly what part of the instrument is being pointed is mission-specific. It could be the boresight, the camera head direction, the CAHV camera model A vector direction, or any of a number of other things. As such, for multimission use this value should be used mostly as an approximation, e.g. identifying scenes which might contain a given object.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *instrument_elevation*  
The instrument_elevation attribute specifies the value for an instrument's rotation in the vertical direction. It may be usually measured from a low hard stop, or relative to a coordinate frame. Although it may be used for any instrument where it makes sense, it is primarily intended for use in surface-based instruments that measure pointing in terms of azimuth and elevation. If this value is expressed using a coordinate system, the coordinate system is specified by the Coordinate_Space_Reference class. The interpretation of exactly what part of the instrument is being pointed is mission-specific. It could be the boresight, the camera head direction, the CAHV camera model A vector direction, or any of a number of other things. As such, for multimission use this value should be used mostly as an approximation, e.g. identifying scenes that might contain a given object.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *interpolation_algorithm*  
The interpolation_algorithm defines how interpolation was performed. For example, "Piecewise Bilinear" does a piecewise bilinear interpolation between calibration models nearest to the interpolation_value.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *interpolation_sequence*  
When more than one dimension is interpolated, interpolation_sequence define the ordering. Sequence value 1 was interpolated first, directly from calibration; sequence value 2 was interpolated from those results, etc.  
- PDS4 data type: ASCII_Integer  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 9223372036854775807  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *interpolation_value*  
The interpolation_value specifies the value of the variable to which the model was interpolated. The interpretation of the value depends on what the variable is and should be documented in the mission documentation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *interpolation_variable*  
The interpolation_variable defines the parameter across which interpolation is being performed. Examples of variables include Focus, Zoom, and Temperature.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *kernel_provenance*  
The kernel_provenance attribute indicates whether a kernel file is a predict kernel, a reconstructed kernel, some combination of the two, or a kernel for which the distinction is not applicable.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Mixed  
    - Description: This kernel contains both reconstructed and predicted portions (e.g. a reconstructed spacecraft trajectory SPK with a run-out predicted tail).  
  - Predicted  
    - Description: This kernel is a predict kernel (e.g. a pre-encounter predicted spacecraft trajectory SPK ).  
  - Provenance Not Applicable  
    - Description: This kernel does not fit into any of the other categories (e.g., LSKs, SCLKs, text PCKs).  
  - Reconstructed  
    - Description: This kernel is reconstructed based on improved information (e.g. a post-encounter reconstructed spacecraft trajectory SPK based on improved navigation information).  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *kernel_type*  
The kernel_type attribute identifies the type of SPICE kernel.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - CK  
    - Description: SPICE_Kernel is type CK (orientation kernel)  
  - DBK  
    - Description: SPICE_Kernel is type DBK (database kernel)  
  - DSK  
    - Description: SPICE_Kernel is type DSK (digital shape kernel)  
  - EK  
    - Description: SPICE_Kernel is type EK (events kernel)  
  - FK  
    - Description: SPICE_Kernel is type FK (frames kernel)  
  - IK  
    - Description: SPICE_Kernel is type IK (instrument kernel)  
  - LSK  
    - Description: SPICE_Kernel is type LSK (leap seconds kernel)  
  - MK  
    - Description: SPICE_Kernel is type MK (meta kernel, which names SPICE kernels to be used together)  
  - PCK  
    - Description: SPICE_Kernel is type PCL (planetary constants kernel)  
  - SCLK  
    - Description: SPICE_Kernel is type SCLK (spacecraft clock kernel)  
  - SPK  
    - Description: SPICE_Kernel is type SPK (ephemeris kernel)  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *lat_long_method*  
The lat_long_method is used with the attributes start_latitude, stop_latitude, start_longitude and stop_longitude. For most observations these parameters would be multivalued. lat_long_method is used to characterize the start and stop latitude and longitude. The possible values are: 'center' indicating the latitude and longitude values are those at the center of the field of view at the beginning and end of the observation. 'median' indicating the latitude and longitude values are the median values at the beginning and end of the observation. 'mean' indicating the latitude and longitude values are the mean values at the beginning and end of the observation.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Center  
    - Description: The latitude and longitude values given using start_ and stop_ latitude and longitude are those at the center of the field of view at the beginning and end of the observation.  
  - Mean  
    - Description: The latitude and longitude values given using start_ and stop_ latitude and longitude are the mean values at the beginning and end of the observation.  
  - Median  
    - Description: The latitude and longitude values given using start_ and stop_ latitude and longitude are the median values at the beginning and end of the observation.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *latitude_position*  
The latitude component of a Planetocentric position vector. Planetocentric latitude is the angle between the equator plane and a vector connecting the point of interest and the origin of the coordinate system. Latitudes are defined to be positive in the northern (as defined by the IAU) hemisphere.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *latitude_velocity*  
The latitude component of a Planetocentric velocity vector. Planetocentric latitude is the angle between the equator plane and a vector connecting the point of interest and the origin of the coordinate system. Latitudes are defined to be positive in the northern (as defined by the IAU) hemisphere.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *light_time_correction_applied*  
The light_time_correction_applied indicates whether or not light travel time correction and stellar aberration correction were used when calculating the values in the enclosing class. The attribute is nillable with nill_reason = unknown, but only for migrated data. Note: generally, received light travel time is calculated unless a transmitter (e.g., radar, radio) was involved in which the calculation typically is transmitted light time.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - None  
    - Description: Neither light travel time nor stellar aberration was used when calculating the values in the enclosing class.  
  - Received_Light_Time  
    - Description: Received light travel time, but not stellar aberration was used when calculating the values in the enclosing class.  
  - Received_Light_Time_Stellar_Abb  
    - Description: Received light travel time and stellar aberration were used when calculating the values in the enclosing class.  
  - Transmitted_Light_Time  
    - Description: Transmitted light travel time, but not stellar aberration was used when calculating the values in the enclosing class.  
  - Transmitted_Light_Time_Stellar_Abb  
    - Description: Transmitted light travel time and stellar aberration were used when calculating the values in the enclosing class.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: Yes  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *local_identifier*  
The local_identifier attribute provides a character string which uniquely identifies the containing object within the label.  
- PDS4 data type: ASCII_Local_Identifier  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- in [Central_Body_Identification](#central_body_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Coordinate_System_Origin_Identification](#coordinate_system_origin_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Geometry_Target_Identification](#geometry_target_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Observer_Identification](#observer_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Device_Angle](#device_angle):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Device_Temperature](#device_temperature):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Articulation_Device_Parameters](#articulation_device_parameters):  
  - Minimum occurrences: 0  
  - Maximum occurrences: unbounded  
- in [Reference_Frame_Identification](#reference_frame_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Rotate_From](#rotate_from):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Rotate_To](#rotate_to):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Geometry_Lander](#geometry_lander):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Motion_Counter](#motion_counter):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Device_Component_State](#device_component_state):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Device_Motor_Counts](#device_motor_counts):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Coordinate_Space_Definition](#coordinate_space_definition):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
  
### *longitude_position*  
The longitudinal component of a Planetocentric position vector. Planetocentric longitude is measured from the IAU approved prime meridian for the body and increases toward the east.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *longitude_velocity*  
The longitudinal component of a Planetocentric velocity vector. Planetocentric longitude is measured from the IAU approved prime meridian for the body and increases toward the east.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *maximum_emission_angle*  
The maximum_emission_angle element provides the largest value during the observation for the emission angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_incidence_angle*  
The maximum_incidence_angle element provides the largest value during the observation for the incidence angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_latitude*  
The maximum_latitude attribute identifies the final end of the range of values for Planetocentric latitude in an image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_longitude*  
The maximum_longitude attribute identifies the final end of the range of values for Planetocentric longitude in an image. Note that since Planetocentric longitude has values in [0,360], if the range in the product crosses the prime meridian, the value of minimum_longitude will be greater than the value of the maximum_longitude.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_phase_angle*  
The maximum_phase_angle element provides the largest value during the observation for the phase angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_solar_elongation*  
The maximum_solar_elongation element provides the largest value during the observation for the solar elongation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_spacecraft_central_body_distance*  
The maximum_spacecraft_central_body_distance attribute provides the largest value during the observation for the distance between the spacecraft and the center of the central body (e.g., the center of Mars when opperating in the Mars system).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_spacecraft_geocentric_distance*  
The maximum_spacecraft_geocentric_distance attribute provides the largest value during the observation for the distance between the spacecraft and the center of Earth.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_spacecraft_heliocentric_distance*  
The maximum_spacecraft_heliocentric_distance attribute provides the largest value during the observation for the distance between the spacecraft and the center of the Sun.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_spacecraft_target_boresight_intercept_distance*  
The maximum_spacecraft_target_boresight_intercept_distance attribute provides the largest value during the observation for the distance between the spacecraft and the boresight vector intercept point on the surface of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_spacecraft_target_center_distance*  
The maximum_spacecraft_target_center_distance attribute provides the largest value during the observation for the distance between the spacecraft and the center of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_spacecraft_target_subspacecraft_distance*  
The maximum_spacecraft_target_subspacecraft_distance attribute provides the largest value during the observation for the distance between the spacecraft and the subspacecraft point on the surface of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_subsolar_azimuth*  
The maximum_subsolar_azimuth attribute identifies the final end of the range of values for subsolar azimuth in an image. Note that since subsolar azimuth has values in [0,360], if the range in the image crosses the horizontal reference corresponding to zero, the value of minimum_subsolar_azimuth will be greater than the value of the maximum_subsolar_azimuth.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_subsolar_latitude*  
The maximum_subsolar_latitude attribute identifies the final end of the range of values for subsolar latitude in an image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_subsolar_longitude*  
The maximum_subsolar_longitude attribute identifies the final end of the range of values for subsolar longitude in an image. Note that since subsolar longitude has values in [0,360], if the range in the product crosses the prime meridian, the value of minimum_subsolar_longitude will be greater than the value of the maximum_subsolar_longitude.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_subspacecraft_azimuth*  
The maximum_subspacecraft_azimuth attribute identifies the final end of the range of values for subspacecraft azimuth in an image. Note that since subspacecraft azimuth has values in [0,360], if the range in the image crosses the horizontal reference corresponding to zero, the value of minimum_subspacecraft_azimuth will be greater than the value of the maximum_subspacecraft_azimuth.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_subspacecraft_latitude*  
The maximum_subspacecraft_latitude attribute identifies the final end of the range of values for subspacecraft latitude in an image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_subspacecraft_longitude*  
The maximum_subspacecraft_longitude attribute identifies the final end of the range of values for subspacecraft longitude in an image. Note that since subspacecraft longitude has values in [0,360], if the range in the product crosses the prime meridian, the value of minimum_subspacecraft_longitude will be greater than the value of the maximum_subspacecraft_longitude.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_target_geocentric_distance*  
The maximum_target_geocentric_distance attribute provides the largest value for the distance between the center of the target and the center of the Earth during the observation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_target_heliocentric_distance*  
The maximum_target_heliocentric_distance attribute provides the largest value for the distance between the center of the target and the center of the Sun during the observation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *maximum_target_ssb_distance*  
The maximum_target_ssb_distance attribute provides the largest value for the distance between the center of the target and the Solar System Barycenter during the observation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_emission_angle*  
The minimum_emission_angle attribute provides the smallest value during the observation for the emission angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_incidence_angle*  
The minimum_incidence_angle attribute provides the smallest value during the observation for the incidence angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_latitude*  
The minimum_latitude attribute identifies the initial end of the range of values for Planetocentric latitude in an image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_longitude*  
The minimum_longitude attribute identifies the initial end of the range of values for Planetocentric longitude. Note that since Planetocentric longitude has values in [0,360], if the range in the product crosses the prime meridian, the value of minimum_longitude will be greater than the value of the maximum_longitude.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_phase_angle*  
The minimum_phase_angle attribute provides the smallest value during the observation for the phase angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_solar_elongation*  
The minimum_solar_elongation attribute provides the smallest value during the observation for the solar elongation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_spacecraft_central_body_distance*  
The minimum_spacecraft_central_body_distance attribute provides the smallest value during the observation for the distance between the spacecraft and the center of the central body (e.g., the center of Mars when opperating in the Mars system).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_spacecraft_geocentric_distance*  
The minimum_spacecraft_geocentric_distance attribute provides the smallest value during the observation for the distance between the spacecraft and the center of Earth.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_spacecraft_heliocentric_distance*  
The minimum_spacecraft_heliocentric_distance attribute provides the smallest value during the observation for the distance between the spacecraft and the center of the Sun.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_spacecraft_target_boresight_intercept_distance*  
The minimum_spacecraft_target_boresight_intercept_distance attribute provides the smallest value during the observation for the distance between the spacecraft and the boresight vector intercept point on the surface of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_spacecraft_target_center_distance*  
The minimum_spacecraft_target_center_distance attribute provides the smallest value during the observation for the distance between the spacecraft and the center of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_spacecraft_target_subspacecraft_distance*  
The minimum_spacecraft_target_subspacecraft_distance attribute provides the smallest value during the observation for the distance between the spacecraft and the subspacecraft point on the surface of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_subsolar_azimuth*  
The minimum_subsolar_azimuth attribute identifies the initial end of the range of values for subsolar azimuth in an image. Note that since subsolar azimuth has values in [0,360], if the range in the image crosses the horizontal reference corresponding to zero, the value of minimum_subsolar_azimuth will be greater than the value of the maximum_subsolar_azimuth.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_subsolar_latitude*  
The minimum_subsolar_latitude attribute identifies the initial end of the range of values for subsolar latitude in an image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_subsolar_longitude*  
The minimum_subsolar_longitude attribute identifies the initial end of the range of values for subsolar longitude. Note that since subsolar longitude has values in [0,360], if the range in the product crosses the prime meridian, the value of minimum_subsolar_longitude will be greater than the value of the maximum_subsolar_longitude.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_subspacecraft_azimuth*  
The minimum_subspacecraft_azimuth attribute identifies the initial end of the range of values for subspacecraft azimuth in an image. Note that since subspacecraft azimuth has values in [0,360], if the range in the image crosses the horizontal reference corresponding to zero, the value of minimum_subspacecraft_azimuth will be greater than the value of the maximum_subspacecraft_azimuth.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_subspacecraft_latitude*  
The minimum_subspacecraft_latitude attribute identifies the initial end of the range of values for subspacecraft latitude in an image.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_subspacecraft_longitude*  
The minimum_subspacecraft_longitude attribute identifies the initial end of the range of values for subspacecraft longitude. Note that since subspacecraft longitude has values in [0,360], if the range in the product crosses the prime meridian, the value of minimum_subspacecraft_longitude will be greater than the value of the maximum_subspacecraft_longitude.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_target_geocentric_distance*  
The minimum_target_geocentric_distance attribute provides the smallest value for the distance between the center of the target and the center of the Earth during the observation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_target_heliocentric_distance*  
The minimum_target_heliocentric_distance attribute provides the smallest value for the distance between the center of the target and the center of the Sun during the observation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *minimum_target_ssb_distance*  
The minimum_target_ssb_distance attribute provides the smallest value for the distance between the center of the target and the Solar System Barycenter during the observation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *model_type*  
The model_type attribute specifies an identifier for the type or kind of model. The value should be one of a well defined set, providing an application program with sufficient information to know how to handle the rest of the parameters within the model. This value will correlate directly with the specific camera model class that is a subclass of the Camera_Model_Parameters class.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - CAHV  
    - Description: The CAHV model is a linear, perspective-projection camera model (equivalent to a pinhole camera).  
  - CAHVOR  
    - Description: The CAHVOR model is built upon CAHV (see CAHV_Model), adding radial (barrel or pincushion) distortion to the linear model.  
  - CAHVORE  
    - Description: The CAHVORE model is built upon CAHVOR (see CAHVOR_Model), adding support for fisheye lenses.  
  - PSPH  
    - Description: The PSPH model is designed to perform better fisheye-image rectification prior to 1D stereo correlation.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *name*  
The name attribute provides a word or combination of words by which the object is known.  
- PDS4 data type: UTF8_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- in [Device_Pose](#device_pose):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Central_Body_Identification](#central_body_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Coordinate_System_Origin_Identification](#coordinate_system_origin_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Geometry_Target_Identification](#geometry_target_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Observer_Identification](#observer_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Reference_Frame_Identification](#reference_frame_identification):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Rotate_From](#rotate_from):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Rotate_To](#rotate_to):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
- in [Motion_Counter](#motion_counter):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### *north_azimuth*  
Assuming the image is displayed as defined by the Display_Direction class, the north_azimuth attribute provides the value of the angle between a line from the image center to the north pole and a reference line in the image plane. The reference line is a horizontal line from the image center to the middle right edge of the image. This angle is measured from the reference line and increases in a clockwise direction.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *phase_angle*  
The phase_angle element provides a measure of the relationship between the instrument viewing position and incident illumination (such as solar light). Specifically, it is the angle, measured at the intercept point, between a vector in the direction of an incoming photon from the illumination source and a vector in the direction of an outgoing photon to the observing instrument. If illumination is from behind the instrument, phase_angle will be small.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- in [Illumination_Specific](#illumination_specific):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 4  
- in [Derived_Geometry](#derived_geometry):  
  - Minimum occurrences: 1  
  - Maximum occurrences: unbounded  
  
### *pixel_field_of_view_method*  
The pixel_field_of_view_method provides the method used to get the values of the horizontal/vertical_pixel_field_view attributes. If the pixel field of view does not vary across the camera field of view, then this value is 'constant'. If the pixel field of view does vary across the camera field of view, the pixel field of view can be determined either by the center pixel of the camera or the average field of view of the pixel. See the camera documentation for more details.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Average  
    - Description: Pixel field of view varies across the camera field of view and represents the average FOV of the pixel  
  - Central Pixel  
    - Description: Pixel field of view varies across the camera field of view and represents the FOV of the central pixel of the camera  
  - Constant  
    - Description: Pixel field of view does not vary across the camera field of view  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *pixel_latitude*  
The pixel_latitude attribute gives the value of the planetocentric latitude on the target of the projection of a specified pixel.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *pixel_longitude*  
The pixel_longitude attribute gives the value of the planetocentric longitude on the target of the projection of a specified pixel.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *positive_azimuth_direction*  
The positive_azimuth_direction attribute specifies the direction in which azimuth is measured in positive degrees for an observer on the surface of a body. The azimuth is measured with respect to the elevation reference plane. A value of 'clockwise' indicates that azimuth is measured positively clockwise, and 'counterclockwise' indicates that azimuth increases positively counter-clockwise.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - CCW  
    - Description: Indicates that azimuth is measured positively Counter-clockwise.  
  - CW  
    - Description: Indicates that azimuth is measured positively Clockwise.  
  - Clockwise  
    - Description: Indicates that azimuth is measured positively Clockwise.  
  - Counterclockwise  
    - Description: Indicates that azimuth is measured positively Counter-clockwise.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *positive_elevation_direction*  
The positive_elevation_direction attribute provides the direction in which elevation is measured in positive degrees for an observer on the surface of a body. The elevation is measured with respect to the azimuthal reference plane. A value of UP or ZENITH indicates that elevation is measured positively upwards, i.e., the zenith point would be at +90 degrees and the nadir point at -90 degrees. DOWN or NADIR indicates that the elevation is measured positively downwards; the zenith point would be at -90 degrees and the nadir point at +90 degrees.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Down  
    - Description: Indicates that the elevation is measured positively downwards, i.e. the zenith point would be at -90 degrees and the nadir point at +90 degrees.  
  - Nadir  
    - Description: Indicates that the elevation is measured positively downwards, i.e. the zenith point would be at -90 degrees and the nadir point at +90 degrees.  
  - Up  
    - Description: Indicates that elevation is measured positively upwards, i.e., the zenith point would be at +90 degrees and the nadir point at -90 degrees.  
  - Zenith  
    - Description: Indicates that elevation is measured positively upwards, i.e., the zenith point would be at +90 degrees and the nadir point at -90 degrees.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *psph_model_scale_x*  
 Column scale factor to convert between x coordinate and rotation around axis x, expressed in radians/pixel.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *psph_model_scale_y*  
 Column scale factor to convert between y coordinate and rotation around axis y, expressed in radians/pixel.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *qcos*  
qcos is the scalar component of a quaternion. qcos = cos(theta/2), where theta is the angle of rotation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *qsin1*  
qsin1 is the first element of the vector component of a quaternion. qsin1 = x*sin(theta/2) where theta is the angle of rotation and (x,y,z) is the unit vector around which the rotation occurs.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *qsin2*  
qsin2 is the second element of the vector component of a quaternion. qsin2 = y*sin(theta/2) where theta is the angle of rotation and (x,y,z) is the unit vector around which the rotation occurs.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *qsin3*  
qsin3 is the third element of the vector component of a quaternion. qsin3 = z*sin(theta/2) where theta is the angle of rotation and (x,y,z) is the unit vector around which the rotation occurs.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *quaternion_measurement_method*  
Specifies the method by which the coordinate space was measured. This provides an indication of the quality of the definition.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Bundle_Adjustment  
    - Description: Coordinate space position and/or orientation was refined using a bundle adjustment process, minimizing error with respect to some fixed reference (such as an orbital map).  
  - Coarse  
    - Description: The attitude estimate is complete (3-axis), but crude.  
  - Fine  
    - Description: The attitude estimate is complete.  
  - Sun_Find  
    - Description: Coordinate space orientation rotation was measured by finding the location of the sun in one or more images and comparing that to where the sun actually was at that time.  
  - Tilt_Only  
    - Description: The attitude estimate is only good for tilt (2-axis) determination.  
  - Unknown  
    - Description: The attitude should not be trusted.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- in [Coordinate_Space_Quality](#coordinate_space_quality):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Coordinate_Space_Definition](#coordinate_space_definition):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### *radial_velocity*  
The radial component of a spherical or cylindrical velocity vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *radius_position*  
The radial component of a spherical or cylindrical position vector (e.g., the radius coordinate in Planetocentric coordinates).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *reference_location*  
The reference_location indicates the position to which values in the containing class apply. If the reference location is on a target, the target is the one specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Boresight Intercept Point  
    - Description: Values were determined for the point where the boresight vector intersects the designated target.  
  - Constant  
    - Description: Constant is used when the pixel scale does not vary, e.g., for telecentric lenses, maps, or cameras that look at constant, fixed targets, such as microscope stages.  
  - Subspacecraft Point  
    - Description: Values were determined for the subspacecraft point on the designated target.  
  - Target Center  
    - Description: Values were determined for the center of the designated target.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- in [Pixel_Size_Projected](#pixel_size_projected):  
  - Minimum occurrences: 1  
  - Maximum occurrences: 1  
- in [Illumination_Specific](#illumination_specific):  
  - Minimum occurrences: 0  
  - Maximum occurrences: 1  
  
### *reference_pixel_location*  
The reference_pixel_location indicates the position of the pixel to which values in the containing class apply.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Center  
    - Description: Values were determined for the intersection of a vector through the center of the field of view with the specified target.  
  - Lower Left Corner  
    - Description: Values were determined for the intersection of a vector through the lower left corner of the field of view with the specified target.  
  - Lower Right Corner  
    - Description: Values were determined for the intersection of a vector through the lower right corner of the field of view with the specified target.  
  - Upper Left Corner  
    - Description: Values were determined for the intersection of a vector through the upper left corner of the field of view with the specified target.  
  - Upper Right Corner  
    - Description: Values were determined for the intersection of a vector through the upper right corner of the field of view with the specified target.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *right_ascension_angle*  
The right_ascension_angle attribute provides the value of right ascension (RA) as an angle. Right ascension is measured from the vernal equinox or the first point of Aries, which is the place on the celestial sphere where the Sun crosses the celestial equator from south to north at the March equinox. Right ascension is measured continuously in a full circle from that equinox towards the east. Right ascension is used in conjunction with the declination attribute to specify a point on the sky. Note Right Ascension also may be given in hour angles in which case the appropriate attribute is right_ascension_hour_angle.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *right_ascension_hour_angle*  
The right_ascension_hour_angle attribute provides the value of right ascension (RA) as in terms of hour angles (hh.xxx...). Right ascension is measured from the vernal equinox or the first point of Aries, which is the place on the celestial sphere where the Sun crosses the celestial equator from south to north at the March equinox. Right ascension is measured continuously in a full circle from that equinox towards the east. Right ascension is used in conjunction with the declination attribute to specify a point on the sky.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *rotation_direction*  
The rotation_direction attribute identifies the direction of the rotation for a specific quaternion. This is used when the two frames involved are unambiguously identifed in the enclosing classes.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Forward  
    - Description: Reference frames are generally defined sequentially from a base reference frame (e.g., base frames might be ICRF, IAU Mars, or the landing site from which a rover begins its exploration). rotation_direction = Forward corresponds to rotation in the 'direction' from the base frame.  
  - From Base  
    - Description: Reference frames are generally defined sequentially from a base reference frame (e.g., base frames might be ICRF, IAU Mars, or the landing site from which a rover begins its exploration). rotation_direction = Away From Base corresponds to rotation in the 'direction' from the base frame.  
  - Present to Reference  
    - Description: The quaternion rotates the frame identifed by Coordinate_Space_Present to the frame identified by Coordinate_Space_Reference.  
  - Reference to Present  
    - Description: The quaternion rotates the frame identifed by Coordinate_Space_Reference to the frame identified by Coordinate_Space_Present.  
  - Reverse  
    - Description: Reference frames are generally defined sequentially from a base reference frame (e.g., base frames might be ICRF, IAU Mars, or the landing site from which a rover begins its exploration). rotation_direction = Reverse corresponds to rotation toward the base frame.  
  - Toward Base  
    - Description: Reference frames are generally defined sequentially from a base reference frame (e.g., base frames might be ICRF, IAU Mars, or the landing site from which a rover begins its exploration). rotation_direction = Toward Base corresponds to rotation toward the base frame.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *selected_instrument_id*  
The selected_instrument_id attribute specifies an abbreviated name or acronym that identifies the selected instrument mounted on the articulation device.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *solar_azimuth*  
The solar_azimuth attribute specifies one of two angular measurements indicating the direction to the Sun as measured from a specific point on the surface of a planet (eg., from a lander or rover). The positive direction of azimuth is set by the positive_azimuth_direction attribute in the reference coordinate space. The azimuth is measured in the clockwise or counterclockwise direction (as viewed from above) with the meridian passing through the positive spin axis of the planet (i.e., the north pole) defining the zero reference.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0.0  
- Maximum value: 360.0  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *solar_elevation*  
The solar_elevation attribute specifies one of two angular measurements indicating the direction to the Sun as measured from a specific point on the surface of a planet (eg., from a lander or rover). The positive direction of the elevation is set by the positive_elevation_direction attribute in the reference coordinate space. The elevation is measured from the plane which is normal to the line passing between the surface point and the planet's center of mass, and that intersects the surface point.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90.0  
- Maximum value: 90.0  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *solar_elongation*  
The solar_elongation element gives the angle between the line of sight of observation and the direction of the Sun. Note: For IRAS: The line of sight of observation is the boresight of the telescope as measured by the satellite sun sensor.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 4  
  
### *solar_image_clock_angle*  
Describes the direction of the sun in terms of the image plane, defined as a clock angle (clockwise) around the center of the image with 0 pointing to the top of the image, with respect to the display orientation (usually defined by disp:vertical_display_direction).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *solution_id*  
The solution_id attribute specifies the unique identifier for the solution set to which the values in the group belong. For certain kinds of information, such as pointing correction (pointing models) and rover localization (coordinate system definitions), the "true" value is unknown and only estimates of the true value exist. Thus, more than one set of estimates may exist simultaneously, each valid for its intended purpose. Each of these sets is called a "solution" to the unknown true value. The solution_id attribute is used to identify which solution is being expressed by the containing group. No specific naming convention is defined here, however it is recommended that projects adopt one. The intent is to be able to identify who created the solution, and why. Possible components of the naming convention include user, institution, purpose, request ID, version, program, date/time.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *spacecraft_central_body_distance*  
The spacecraft_central_body_distance attribute provides the scalar distance between the spacecraft and the center of the central body (e.g., the center of Mars when opperating in the Mars system).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *spacecraft_geocentric_distance*  
The spacecraft_geocentric_distance attribute provides the scalar distance between the spacecraft and the center of Earth.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *spacecraft_heliocentric_distance*  
The spacecraft_heliocentric_distance attribute provides the scalar distance between the spacecraft and the center of the Sun.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *spacecraft_target_boresight_intercept_distance*  
The spacecraft_target_boresight_intercept_distance attribute provides the scalar distance between the spacecraft and the boresight vector intercept point on the surface of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *spacecraft_target_center_distance*  
The spacecraft_target_center_distance attribute provides the scalar distance between the spacecraft and the center of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *spacecraft_target_subspacecraft_distance*  
The spacecraft_target_subspacecraft_distance attribute provides the scalar distance between the spacecraft and the subspacecraft point on the surface of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *spice_kernel_file_name*  
The spice_kernel_file_name attribute provides the file name of a SPICE kernel file used to process the data or to produce geometric quantities given in the label.  
- PDS4 data type: ASCII_File_Name  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Regex Pattern: [a-zA-Z0-9]([a-zA-Z0-9]|[-]|[_]|[.])*[.][a-zA-Z0-9]+  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *start_azimuth*  
The start_azimuth attribute specifies the angular distance from a fixed reference position at which an image or observation starts. Azimuth is measured in a spherical coordinate system, in a plane normal to the principal axis. Azimuth values increase according to the right hand rule relative to the positive direction of the principal axis of the spherical coordinate system. When applied to a site or surface projection coordinate space, specifies the azimuth of the left edge of the output map. Applies to Cylindrical and Cylindrical-Perspective projections only.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0.0  
- Maximum value: 360.0  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *start_emission_angle*  
The start_emission_angle attribute provides the value at the beginning of the observation (geometry_start_time_utc) for the emission angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_incidence_angle*  
The start_incidence_angle attribute provides the value at the beginning of the observation (geometry_start_time_utc) for the incidence angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_latitude*  
The start_latitude attribute identifies the value of the Planetocentric latitude at the beginning of the observation (geometry_start_time_utc). When either start_latitude or stop_latitude is used, both must be used. In addition the attribute lat_long_method must be used.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_longitude*  
The start_longitude attribute identifies the value of the Planetocentric longitude at the beginning of the observation (geometry_start_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_phase_angle*  
The start_phase_angle attribute provides the value at the beginning of the observation (geometry_start_time_utc) for the phase angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_solar_elongation*  
The start_solar_elongation attribute provides the value at the beginning of the observation (geometry_start_time_utc) for the solar elongation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_spacecraft_central_body_distance*  
The start_spacecraft_central_body_distance attribute provides the scalar distance at the beginning of the observation (geometry_start_time_utc) between the spacecraft and the center of the central body (e.g., the center of Mars when opperating in the Mars system).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_spacecraft_geocentric_distance*  
The start_spacecraft_geocentric_distance attribute provides the scalar distance at the beginning of the observation (geometry_start_time_utc) between the spacecraft and the center of Earth.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_spacecraft_heliocentric_distance*  
The start_spacecraft_heliocentric_distance attribute provides the scalar distance at the beginning of the observation (geometry_start_time_utc) between the spacecraft and the center of the Sun.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_spacecraft_target_boresight_intercept_distance*  
The start_spacecraft_target_boresight_intercept_distance attribute provides the scalar distance at the beginning of the observation (geometry_start_time_utc) between the spacecraft and the boresight vector intercept point on the surface of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_spacecraft_target_center_distance*  
The start_spacecraft_target_center_distance attribute provides the scalar distance at the beginning of the observation (geometry_start_time_utc) between the spacecraft and the center of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_spacecraft_target_subspacecraft_distance*  
The start_spacecraft_target_subspacecraft_distance attribute provides the scalar distance at the beginning of the observation (geometry_start_time_utc) between the spacecraft and the subspacecraft point on the surface of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_subsolar_azimuth*  
The start_subsolar_azimuth attribute identifies the value of the subsolar azimuth at the beginning of the observation (geometry_start_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_subsolar_latitude*  
The start_subsolar_latitude attribute identifies the value of the subsolar latitude at the beginning of the observation (geometry_start_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_subsolar_longitude*  
The start_subsolar_longitude attribute identifies the value of the subsolar longitude at the beginning of the observation (geometry_start_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_subspacecraft_azimuth*  
The start_subspacecraft_azimuth attribute identifies the value of the subspacecraft azimuth at the beginning of the observation (geometry_start_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_subspacecraft_latitude*  
The start_subspacecraft_latitude attribute identifies the value of the subspacecraft latitude at the beginning of the observation (geometry_start_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_subspacecraft_longitude*  
The start_subspacecraft_longitude attribute identifies the value of the subspacecraft longitude at the beginning of the observation (geometry_start_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_target_geocentric_distance*  
The start_target_geocentric_distance attribute provides the scalar distance between the center of the target and the center of the Earth at the beginning of the observation (geometry_start_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_target_heliocentric_distance*  
The start_target_heliocentric_distance attribute provides the scalar distance between the center of the target and the center of the Sun at the beginning of the observation (geometry_start_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *start_target_ssb_distance*  
The start_target_ssb_distance attribute provides the scalar distance between the center of the target and the Solar System Barycenter at the beginning of the observation (geometry_start_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_azimuth*  
The stop_azimuth attribute specifies the angular distance from a fixed reference position at which an image or observation stops. Azimuth is measured in a spherical coordinate system, in a plane normal to the principal axis. Azimuth values increase according to the right hand rule relative to the positive direction of the principal axis of the spherical coordinate system. When applied to a site or surface projection coordinate space, specifies the azimuth of the right edge of the output map. Applies to Cylindrical and Cylindrical-Perspective projections only.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0.0  
- Maximum value: 360.0  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *stop_emission_angle*  
The stop_emission_angle attribute provides the value at the end of the observation (geometry_stop_time_utc) for the emission angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_incidence_angle*  
The stop_incidence_angle attribute provides the value at the end of the observation (geometry_stop_time_utc) for the incidence angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_latitude*  
The stop_latitude attribute identifies the value of the Planetocentric latitude at the end of the observation (geometry_stop_time_utc). When either start_latitude or stop_latitude is used, both must be used. In addition the attribute lat_long_method must be used.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_longitude*  
The stop_longitude attribute identifies the value of the Planetocentric longitude at the end of the observation (geometry_stop_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_phase_angle*  
The stop_phase_angle attribute provides the value at the end of the observation (geometry_stop_time_utc) for the phase angle at the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_solar_elongation*  
The stop_solar_elongation attribute provides the value at the end of the observation (geometry_stop_time_utc) for the solar elongation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 180  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_spacecraft_central_body_distance*  
The stop_spacecraft_central_body_distance attribute provides the scalar distance at the end of the observation (geometry_stop_time_utc) between the spacecraft and the center of the central body (e.g., the center of Mars when opperating in the Mars system).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_spacecraft_geocentric_distance*  
The stop_spacecraft_geocentric_distance attribute provides the scalar distance at the end of the observation (geometry_stop_time_utc) between the spacecraft and the center of Earth.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_spacecraft_heliocentric_distance*  
The stop_spacecraft_heliocentric_distance attribute provides the scalar distance at the end of the observation (geometry_stop_time_utc) between the spacecraft and the center of the Sun.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_spacecraft_target_boresight_intercept_distance*  
The stop_spacecraft_target_boresight_intercept_distance attribute provides the scalar distance at the end of the observation (geometry_stop_time_utc) between the spacecraft and the boresight vector intercept point on the surface of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_spacecraft_target_center_distance*  
The stop_spacecraft_target_center_distance attribute provides the scalar distance at the end of the observation (geometry_stop_time_utc) between the spacecraft and the center of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_spacecraft_target_subspacecraft_distance*  
The stop_spacecraft_target_subspacecraft_distance attribute provides the scalar distance at the end of the observation (geometry_stop_time_utc) between the spacecraft and the subspacecraft point on the surface of the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_subsolar_azimuth*  
The stop_subsolar_azimuth attribute identifies the value of the subsolar azimuth at the end of the observation (geometry_stop_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_subsolar_latitude*  
The stop_subsolar_latitude attribute identifies the value of the subsolar latitude at the end of the observation (geometry_stop_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_subsolar_longitude*  
The stop_subsolar_longitude attribute identifies the value of the subsolar longitude at the end of the observation (geometry_stop_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_subspacecraft_azimuth*  
The stop_subspacecraft_azimuth attribute identifies the value of the subspacecraft azimuth at the end of the observation (geometry_stop_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_subspacecraft_latitude*  
The stop_subspacecraft_latitude attribute identifies the value of the subspacecraft latitude at the end of the observation (geometry_stop_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_subspacecraft_longitude*  
The stop_subspacecraft_longitude attribute identifies the value of the subspacecraft longitude at the end of the observation (geometry_stop_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_target_geocentric_distance*  
The stop_target_geocentric_distance attribute provides the scalar distance between the center of the target and the center of the Earth at the end of the observation (geometry_stop_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_target_heliocentric_distance*  
The stop_target_heliocentric_distance attribute provides the scalar distance between the center of the target and the center of the Sun at the end of the observation (geometry_stop_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *stop_target_ssb_distance*  
The stop_target_ssb_distance attribute provides the scalar distance between the center of the target and the Solar System Barycenter at the end of the observation (geometry_stop_time_utc).  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *subsolar_azimuth*  
The subsolar_azimuth attribute provides the value of the angle between the line from the center of an image to the subsolar point on the target and a horizontal reference line (in the image plane) extending from the image center to the middle right edge of the image. The values of this angle increase in a clockwise direction.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *subsolar_latitude*  
The subsolar_latitude attribute gives the value of the planetocentric latitude at the subsolar point on the target.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *subsolar_longitude*  
The subsolar_longitude attribute gives the value of the planetocentric longitude at the subsolar point on the target.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *subspacecraft_azimuth*  
The subspacecraft_azimuth attribute provides the value of the angle between the line from the center of an image to the subspacecraft point on the target and a horizontal reference line (in the image plane) extending from the image center to the middle right edge of the image. The values of this angle increase in a clockwise direction.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *subspacecraft_latitude*  
The subspacecraft_latitude attribute gives the value of the planetocentric latitude at the subspacecraft point on the target.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -90  
- Maximum value: 90  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *subspacecraft_longitude*  
The subspacecraft_longitude attribute gives the value of the planetocentric longitude at the subspacecraft point on the target.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *sun_direction_clock_angle*  
The sun_direction_clock_angle attribute specifies the direction of the sun as an angle measured from a line 'upward' from the center of the field of view, clockwise to the direction toward sun, assuming the image is displayed as defined by the Display_Direction class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *target_geocentric_distance*  
The target_geocentric_distance attribute provides the scalar distance between the center of the target and the center of the Earth.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *target_heliocentric_distance*  
The target_heliocentric_distance attribute provides the scalar distance between the center of the target and the center of the Sun.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *target_name*  
Specifies the name of the target location for items in this class.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *target_north_pole_clock_angle*  
The target_north_pole_clock_angle element specifies the direction of the target body's rotation axis in an image. It is measured from the 'upward' direction in the image, clockwise to the direction of the northern rotational pole as projected into the image plane, assuming the image is displayed as defined by the Display_Direction class. The north pole of a planet or any of its satellites in the solar system is the pole of the rotation axis that is in the same celestial hemisphere relative to the invariable plane of the solar system as Earth's North pole.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *target_positive_pole_clock_angle*  
The target_positive_pole_clock_angle element specifies the direction of the target body's rotation axis in an image. It is measured from the 'upward' direction in the image, clockwise to the direction of the positive rotational pole as projected into the image plane, assuming the image is displayed as defined by the Display_Direction class. The positive pole is defined as the pole toward which the thumb points when the fingers of the right hand are curled in the body's direction of rotation.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *target_ssb_distance*  
The target_ssb_distance attribute provides the scalar distance between the center of the target and the Solar System Barycenter.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: unbounded  
  
### *vertical_coordinate_pixel*  
vertical_coordinate_pixel (line) is the vertical coordinate of a specific pixel.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *vertical_display_axis*  
The vertical_display_axis attribute identifies, by name, the axis of an Array (or Array subclass) that is intended to be displayed in the vertical or "line" dimension on a display device. The value of this attribute must match the value of one, and only one, axis_name attribute in an Axis_Array class of the associated Array.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values: N/A  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *vertical_display_direction*  
The vertical_display_direction attribute specifies the direction along the screen of a display device that data along the vertical axis of an Array is supposed to be displayed.  
- PDS4 data type: ASCII_Short_String_Collapsed  
- Valid values:  
  - Bottom to Top  
    - Description: Data along the vertical axis of an array should be displayed from the bottom to the top of the display device.  
  - Top to Bottom  
    - Description: Data along the vertical axis of an array should be displayed from the top to the bottom of the display device.  
- Minimum Length: 1  
- Maximum Length: 255  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *vertical_pixel_field_of_view*  
The vertical_pixel_field_of_view provides the angular measure of the vertical field of view of a single pixel, and is sometimes referred to as the instantaneous field of view. The pixel_field_of_view_method attribute will designate the method used to determine this value. If the pixel_field_of_view_method attribute is not specified, see the camera documentation for more details.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: 0  
- Maximum value: 360  
- Nillable: No  
- Minimum occurrences: 0  
- Maximum occurrences: 1  
  
### *vertical_pixel_footprint*  
The vertical_pixel_footprint provides the size of the vertical field of view of a single pixel projected onto the target specified in the parent Geometry_Orbiter class.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *x*  
The x component of a Cartesian vector which has no units.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *x_acceleration*  
The x component of a Cartesian acceleration vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *x_pixel*  
The x component of a Cartesian pixel vector; typically used in cameral models.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *x_position*  
The x component of a Cartesian position vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *x_unit*  
The x component of a unit Cartesian vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1  
- Maximum value: 1  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *x_velocity*  
The x component of a Cartesian velocity vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *y*  
The y component of a Cartesian vector which has no units.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *y_acceleration*  
The y component of a Cartesian acceleration vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *y_pixel*  
The y component of a Cartesian pixel vector; typically used in cameral models.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *y_position*  
The y component of a Cartesian position vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *y_unit*  
The y component of a unit Cartesian vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1  
- Maximum value: 1  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *y_velocity*  
The y component of a Cartesian velocity vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *z*  
The z component of a Cartesian vector which has no units.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *z_acceleration*  
The z component of a Cartesian acceleration vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *z_pixel*  
The z component of a Cartesian pixel vector; typically used in cameral models.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *z_position*  
The z component of a Cartesian position vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *z_unit*  
The z component of a unit Cartesian vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1  
- Maximum value: 1  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
### *z_velocity*  
The z component of a Cartesian velocity vector.  
- PDS4 data type: ASCII_Real  
- Valid values: N/A  
- Minimum value: -1.7976931348623157e+308  
- Maximum value: 1.7976931348623157e+308  
- Nillable: No  
- Minimum occurrences: 1  
- Maximum occurrences: 1  
  
# Examples  
  
Example PDS4 label snippet from urn:nasa:pds:mro_crism_ddr_1001:data_ddr:msp00002f9e_01_de214l_ddr1::1.0:  
```
<Discipline_Area>
  ...
  <geom:Geometry>
    <geom:SPICE_Kernel_Files>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>SCLK</geom:kernel_type>
        <geom:spice_kernel_file_name>MRO_SCLKSCET.00018.65536.tsc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>FK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_v08.tf</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>FK</geom:kernel_type>
        <geom:spice_kernel_file_name>MRO_CRISM_FK_0000_000_N_1.TF</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>IK</geom:kernel_type>
        <geom:spice_kernel_file_name>MRO_CRISM_IK_0000_000_N_1.TI</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>LSK</geom:kernel_type>
        <geom:spice_kernel_file_name>naif0008.tls</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>PCK</geom:kernel_type>
        <geom:spice_kernel_file_name>pck00008.tpc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-08.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-09.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-10.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-11.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-12.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-13.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-14.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-15.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-16.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-17.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-18.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-19.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-20.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-21.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_sc_2006-11-22.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_312_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_313_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_314_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_315_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_316_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_317_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_318_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_319_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_320_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_321_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_322_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_323_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_324_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>CK</geom:kernel_type>
        <geom:spice_kernel_file_name>spck_2006_325_r_1.bc</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>SPK</geom:kernel_type>
        <geom:spice_kernel_file_name>de410.bsp</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>SPK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_cruise.bsp</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>SPK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_ab.bsp</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>SPK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_psp.bsp</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
      <geom:SPICE_Kernel_Identification>
        <geom:kernel_type>SPK</geom:kernel_type>
        <geom:spice_kernel_file_name>mro_psp_rec.bsp</geom:spice_kernel_file_name>
        <geom:kernel_provenance>Reconstructed</geom:kernel_provenance>
      </geom:SPICE_Kernel_Identification>
    </geom:SPICE_Kernel_Files>
    <geom:Geometry_Orbiter>
      <geom:geometry_start_time_utc>2006-11-12T06:03:19.074Z</geom:geometry_start_time_utc>
      <geom:geometry_stop_time_utc>2006-11-12T06:06:19.003Z</geom:geometry_stop_time_utc>
      <geom:Orbiter_Identification>
        <geom:Geometry_Target_Identification>
          <geom:name>Mars</geom:name>
        </geom:Geometry_Target_Identification>
      </geom:Orbiter_Identification>
      <geom:Distances>
        <geom:Distances_Specific>
          <geom:target_heliocentric_distance unit="km">235913328.707360</geom:target_heliocentric_distance>
          <geom:spacecraft_target_center_distance unit="km">3687.045950</geom:spacecraft_target_center_distance>
        </geom:Distances_Specific>
      </geom:Distances>
    </geom:Geometry_Orbiter>
  </geom:Geometry>
  ...
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:mer_pancam_photometry:data_finalsols:2p298938988iofb1e5p2384l2c2_photometry::1.0:  
```
<Discipline_Area>
  ...
  <geom:Geometry>
    <geom:SPICE_Kernel_Files>
      <geom:SPICE_Kernel_Identification>
        <geom:spice_kernel_file_name>chronos.mer</geom:spice_kernel_file_name>
      </geom:SPICE_Kernel_Identification>
    </geom:SPICE_Kernel_Files>
    <geom:Geometry_Lander>
      <geom:Motion_Counter>
        <geom:name>Rover Motion Counter</geom:name>
        <local_identifier>Rover_Motion_Counter</local_identifier>
        <geom:Motion_Counter_Index>
          <geom:index_name>Site</geom:index_name>
          <geom:index_value_number>137</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_name>Drive</geom:index_name>
          <geom:index_value_number>249</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_name>IDD</geom:index_name>
          <geom:index_value_number>143</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_name>PMA</geom:index_name>
          <geom:index_value_number>315</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_name>HGA</geom:index_name>
          <geom:index_value_number>346</geom:index_value_number>
        </geom:Motion_Counter_Index>
      </geom:Motion_Counter>
    </geom:Geometry_Lander>
  </geom:Geometry>
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:kplo-shadowcam:data-raw:m050203503se::1.0:  
```
<Discipline_Area>
  <geom:Geometry>
    <geom:Geometry_Orbiter>
      <geom:geometry_reference_time_utc>2024-03-08T00:33:04.180651Z</geom:geometry_reference_time_utc>
      <geom:Orbiter_Identification>
        <geom:Central_Body_Identification>
          <geom:body_spice_name>EARTH</geom:body_spice_name>
          <geom:name>Earth</geom:name>
          <Internal_Reference>
            <lid_reference>urn:nasa:pds:context:target:planet.earth</lid_reference>
            <reference_type>geometry_to_body</reference_type>
          </Internal_Reference>
        </geom:Central_Body_Identification>
        <geom:Geometry_Target_Identification>
          <geom:body_spice_name>MOON</geom:body_spice_name>
          <geom:name>Moon</geom:name>
          <Internal_Reference>
            <lid_reference>urn:nasa:pds:context:target:satellite.earth.moon</lid_reference>
            <reference_type>geometry_to_body</reference_type>
          </Internal_Reference>
        </geom:Geometry_Target_Identification>
        <geom:Coordinate_System_Identification>
          <geom:coordinate_system_type>Planetocentric</geom:coordinate_system_type>
          <geom:Coordinate_System_Origin_Identification>
            <geom:body_spice_name>MOON</geom:body_spice_name>
            <geom:name>Moon</geom:name>
            <Internal_Reference>
              <lid_reference>urn:nasa:pds:context:target:satellite.earth.moon</lid_reference>
              <reference_type>geometry_to_body</reference_type>
            </Internal_Reference>
          </geom:Coordinate_System_Origin_Identification>
          <geom:Reference_Frame_Identification>
            <geom:frame_spice_name>KPLO_SHC_A</geom:frame_spice_name>
            <geom:name>ShadowCam</geom:name>
            <Internal_Reference>
              <lid_reference>urn:kari:kpds:context:instrument:kplo.shc</lid_reference>
              <reference_type>geometry_to_reference_frame</reference_type>
            </Internal_Reference>
          </geom:Reference_Frame_Identification>
        </geom:Coordinate_System_Identification>
      </geom:Orbiter_Identification>
      <geom:Pixel_Dimensions>
        <geom:pixel_field_of_view_method>Central Pixel</geom:pixel_field_of_view_method>
        <geom:Pixel_Size_Projected>
          <geom:distance unit="km">1837.863</geom:distance>
          <geom:horizontal_pixel_footprint unit="m">1.7256</geom:horizontal_pixel_footprint>
          <geom:vertical_pixel_footprint unit="m">3.086</geom:vertical_pixel_footprint>
        </geom:Pixel_Size_Projected>
      </geom:Pixel_Dimensions>
      <geom:Distances>
        <geom:Distances_Specific>
          <geom:spacecraft_target_subspacecraft_distance unit="km">100.557</geom:spacecraft_target_subspacecraft_distance>
          <geom:target_heliocentric_distance unit="km">148194655.537</geom:target_heliocentric_distance>
        </geom:Distances_Specific>
      </geom:Distances>
      <geom:Surface_Geometry>
        <geom:Surface_Geometry_Specific>
          <geom:Pixel_Intercept>
            <geom:reference_pixel_location>Center</geom:reference_pixel_location>
            <geom:pixel_latitude unit="deg">16.729696</geom:pixel_latitude>
            <geom:pixel_longitude unit="deg">354.035502</geom:pixel_longitude>
          </geom:Pixel_Intercept>
          <geom:subsolar_latitude unit="deg">-0.744</geom:subsolar_latitude>
          <geom:subsolar_longitude unit="deg">208.833</geom:subsolar_longitude>
          <geom:subspacecraft_latitude unit="deg">16.729829</geom:subspacecraft_latitude>
          <geom:subspacecraft_longitude unit="deg">354.035453</geom:subspacecraft_longitude>
        </geom:Surface_Geometry_Specific>
      </geom:Surface_Geometry>
      <geom:Illumination_Geometry>
        <geom:Illumination_Specific>
          <geom:reference_location>Boresight Intercept Point</geom:reference_location>
          <geom:emission_angle unit="deg">0.003</geom:emission_angle>
          <geom:incidence_angle unit="deg">142.194</geom:incidence_angle>
          <geom:phase_angle unit="deg">142.192</geom:phase_angle>
        </geom:Illumination_Specific>
      </geom:Illumination_Geometry>
    </geom:Geometry_Orbiter>
  </geom:Geometry>
  ...
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:mars2020_imgops:data_rmi_imgops:lrf_0050_0671384429_129eby_n0031950scam01050_0200i6j::2.0:  
```
<Discipline_Area>
  ...
  <geom:Geometry>
    <geom:SPICE_Kernel_Files>
      <geom:SPICE_Kernel_Identification>
        <geom:spice_kernel_file_name>chronos.m2020_ops210303_v1</geom:spice_kernel_file_name>
      </geom:SPICE_Kernel_Identification>
    </geom:SPICE_Kernel_Files>
    <geom:Geometry_Lander>
      <geom:geometry_state>Telemetry</geom:geometry_state>
      <geom:description>Geometry as reported by the spacecraft in telemetry</geom:description>
      <local_identifier>geom_telemetry_state</local_identifier>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>RSM</geom:device_id>
        <geom:device_name>REMOTE SENSING MAST</geom:device_name>
        <geom:device_mode>DEPLOYED</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH FINAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">0.13336</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION FINAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">1.08131</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH INITIAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">0.142708</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION INITIAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">1.08157</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH REQUESTED</geom:index_id>
            <geom:index_value_angle unit="rad">0.13799</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION REQUESTED</geom:index_id>
            <geom:index_value_angle unit="rad">1.08378</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH FINAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">0.138015</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION FINAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">1.08373</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH INITIAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">0.147366</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION INITIAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">1.08405</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
        <geom:Device_Temperature>
          <geom:Device_Temperature_Index>
            <geom:index_id>NAVCAM LEFT CAMERA PLATE</geom:index_id>
            <geom:index_value_temperature unit="degC">-19.9337</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>NAVCAM RIGHT CAMERA PLATE</geom:index_id>
            <geom:index_value_temperature unit="degC">-22.3957</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
        </geom:Device_Temperature>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>ARM</geom:device_id>
        <geom:device_name>SAMPLE ARM</geom:device_name>
        <geom:selected_instrument_id>WATSON</geom:selected_instrument_id>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 1 AZIMUTH-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">1.57291</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 2 ELEVATION-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">-0.286141</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 3 ELBOW-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">-2.81942</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 4 WRIST-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">3.11076</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 5 TURRET-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">4.86046</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 1 AZIMUTH-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">1.57242</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 2 ELEVATION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-0.285657</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 3 ELBOW-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-2.82089</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 4 WRIST-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">3.10984</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 5 TURRET-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">4.86077</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SCS DOCKING CLOCK ANGLE</geom:index_id>
            <geom:index_value_angle unit="rad">0.0602604</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
        <geom:Device_Component_State>
          <geom:Device_Component_State_Index>
            <geom:index_id>PRELOAD_VALUE</geom:index_id>
            <geom:index_value_string>0</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>PRELOAD_TOOL</geom:index_id>
            <geom:index_value_string>WATSON</geom:index_value_string>
          </geom:Device_Component_State_Index>
        </geom:Device_Component_State>
        <geom:Device_Component_State>
          <geom:Device_Component_State_Index>
            <geom:index_id>FACILITY CONTACT SENSOR A</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>FACILITY CONTACT SENSOR B</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DRILL STABILIZER 1</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DRILL STABILIZER 2</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 1</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 2</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 3</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 4</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
        </geom:Device_Component_State>
        <geom:Device_Temperature>
          <geom:Device_Temperature_Index>
            <geom:index_id>AZIMUTH JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-30.2288</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>ELEVATION JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-26.7067</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>ELBOW JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-19.0049</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>WRIST JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-20.6965</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>TURRET JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-35.3106</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>DEFLECTION BODY DELTA TEMPERATURE</geom:index_id>
            <geom:index_value_temperature unit="degC">0.0</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>DEFLECTION ARM DELTA TEMPERATURE</geom:index_id>
            <geom:index_value_temperature unit="degC">-39.3098</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
        </geom:Device_Temperature>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>CHASSIS</geom:device_id>
        <geom:device_name>MOBILITY CHASSIS</geom:device_name>
        <geom:device_mode>DEPLOYED</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT FRONT WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">4.26106e-05</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT FRONT WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">-0.00127832</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT REAR WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">-4.26106e-05</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT REAR WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">4.26106e-05</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT BOGIE</geom:index_id>
            <geom:index_value_angle unit="rad">0.0551918</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT BOGIE</geom:index_id>
            <geom:index_value_angle unit="rad">-0.0215051</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT DIFFERENTIAL</geom:index_id>
            <geom:index_value_angle unit="rad">0.00230504</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT DIFFERENTIAL</geom:index_id>
            <geom:index_value_angle unit="rad">0.0116871</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT FRONT WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT FRONT WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT MIDDLE WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT MIDDLE WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT REAR WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT REAR WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
        <geom:Vector_Device_Gravity>
          <geom:x_unit>-3.9421636155334935E-4</geom:x_unit>
          <geom:y_unit>-0.0019710871901479155</geom:y_unit>
          <geom:z_unit>0.9999979797023337</geom:z_unit>
        </geom:Vector_Device_Gravity>
        <geom:Vector_Device_Gravity_Magnitude>
          <geom:x_acceleration unit="m/s**2">-0.00146484</geom:x_acceleration>
          <geom:y_acceleration unit="m/s**2">-0.00732422</geom:y_acceleration>
          <geom:z_acceleration unit="m/s**2">3.71582</geom:z_acceleration>
        </geom:Vector_Device_Gravity_Magnitude>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>HGA</geom:device_id>
        <geom:device_name>HIGH GAIN ANTENNA</geom:device_name>
        <geom:device_mode>DEPLOYED</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH</geom:index_id>
            <geom:index_value_angle unit="rad">1.13452</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION</geom:index_id>
            <geom:index_value_angle unit="rad">-0.785009</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>DRILL</geom:device_id>
        <geom:device_name>DRILL</geom:device_name>
        <geom:device_mode>INVALID POSE</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>SPINDLE OUTPUT POSITION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">2265.72</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>CHUCK POSITION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-0.468715</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>PERCUSS POSITION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>SCS</geom:device_id>
        <geom:device_name>SAMPLE CACHE SYSTEM</geom:device_name>
        <geom:device_mode>EMPTY</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>SCS BIT CAROUSEL-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">-1.39662</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SCS BIT CAROUSEL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-1.39571</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>SHA</geom:device_id>
        <geom:device_name>SAMPLE HANDLING ARM</geom:device_name>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 1 Z-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0179931</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 2 SHOULDER-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">-0.239298</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 3 ELBOW-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">2.68485</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 1 Z-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 2 SHOULDER-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-0.239698</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 3 ELBOW-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">2.68397</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Camera_Model_Parameters>
        <geom:model_type>CAHV</geom:model_type>
        <geom:calibration_source_id>1</geom:calibration_source_id>
        <geom:CAHV_Model>
          <geom:Vector_Center>
            <geom:x_position unit="m">0.840641</geom:x_position>
            <geom:y_position unit="m">0.676759</geom:y_position>
            <geom:z_position unit="m">-2.19275</geom:z_position>
          </geom:Vector_Center>
          <geom:Vector_Axis>
            <geom:x_unit>-0.845915</geom:x_unit>
            <geom:y_unit>-0.531705</geom:y_unit>
            <geom:z_unit>-0.0416555</geom:z_unit>
          </geom:Vector_Axis>
          <geom:Vector_Horizontal>
            <geom:x_pixel>8279.85</geom:x_pixel>
            <geom:y_pixel>-80438.1</geom:y_pixel>
            <geom:z_pixel>-291.596</geom:z_pixel>
          </geom:Vector_Horizontal>
          <geom:Vector_Vertical>
            <geom:x_pixel>38130.9</geom:x_pixel>
            <geom:y_pixel>4180.11</geom:y_pixel>
            <geom:z_pixel>69888.3</geom:z_pixel>
          </geom:Vector_Vertical>
        </geom:CAHV_Model>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ROVER_NAV_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>3</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>1950</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>4</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
        <geom:Quaternion_Model_Transform>
          <geom:qcos>0.0550875</geom:qcos>
          <geom:qsin1>-0.249146</geom:qsin1>
          <geom:qsin2>-0.0129946</geom:qsin2>
          <geom:qsin3>-0.966811</geom:qsin3>
        </geom:Quaternion_Model_Transform>
        <geom:Vector_Model_Transform>
          <geom:x>0.804896</geom:x>
          <geom:y>0.559435</geom:y>
          <geom:z>-1.91903</geom:z>
        </geom:Vector_Model_Transform>
      </geom:Camera_Model_Parameters>
      <geom:Coordinate_Space_Definition>
        <local_identifier>ROVER_NAV_FRAME_3_1950_4_0_0_0_108_102_0_0</local_identifier>
        <local_identifier>ROVER_NAV_FRAME_3_1950_4_0_0_0_108_102_0_0_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ROVER_NAV_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>3</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>1950</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>4</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>108</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>102</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">10.3131</geom:x_position>
          <geom:y_position unit="m">65.9943</geom:y_position>
          <geom:z_position unit="m">0.715083</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.00131628</geom:qcos>
          <geom:qsin1>0.000646026</geom:qsin1>
          <geom:qsin2>-0.000920782</geom:qsin2>
          <geom:qsin3>0.999999</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>SITE_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>3</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
        <geom:Coordinate_Space_Quality>
          <geom:quaternion_measurement_method>Sun_Find</geom:quaternion_measurement_method>
        </geom:Coordinate_Space_Quality>
      </geom:Coordinate_Space_Definition>
      <geom:Coordinate_Space_Definition>
        <local_identifier>RSM_HEAD_FRAME_3_1950_4_0_0_0_108_102_0_0</local_identifier>
        <local_identifier>RSM_HEAD_FRAME_3_1950_4_0_0_0_108_102_0_0_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>RSM_HEAD_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>3</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>1950</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>4</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>108</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>102</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">0.804896</geom:x_position>
          <geom:y_position unit="m">0.559435</geom:y_position>
          <geom:z_position unit="m">-1.91903</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.0550875</geom:qcos>
          <geom:qsin1>-0.249146</geom:qsin1>
          <geom:qsin2>-0.0129946</geom:qsin2>
          <geom:qsin3>-0.966811</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ROVER_NAV_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>3</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>1950</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>4</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>108</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>102</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
      </geom:Coordinate_Space_Definition>
      <geom:Coordinate_Space_Definition>
        <local_identifier>TURRET_FRAME_3_1950_4_0_0_0_108_102_0_0</local_identifier>
        <local_identifier>TURRET_FRAME_3_1950_4_0_0_0_108_102_0_0_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>TURRET_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>3</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>1950</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>4</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>108</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>102</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">1.08465</geom:x_position>
          <geom:y_position unit="m">-0.429047</geom:y_position>
          <geom:z_position unit="m">-1.40261</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.997183</geom:qcos>
          <geom:qsin1>-0.00159368</geom:qsin1>
          <geom:qsin2>0.000841571</geom:qsin2>
          <geom:qsin3>0.0749847</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ROVER_NAV_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>3</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>1950</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>4</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>108</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>102</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
      </geom:Coordinate_Space_Definition>
      <geom:Coordinate_Space_Definition>
        <local_identifier>ARM_WATSON_FRAME_3_1950_4_0_0_0_108_102_0_0</local_identifier>
        <local_identifier>ARM_WATSON_FRAME_3_1950_4_0_0_0_108_102_0_0_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ARM_WATSON_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>3</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>1950</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>4</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>108</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>102</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">1.01786</geom:x_position>
          <geom:y_position unit="m">-0.760246</geom:y_position>
          <geom:z_position unit="m">-1.4157</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.633384</geom:qcos>
          <geom:qsin1>-0.00160347</geom:qsin1>
          <geom:qsin2>-0.000822763</geom:qsin2>
          <geom:qsin3>-0.773835</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ROVER_NAV_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>3</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>1950</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>4</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>108</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>102</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
      </geom:Coordinate_Space_Definition>
      <geom:Derived_Geometry>
        <geom:instrument_azimuth unit="deg">186.309</geom:instrument_azimuth>
        <geom:instrument_elevation unit="deg">-29.0427</geom:instrument_elevation>
        <geom:solar_azimuth unit="deg">77.7284</geom:solar_azimuth>
        <geom:solar_elevation unit="deg">66.699</geom:solar_elevation>
        <geom:Vector_Solar_Direction>
          <geom:x_unit>0.0840752</geom:x_unit>
          <geom:y_unit>0.386524</geom:y_unit>
          <geom:z_unit>-0.918439</geom:z_unit>
        </geom:Vector_Solar_Direction>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ROVER_NAV_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>3</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>1950</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>4</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>108</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>102</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
      </geom:Derived_Geometry>
      <geom:Derived_Geometry>
        <geom:target_name>SuperCam Calibration Target</geom:target_name>
        <geom:incidence_angle unit="deg">49.2748</geom:incidence_angle>
        <geom:phase_angle unit="deg">56.2162</geom:phase_angle>
        <geom:instrument_azimuth unit="deg">6.09582</geom:instrument_azimuth>
        <geom:instrument_elevation unit="deg">-28.9805</geom:instrument_elevation>
        <geom:solar_azimuth unit="deg">257.997</geom:solar_azimuth>
        <geom:solar_elevation unit="deg">66.0889</geom:solar_elevation>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>SITE_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>3</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
      </geom:Derived_Geometry>
      <geom:Derived_Geometry>
        <geom:target_name>Mars</geom:target_name>
        <geom:target_heliocentric_distance unit="km">2.43024e+08</geom:target_heliocentric_distance>
      </geom:Derived_Geometry>
      <geom:Motion_Counter>
        <geom:name>RMC</geom:name>
        <geom:Motion_Counter_Index>
          <geom:index_id>SITE</geom:index_id>
          <geom:index_value_number>3</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>DRIVE</geom:index_id>
          <geom:index_value_number>1950</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>POSE</geom:index_id>
          <geom:index_value_number>4</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>ARM</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>SHA</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>DRILL</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>RSM</geom:index_id>
          <geom:index_value_number>108</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>HGA</geom:index_id>
          <geom:index_value_number>102</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>BITCAR</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>SEAL</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
      </geom:Motion_Counter>
    </geom:Geometry_Lander>
  </geom:Geometry>
  ...
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:mars2020_mastcamz_ops_calibrated:data:zl2_0445_0706443429_363rad_t0250214zcam03366_110300j::2.0:  
```
<Discipline_Area>
  ...
  <geom:Geometry>
    <geom:SPICE_Kernel_Files>
      <geom:SPICE_Kernel_Identification>
        <geom:spice_kernel_file_name>chronos.m2020_ops210303_v1</geom:spice_kernel_file_name>
      </geom:SPICE_Kernel_Identification>
    </geom:SPICE_Kernel_Files>
    <geom:Geometry_Lander>
      <geom:geometry_state>Telemetry</geom:geometry_state>
      <geom:description>Geometry as reported by the spacecraft in telemetry</geom:description>
      <local_identifier>geom_telemetry_state</local_identifier>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>RSM</geom:device_id>
        <geom:device_name>REMOTE SENSING MAST</geom:device_name>
        <geom:device_mode>DEPLOYED</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH FINAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">2.44864</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION FINAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">1.09329</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH INITIAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">2.53138</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION INITIAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">1.00343</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH REQUESTED</geom:index_id>
            <geom:index_value_angle unit="rad">2.4533</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION REQUESTED</geom:index_id>
            <geom:index_value_angle unit="rad">1.0959</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH FINAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">2.4533</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION FINAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">1.09587</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH INITIAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">2.53591</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION INITIAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">1.00607</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
        <geom:Device_Temperature>
          <geom:Device_Temperature_Index>
            <geom:index_id>NAVCAM LEFT CAMERA PLATE</geom:index_id>
            <geom:index_value_temperature unit="degC">-15.7796</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>NAVCAM RIGHT CAMERA PLATE</geom:index_id>
            <geom:index_value_temperature unit="degC">-19.5222</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
        </geom:Device_Temperature>
        <geom:Commanded_Geometry>
          <geom:command_type>No_Motion</geom:command_type>
          <geom:Device_Angle>
            <geom:Device_Angle_Index>
              <geom:index_name>Unknown</geom:index_name>
              <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
            </geom:Device_Angle_Index>
          </geom:Device_Angle>
        </geom:Commanded_Geometry>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>ARM</geom:device_id>
        <geom:device_name>SAMPLE ARM</geom:device_name>
        <geom:selected_instrument_id>DOCKING POST</geom:selected_instrument_id>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 1 AZIMUTH-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">1.57291</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 2 ELEVATION-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">-0.286141</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 3 ELBOW-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">-2.81942</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 4 WRIST-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">3.11068</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 5 TURRET-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">4.86046</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 1 AZIMUTH-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">1.57232</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 2 ELEVATION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-0.285633</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 3 ELBOW-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-2.82144</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 4 WRIST-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">3.10981</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 5 TURRET-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">4.86115</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SCS DOCKING CLOCK ANGLE</geom:index_id>
            <geom:index_value_angle unit="rad">0.0600421</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
        <geom:Device_Component_State>
          <geom:Device_Component_State_Index>
            <geom:index_id>PRELOAD_VALUE</geom:index_id>
            <geom:index_value_string>0</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>PRELOAD_TOOL</geom:index_id>
            <geom:index_value_string>DOCKING POST</geom:index_value_string>
          </geom:Device_Component_State_Index>
        </geom:Device_Component_State>
        <geom:Device_Component_State>
          <geom:Device_Component_State_Index>
            <geom:index_id>FACILITY CONTACT SENSOR A</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>FACILITY CONTACT SENSOR B</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DRILL STABILIZER 1</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DRILL STABILIZER 2</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 1</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 2</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 3</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 4</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
        </geom:Device_Component_State>
        <geom:Device_Pose>
          <geom:name>arm_attitude_reference</geom:name>
          <geom:Quaternion_Plus_Direction>
            <geom:qcos>0.704803</geom:qcos>
            <geom:qsin1>-0.0706213</geom:qsin1>
            <geom:qsin2>0.0760767</geom:qsin2>
            <geom:qsin3>-0.701768</geom:qsin3>
            <geom:rotation_direction>Forward</geom:rotation_direction>
          </geom:Quaternion_Plus_Direction>
        </geom:Device_Pose>
        <geom:Device_Temperature>
          <geom:Device_Temperature_Index>
            <geom:index_id>AZIMUTH JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-39.7362</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>ELEVATION JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-40.322</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>ELBOW JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-32.2912</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>WRIST JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-36.5628</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>TURRET JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-46.4838</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>DEFLECTION BODY DELTA TEMPERATURE</geom:index_id>
            <geom:index_value_temperature unit="degC">0.0</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>DEFLECTION ARM DELTA TEMPERATURE</geom:index_id>
            <geom:index_value_temperature unit="degC">-41.0597</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
        </geom:Device_Temperature>
        <geom:Vector_Device_Gravity>
          <geom:x_unit>0.20635797176158457</geom:x_unit>
          <geom:y_unit>-0.007228209010878198</geom:y_unit>
          <geom:z_unit>0.9784498661070684</geom:z_unit>
        </geom:Vector_Device_Gravity>
        <geom:Vector_Device_Gravity_Magnitude>
          <geom:x_acceleration unit="m/s**2">0.206358</geom:x_acceleration>
          <geom:y_acceleration unit="m/s**2">-0.00722821</geom:y_acceleration>
          <geom:z_acceleration unit="m/s**2">0.97845</geom:z_acceleration>
        </geom:Vector_Device_Gravity_Magnitude>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>CHASSIS</geom:device_id>
        <geom:device_name>MOBILITY CHASSIS</geom:device_name>
        <geom:device_mode>DEPLOYED</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT FRONT WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">4.26106e-05</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT FRONT WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">-0.000127832</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT REAR WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">-0.000213053</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT REAR WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.000426106</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT BOGIE</geom:index_id>
            <geom:index_value_angle unit="rad">0.0160963</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT BOGIE</geom:index_id>
            <geom:index_value_angle unit="rad">0.00499211</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT DIFFERENTIAL</geom:index_id>
            <geom:index_value_angle unit="rad">0.0157508</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT DIFFERENTIAL</geom:index_id>
            <geom:index_value_angle unit="rad">-0.00272702</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT FRONT WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT FRONT WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT MIDDLE WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT MIDDLE WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT REAR WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT REAR WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
        <geom:Vector_Device_Gravity>
          <geom:x_unit>-0.0080201598163349</geom:x_unit>
          <geom:y_unit>-0.20628864997957977</geom:y_unit>
          <geom:z_unit>0.9784583128197761</geom:z_unit>
        </geom:Vector_Device_Gravity>
        <geom:Vector_Device_Gravity_Magnitude>
          <geom:x_acceleration unit="m/s**2">-0.0297852</geom:x_acceleration>
          <geom:y_acceleration unit="m/s**2">-0.766113</geom:y_acceleration>
          <geom:z_acceleration unit="m/s**2">3.63379</geom:z_acceleration>
        </geom:Vector_Device_Gravity_Magnitude>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>HGA</geom:device_id>
        <geom:device_name>HIGH GAIN ANTENNA</geom:device_name>
        <geom:device_mode>DEPLOYED</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH</geom:index_id>
            <geom:index_value_angle unit="rad">1.13443</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION</geom:index_id>
            <geom:index_value_angle unit="rad">-0.784997</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>DRILL</geom:device_id>
        <geom:device_name>DRILL</geom:device_name>
        <geom:device_mode>DRILL</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>SPINDLE OUTPUT POSITION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-0.610797</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>CHUCK POSITION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-0.468847</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>PERCUSS POSITION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>SCS</geom:device_id>
        <geom:device_name>SAMPLE CACHE SYSTEM</geom:device_name>
        <geom:device_mode>SEAL ACTIVATED</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>SCS BIT CAROUSEL-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">80.2859</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SCS BIT CAROUSEL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">74.0026</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>SHA</geom:device_id>
        <geom:device_name>SAMPLE HANDLING ARM</geom:device_name>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 1 Z-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0179931</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 2 SHOULDER-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">-0.239406</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 3 ELBOW-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">2.68496</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 1 Z-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 2 SHOULDER-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-0.23953</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 3 ELBOW-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">2.68459</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Camera_Model_Parameters>
        <geom:model_type>CAHVOR</geom:model_type>
        <geom:calibration_source_id>1</geom:calibration_source_id>
        <geom:CAHVOR_Model>
          <geom:Vector_Center>
            <geom:x_position unit="m">0.763526</geom:x_position>
            <geom:y_position unit="m">0.431354</geom:y_position>
            <geom:z_position unit="m">-1.96582</geom:z_position>
          </geom:Vector_Center>
          <geom:Vector_Axis>
            <geom:x_unit>0.674862</geom:x_unit>
            <geom:y_unit>-0.558159</geom:y_unit>
            <geom:z_unit>0.482737</geom:z_unit>
          </geom:Vector_Axis>
          <geom:Vector_Horizontal>
            <geom:x_pixel>1262.66</geom:x_pixel>
            <geom:y_pixel>1359.61</geom:y_pixel>
            <geom:z_pixel>24.7946</geom:z_pixel>
          </geom:Vector_Horizontal>
          <geom:Vector_Vertical>
            <geom:x_pixel>-615.792</geom:x_pixel>
            <geom:y_pixel>549.758</geom:y_pixel>
            <geom:z_pixel>1660.55</geom:z_pixel>
          </geom:Vector_Vertical>
          <geom:Vector_Optical>
            <geom:x_unit>0.677623</geom:x_unit>
            <geom:y_unit>-0.560592</geom:y_unit>
            <geom:z_unit>0.476003</geom:z_unit>
          </geom:Vector_Optical>
          <geom:Radial_Terms>
            <geom:c0>6.85556e-05</geom:c0>
            <geom:c1>0.520787</geom:c1>
            <geom:c2>-0.014993</geom:c2>
          </geom:Radial_Terms>
        </geom:CAHVOR_Model>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ROVER_NAV_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>25</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>214</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>6</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
        <geom:Quaternion_Model_Transform>
          <geom:qcos>0.90868</geom:qcos>
          <geom:qsin1>-0.0855879</geom:qsin1>
          <geom:qsin2>-0.229092</geom:qsin2>
          <geom:qsin3>-0.338368</geom:qsin3>
        </geom:Quaternion_Model_Transform>
        <geom:Vector_Model_Transform>
          <geom:x>0.805018</geom:x>
          <geom:y>0.559397</geom:y>
          <geom:z>-1.91903</geom:z>
        </geom:Vector_Model_Transform>
        <geom:Interpolation>
          <geom:interpolation_algorithm>Piecewise Bilinear</geom:interpolation_algorithm>
          <geom:interpolation_variable>Zoom</geom:interpolation_variable>
          <geom:interpolation_value>9600.0</geom:interpolation_value>
        </geom:Interpolation>
      </geom:Camera_Model_Parameters>
      <geom:Coordinate_Space_Definition>
        <local_identifier>ROVER_NAV_FRAME_25_214_6_0_0_0_142_106_0_0</local_identifier>
        <local_identifier>ROVER_NAV_FRAME_25_214_6_0_0_0_142_106_0_0_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ROVER_NAV_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>25</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>214</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>6</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>142</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>106</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">-8.04223</geom:x_position>
          <geom:y_position unit="m">-62.9697</geom:y_position>
          <geom:z_position unit="m">0.380571</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.704803</geom:qcos>
          <geom:qsin1>-0.0706213</geom:qsin1>
          <geom:qsin2>0.0760767</geom:qsin2>
          <geom:qsin3>-0.701768</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>SITE_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>25</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
        <geom:Coordinate_Space_Quality>
          <geom:quaternion_measurement_method>Sun_Find</geom:quaternion_measurement_method>
          <geom:attitude_propagation_counter>0.0</geom:attitude_propagation_counter>
        </geom:Coordinate_Space_Quality>
      </geom:Coordinate_Space_Definition>
      <geom:Coordinate_Space_Definition>
        <local_identifier>RSM_HEAD_FRAME_25_214_6_0_0_0_142_106_0_0</local_identifier>
        <local_identifier>RSM_HEAD_FRAME_25_214_6_0_0_0_142_106_0_0_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>RSM_HEAD_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>25</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>214</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>6</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>142</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>106</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">0.805018</geom:x_position>
          <geom:y_position unit="m">0.559397</geom:y_position>
          <geom:z_position unit="m">-1.91903</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.90868</geom:qcos>
          <geom:qsin1>-0.0855879</geom:qsin1>
          <geom:qsin2>-0.229092</geom:qsin2>
          <geom:qsin3>-0.338368</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <Local_Internal_Reference>
            <local_identifier_reference>ROVER_NAV_FRAME_25_214_6_0_0_0_142_106_0_0</local_identifier_reference>
            <local_reference_type>to_reference_coordinate_space</local_reference_type>
          </Local_Internal_Reference>
        </geom:Coordinate_Space_Reference>
        <geom:Coordinate_Space_Quality>
          <geom:quaternion_measurement_method>Unknown</geom:quaternion_measurement_method>
        </geom:Coordinate_Space_Quality>
      </geom:Coordinate_Space_Definition>
      <geom:Coordinate_Space_Definition>
        <local_identifier>ARM_TURRET_FRAME_25_214_6_0_0_0_142_106_0_0</local_identifier>
        <local_identifier>ARM_TURRET_FRAME_25_214_6_0_0_0_142_106_0_0_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ARM_TURRET_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>25</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>214</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>6</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>142</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>106</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">1.08468</geom:x_position>
          <geom:y_position unit="m">-0.429726</geom:y_position>
          <geom:z_position unit="m">-1.40212</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.997173</geom:qcos>
          <geom:qsin1>-0.00230189</geom:qsin1>
          <geom:qsin2>0.00088511</geom:qsin2>
          <geom:qsin3>0.0750983</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ROVER_NAV_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>25</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>214</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>6</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>142</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>106</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
        <geom:Coordinate_Space_Quality>
          <geom:quaternion_measurement_method>Unknown</geom:quaternion_measurement_method>
        </geom:Coordinate_Space_Quality>
      </geom:Coordinate_Space_Definition>
      <geom:Coordinate_Space_Definition>
        <local_identifier>ARM_DOCKING_POST_FRAME_25_214_6_0_0_0_142_106_0_0</local_identifier>
        <local_identifier>ARM_DOCKING_POST_FRAME_25_214_6_0_0_0_142_106_0_0_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ARM_DOCKING_POST_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>25</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>214</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>6</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>142</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>106</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">1.37761</geom:x_position>
          <geom:y_position unit="m">-0.385546</geom:y_position>
          <geom:z_position unit="m">-1.40276</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.997174</geom:qcos>
          <geom:qsin1>-0.00230922</geom:qsin1>
          <geom:qsin2>0.000882401</geom:qsin2>
          <geom:qsin3>0.0750887</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <Local_Internal_Reference>
            <local_identifier_reference>ROVER_NAV_FRAME_25_214_6_0_0_0_142_106_0_0</local_identifier_reference>
            <local_reference_type>to_reference_coordinate_space</local_reference_type>
          </Local_Internal_Reference>
        </geom:Coordinate_Space_Reference>
        <geom:Coordinate_Space_Quality>
          <geom:quaternion_measurement_method>Unknown</geom:quaternion_measurement_method>
        </geom:Coordinate_Space_Quality>
      </geom:Coordinate_Space_Definition>
      <geom:Derived_Geometry>
        <geom:instrument_azimuth unit="deg">-39.6912</geom:instrument_azimuth>
        <geom:instrument_elevation unit="deg">-28.7207</geom:instrument_elevation>
        <geom:Coordinate_Space_Reference>
          <Local_Internal_Reference>
            <local_identifier_reference>ROVER_NAV_FRAME_25_214_6_0_0_0_142_106_0_0</local_identifier_reference>
            <local_reference_type>to_reference_coordinate_space</local_reference_type>
          </Local_Internal_Reference>
        </geom:Coordinate_Space_Reference>
      </geom:Derived_Geometry>
      <geom:Derived_Geometry>
        <geom:instrument_azimuth unit="deg">-123.248</geom:instrument_azimuth>
        <geom:instrument_elevation unit="deg">-35.4692</geom:instrument_elevation>
        <geom:solar_azimuth unit="deg">190.613</geom:solar_azimuth>
        <geom:solar_elevation unit="deg">51.1815</geom:solar_elevation>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>SITE_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>25</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
      </geom:Derived_Geometry>
      <geom:Motion_Counter>
        <geom:name>RMC</geom:name>
        <geom:Motion_Counter_Index>
          <geom:index_id>SITE</geom:index_id>
          <geom:index_value_number>25</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>DRIVE</geom:index_id>
          <geom:index_value_number>214</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>POSE</geom:index_id>
          <geom:index_value_number>6</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>ARM</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>SHA</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>DRILL</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>RSM</geom:index_id>
          <geom:index_value_number>142</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>HGA</geom:index_id>
          <geom:index_value_number>106</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>BITCAR</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>SEAL</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
      </geom:Motion_Counter>
    </geom:Geometry_Lander>
  </geom:Geometry>
  ...
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:mars2020_navcam_ops_calibrated:data:nlf_0314_0694827040_022fdr_n0090000ncam00501_0a0295j::1.0:  
```
<Discipline_Area>
  ...
  <geom:Geometry>
    <geom:SPICE_Kernel_Files>
      <geom:SPICE_Kernel_Identification>
        <geom:spice_kernel_file_name>chronos.m2020_ops210303_v1</geom:spice_kernel_file_name>
      </geom:SPICE_Kernel_Identification>
    </geom:SPICE_Kernel_Files>
    <geom:Geometry_Lander>
      <geom:geometry_state>Telemetry</geom:geometry_state>
      <geom:description>Geometry as reported by the spacecraft in telemetry</geom:description>
      <local_identifier>geom_telemetry_state</local_identifier>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>RSM</geom:device_id>
        <geom:device_name>REMOTE SENSING MAST</geom:device_name>
        <geom:device_mode>DEPLOYED</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH FINAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">1.59776</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION FINAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">2.02499</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH INITIAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">0.0339389</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION INITIAL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">2.02152</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH REQUESTED</geom:index_id>
            <geom:index_value_angle unit="rad">1.60552</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION REQUESTED</geom:index_id>
            <geom:index_value_angle unit="rad">2.02375</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH FINAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">1.60552</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION FINAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">2.02375</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH INITIAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">0.0385377</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION INITIAL-ENCODER</geom:index_id>
            <geom:index_value_angle unit="rad">2.02359</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
        <geom:Device_Temperature>
          <geom:Device_Temperature_Index>
            <geom:index_id>NAVCAM LEFT CAMERA PLATE</geom:index_id>
            <geom:index_value_temperature unit="degC">-15.7796</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>NAVCAM RIGHT CAMERA PLATE</geom:index_id>
            <geom:index_value_temperature unit="degC">-15.686</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
        </geom:Device_Temperature>
        <geom:Commanded_Geometry>
          <geom:command_type>No_Motion</geom:command_type>
          <geom:Device_Angle>
            <geom:Device_Angle_Index>
              <geom:index_name>Unknown</geom:index_name>
              <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
            </geom:Device_Angle_Index>
          </geom:Device_Angle>
        </geom:Commanded_Geometry>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>ARM</geom:device_id>
        <geom:device_name>SAMPLE ARM</geom:device_name>
        <geom:selected_instrument_id>WATSON</geom:selected_instrument_id>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 1 AZIMUTH-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">-1.75795</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 2 ELEVATION-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">-2.12703</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 3 ELBOW-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">-0.958683</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 4 WRIST-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">-0.0425635</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 5 TURRET-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">6.00919</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 1 AZIMUTH-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-1.75789</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 2 ELEVATION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-2.12876</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 3 ELBOW-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-0.959944</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 4 WRIST-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-0.0424461</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>JOINT 5 TURRET-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">6.00943</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SCS DOCKING CLOCK ANGLE</geom:index_id>
            <geom:index_value_angle unit="rad">0.0599876</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
        <geom:Device_Component_State>
          <geom:Device_Component_State_Index>
            <geom:index_id>PRELOAD_VALUE</geom:index_id>
            <geom:index_value_string>0</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>PRELOAD_TOOL</geom:index_id>
            <geom:index_value_string>WATSON</geom:index_value_string>
          </geom:Device_Component_State_Index>
        </geom:Device_Component_State>
        <geom:Device_Component_State>
          <geom:Device_Component_State_Index>
            <geom:index_id>FACILITY CONTACT SENSOR A</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>FACILITY CONTACT SENSOR B</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DRILL STABILIZER 1</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DRILL STABILIZER 2</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 1</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 2</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 3</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
          <geom:Device_Component_State_Index>
            <geom:index_id>DOCK 4</geom:index_id>
            <geom:index_value_string>NO CONTACT</geom:index_value_string>
          </geom:Device_Component_State_Index>
        </geom:Device_Component_State>
        <geom:Device_Pose>
          <geom:name>arm_attitude_reference</geom:name>
          <geom:Quaternion_Plus_Direction>
            <geom:qcos>0.428359</geom:qcos>
            <geom:qsin1>0.0722588</geom:qsin1>
            <geom:qsin2>0.0260822</geom:qsin2>
            <geom:qsin3>-0.900337</geom:qsin3>
            <geom:rotation_direction>Forward</geom:rotation_direction>
          </geom:Quaternion_Plus_Direction>
        </geom:Device_Pose>
        <geom:Device_Temperature>
          <geom:Device_Temperature_Index>
            <geom:index_id>AZIMUTH JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-5.0131</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>ELEVATION JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-7.8988</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>ELBOW JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-5.32508</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>WRIST JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">-1.52938</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>TURRET JOINT</geom:index_id>
            <geom:index_value_temperature unit="degC">0.137267</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>DEFLECTION BODY DELTA TEMPERATURE</geom:index_id>
            <geom:index_value_temperature unit="degC">0.0</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
          <geom:Device_Temperature_Index>
            <geom:index_id>DEFLECTION ARM DELTA TEMPERATURE</geom:index_id>
            <geom:index_value_temperature unit="degC">-33.8681</geom:index_value_temperature>
          </geom:Device_Temperature_Index>
        </geom:Device_Temperature>
        <geom:Vector_Device_Gravity>
          <geom:x_unit>-0.10776996883562377</geom:x_unit>
          <geom:y_unit>-0.10887096851724222</geom:y_unit>
          <geom:z_unit>0.9881967142382565</geom:z_unit>
        </geom:Vector_Device_Gravity>
        <geom:Vector_Device_Gravity_Magnitude>
          <geom:x_acceleration unit="m/s**2">-0.10777</geom:x_acceleration>
          <geom:y_acceleration unit="m/s**2">-0.108871</geom:y_acceleration>
          <geom:z_acceleration unit="m/s**2">0.988197</geom:z_acceleration>
        </geom:Vector_Device_Gravity_Magnitude>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>CHASSIS</geom:device_id>
        <geom:device_name>MOBILITY CHASSIS</geom:device_name>
        <geom:device_mode>DEPLOYED</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT FRONT WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">-4.26106e-05</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT FRONT WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">-4.26106e-05</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT REAR WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">-4.26106e-05</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT REAR WHEEL STEER MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.000127832</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT BOGIE</geom:index_id>
            <geom:index_value_angle unit="rad">-0.108384</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT BOGIE</geom:index_id>
            <geom:index_value_angle unit="rad">0.00230399</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT DIFFERENTIAL</geom:index_id>
            <geom:index_value_angle unit="rad">0.0353432</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT DIFFERENTIAL</geom:index_id>
            <geom:index_value_angle unit="rad">-0.0214265</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT FRONT WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT FRONT WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>MIDDLE LEFT WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>MIDDLE RIGHT WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>LEFT REAR WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>RIGHT REAR WHEEL DRIVE MOTOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
        <geom:Vector_Device_Gravity>
          <geom:x_unit>-0.14998134610569644</geom:x_unit>
          <geom:y_unit>0.017335846465737347</geom:y_unit>
          <geom:z_unit>0.9885368299904864</geom:z_unit>
        </geom:Vector_Device_Gravity>
        <geom:Vector_Device_Gravity_Magnitude>
          <geom:x_acceleration unit="m/s**2">-0.557617</geom:x_acceleration>
          <geom:y_acceleration unit="m/s**2">0.0644531</geom:y_acceleration>
          <geom:z_acceleration unit="m/s**2">3.67529</geom:z_acceleration>
        </geom:Vector_Device_Gravity_Magnitude>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>HGA</geom:device_id>
        <geom:device_name>HIGH GAIN ANTENNA</geom:device_name>
        <geom:device_mode>DEPLOYED</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>AZIMUTH</geom:index_id>
            <geom:index_value_angle unit="rad">1.13444</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>ELEVATION</geom:index_id>
            <geom:index_value_angle unit="rad">-0.784997</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>DRILL</geom:device_id>
        <geom:device_name>DRILL</geom:device_name>
        <geom:device_mode>DRILL</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>SPINDLE OUTPUT POSITION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">5.57861</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>CHUCK POSITION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">-0.468715</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>PERCUSS POSITION-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>SCS</geom:device_id>
        <geom:device_name>SAMPLE CACHE SYSTEM</geom:device_name>
        <geom:device_mode>FILLED</geom:device_mode>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>SCS BIT CAROUSEL-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">44.4266</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SCS BIT CAROUSEL-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">38.1444</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Articulation_Device_Parameters>
        <geom:device_id>SHA</geom:device_id>
        <geom:device_name>SAMPLE HANDLING ARM</geom:device_name>
        <geom:Device_Angle>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 1 Z-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">0.0244656</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 2 SHOULDER-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">1.18848</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 3 ELBOW-HALL SENSOR</geom:index_id>
            <geom:index_value_angle unit="rad">1.07695</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 1 Z-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">0.0</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 2 SHOULDER-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">1.18837</geom:index_value_angle>
          </geom:Device_Angle_Index>
          <geom:Device_Angle_Index>
            <geom:index_id>SHA JOINT 3 ELBOW-RESOLVER</geom:index_id>
            <geom:index_value_angle unit="rad">1.07677</geom:index_value_angle>
          </geom:Device_Angle_Index>
        </geom:Device_Angle>
      </geom:Articulation_Device_Parameters>
      <geom:Camera_Model_Parameters>
        <geom:model_type>CAHVORE</geom:model_type>
        <geom:calibration_source_id>1</geom:calibration_source_id>
        <geom:CAHVORE_Model>
          <geom:Vector_Center>
            <geom:x_position unit="m">0.591534</geom:x_position>
            <geom:y_position unit="m">0.465558</geom:y_position>
            <geom:z_position unit="m">-2.02622</geom:z_position>
          </geom:Vector_Center>
          <geom:Vector_Axis>
            <geom:x_unit>0.00920777</geom:x_unit>
            <geom:y_unit>-0.908304</geom:y_unit>
            <geom:z_unit>-0.418229</geom:z_unit>
          </geom:Vector_Axis>
          <geom:Vector_Horizontal>
            <geom:x_pixel>745.556</geom:x_pixel>
            <geom:y_pixel>-581.84</geom:y_pixel>
            <geom:z_pixel>-270.125</geom:z_pixel>
          </geom:Vector_Horizontal>
          <geom:Vector_Vertical>
            <geom:x_pixel>6.3519</geom:x_pixel>
            <geom:y_pixel>-750.04</geom:y_pixel>
            <geom:z_pixel>468.718</geom:z_pixel>
          </geom:Vector_Vertical>
          <geom:Vector_Optical>
            <geom:x_unit>0.0106242</geom:x_unit>
            <geom:y_unit>-0.908333</geom:y_unit>
            <geom:z_unit>-0.418133</geom:z_unit>
          </geom:Vector_Optical>
          <geom:Radial_Terms>
            <geom:c0>1.736e-06</geom:c0>
            <geom:c1>0.0501396</geom:c1>
            <geom:c2>-0.0171254</geom:c2>
          </geom:Radial_Terms>
          <geom:Entrance_Terms>
            <geom:c0>-8.0e-09</geom:c0>
            <geom:c1>1.0e-08</geom:c1>
            <geom:c2>-2.9e-08</geom:c2>
          </geom:Entrance_Terms>
          <geom:cahvore_model_type>2</geom:cahvore_model_type>
          <geom:cahvore_model_parameter>0.0</geom:cahvore_model_parameter>
        </geom:CAHVORE_Model>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ROVER_NAV_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>9</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>506</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
        <geom:Quaternion_Model_Transform>
          <geom:qcos>0.69286</geom:qcos>
          <geom:qsin1>0.153904</geom:qsin1>
          <geom:qsin2>0.153838</geom:qsin2>
          <geom:qsin3>-0.687454</geom:qsin3>
        </geom:Quaternion_Model_Transform>
        <geom:Vector_Model_Transform>
          <geom:x>0.804966</geom:x>
          <geom:y>0.559373</geom:y>
          <geom:z>-1.91903</geom:z>
        </geom:Vector_Model_Transform>
        <geom:Interpolation>
          <geom:interpolation_algorithm>Piecewise Bilinear</geom:interpolation_algorithm>
          <geom:interpolation_variable>Temperature</geom:interpolation_variable>
          <geom:interpolation_value>-15.7796</geom:interpolation_value>
        </geom:Interpolation>
      </geom:Camera_Model_Parameters>
      <geom:Coordinate_Space_Definition>
        <local_identifier>ROVER_NAV_FRAME_9_0_506_1912_1294_952_4162_1442_82_42</local_identifier>
        <local_identifier>ROVER_NAV_FRAME_9_0_506_1912_1294_952_4162_1442_82_42_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ROVER_NAV_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>9</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>506</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>1912</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>1294</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>952</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>4162</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>1442</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>82</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>42</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">0.0</geom:x_position>
          <geom:y_position unit="m">0.0</geom:y_position>
          <geom:z_position unit="m">0.0</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.428436</geom:qcos>
          <geom:qsin1>0.0718908</geom:qsin1>
          <geom:qsin2>0.0254764</geom:qsin2>
          <geom:qsin3>-0.900348</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <Local_Internal_Reference>
            <local_identifier_reference>SITE_FRAME_9</local_identifier_reference>
            <local_reference_type>to_reference_coordinate_space</local_reference_type>
          </Local_Internal_Reference>
        </geom:Coordinate_Space_Reference>
        <geom:Coordinate_Space_Quality>
          <geom:quaternion_measurement_method>Sun_Find</geom:quaternion_measurement_method>
          <geom:attitude_propagation_counter>0.0</geom:attitude_propagation_counter>
        </geom:Coordinate_Space_Quality>
      </geom:Coordinate_Space_Definition>
      <geom:Coordinate_Space_Definition>
        <local_identifier>SITE_FRAME_9</local_identifier>
        <local_identifier>SITE_FRAME_9_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>SITE_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>9</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">-78.5516</geom:x_position>
          <geom:y_position unit="m">-93.1537</geom:y_position>
          <geom:z_position unit="m">5.25963</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>1.0</geom:qcos>
          <geom:qsin1>0.0</geom:qsin1>
          <geom:qsin2>0.0</geom:qsin2>
          <geom:qsin3>0.0</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>SITE_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>8</geom:index_value_number>
            </geom:Coordinate_Space_Index>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Reference>
        <geom:Coordinate_Space_Quality>
          <geom:quaternion_measurement_method>Unknown</geom:quaternion_measurement_method>
        </geom:Coordinate_Space_Quality>
      </geom:Coordinate_Space_Definition>
      <geom:Coordinate_Space_Definition>
        <local_identifier>RSM_HEAD_FRAME_9_0_506_1912_1294_952_4162_1442_82_42</local_identifier>
        <local_identifier>RSM_HEAD_FRAME_9_0_506_1912_1294_952_4162_1442_82_42_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>RSM_HEAD_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>9</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>506</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>1912</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>1294</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>952</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>4162</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>1442</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>82</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>42</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">0.804966</geom:x_position>
          <geom:y_position unit="m">0.559373</geom:y_position>
          <geom:z_position unit="m">-1.91903</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.69286</geom:qcos>
          <geom:qsin1>0.153904</geom:qsin1>
          <geom:qsin2>0.153838</geom:qsin2>
          <geom:qsin3>-0.687454</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <Local_Internal_Reference>
            <local_identifier_reference>ROVER_NAV_FRAME_9_0_506_1912_1294_952_4162_1442_82_42</local_identifier_reference>
            <local_reference_type>to_reference_coordinate_space</local_reference_type>
          </Local_Internal_Reference>
        </geom:Coordinate_Space_Reference>
        <geom:Coordinate_Space_Quality>
          <geom:quaternion_measurement_method>Unknown</geom:quaternion_measurement_method>
        </geom:Coordinate_Space_Quality>
      </geom:Coordinate_Space_Definition>
      <geom:Coordinate_Space_Definition>
        <local_identifier>ARM_TURRET_FRAME_9_0_506_1912_1294_952_4162_1442_82_42</local_identifier>
        <local_identifier>ARM_TURRET_FRAME_9_0_506_1912_1294_952_4162_1442_82_42_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ARM_TURRET_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>9</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>506</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>1912</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>1294</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>952</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>4162</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>1442</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>82</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>42</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">1.59706</geom:x_position>
          <geom:y_position unit="m">0.348628</geom:y_position>
          <geom:z_position unit="m">-1.21858</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.00106859</geom:qcos>
          <geom:qsin1>0.675265</geom:qsin1>
          <geom:qsin2>0.737575</geom:qsin2>
          <geom:qsin3>-0.000476947</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <Local_Internal_Reference>
            <local_identifier_reference>ROVER_NAV_FRAME_9_0_506_1912_1294_952_4162_1442_82_42</local_identifier_reference>
            <local_reference_type>to_reference_coordinate_space</local_reference_type>
          </Local_Internal_Reference>
        </geom:Coordinate_Space_Reference>
        <geom:Coordinate_Space_Quality>
          <geom:quaternion_measurement_method>Unknown</geom:quaternion_measurement_method>
        </geom:Coordinate_Space_Quality>
      </geom:Coordinate_Space_Definition>
      <geom:Coordinate_Space_Definition>
        <local_identifier>ARM_WATSON_FRAME_9_0_506_1912_1294_952_4162_1442_82_42</local_identifier>
        <local_identifier>ARM_WATSON_FRAME_9_0_506_1912_1294_952_4162_1442_82_42_TELEMETRY</local_identifier>
        <geom:positive_azimuth_direction>Clockwise</geom:positive_azimuth_direction>
        <geom:positive_elevation_direction>Up</geom:positive_elevation_direction>
        <geom:Coordinate_Space_Present>
          <geom:Coordinate_Space_Indexed>
            <geom:coordinate_space_frame_type>ARM_WATSON_FRAME</geom:coordinate_space_frame_type>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SITE</geom:index_id>
              <geom:index_value_number>9</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRIVE</geom:index_id>
              <geom:index_value_number>0</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>POSE</geom:index_id>
              <geom:index_value_number>506</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>ARM</geom:index_id>
              <geom:index_value_number>1912</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SHA</geom:index_id>
              <geom:index_value_number>1294</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>DRILL</geom:index_id>
              <geom:index_value_number>952</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>RSM</geom:index_id>
              <geom:index_value_number>4162</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>HGA</geom:index_id>
              <geom:index_value_number>1442</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>BITCAR</geom:index_id>
              <geom:index_value_number>82</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:Coordinate_Space_Index>
              <geom:index_id>SEAL</geom:index_id>
              <geom:index_value_number>42</geom:index_value_number>
            </geom:Coordinate_Space_Index>
            <geom:solution_id>TELEMETRY</geom:solution_id>
          </geom:Coordinate_Space_Indexed>
        </geom:Coordinate_Space_Present>
        <geom:Vector_Origin_Offset>
          <geom:x_position unit="m">1.291</geom:x_position>
          <geom:y_position unit="m">0.205621</geom:y_position>
          <geom:z_position unit="m">-1.20427</geom:z_position>
        </geom:Vector_Origin_Offset>
        <geom:Quaternion_Plus_Direction>
          <geom:qcos>0.000222225</geom:qcos>
          <geom:qsin1>-0.21687</geom:qsin1>
          <geom:qsin2>0.9762</geom:qsin2>
          <geom:qsin3>-0.0011489</geom:qsin3>
          <geom:rotation_direction>Forward</geom:rotation_direction>
        </geom:Quaternion_Plus_Direction>
        <geom:Coordinate_Space_Reference>
          <Local_Internal_Reference>
            <local_identifier_reference>ROVER_NAV_FRAME_9_0_506_1912_1294_952_4162_1442_82_42</local_identifier_reference>
            <local_reference_type>to_reference_coordinate_space</local_reference_type>
          </Local_Internal_Reference>
        </geom:Coordinate_Space_Reference>
        <geom:Coordinate_Space_Quality>
          <geom:quaternion_measurement_method>Unknown</geom:quaternion_measurement_method>
        </geom:Coordinate_Space_Quality>
      </geom:Coordinate_Space_Definition>
      <geom:Derived_Geometry>
        <geom:instrument_azimuth unit="deg">269.827</geom:instrument_azimuth>
        <geom:instrument_elevation unit="deg">25.17</geom:instrument_elevation>
        <geom:solar_azimuth unit="deg">38.0508</geom:solar_azimuth>
        <geom:solar_elevation unit="deg">23.2881</geom:solar_elevation>
        <geom:Vector_Solar_Direction>
          <geom:x_unit>0.723309</geom:x_unit>
          <geom:y_unit>0.566144</geom:y_unit>
          <geom:z_unit>-0.395354</geom:z_unit>
        </geom:Vector_Solar_Direction>
        <geom:Coordinate_Space_Reference>
          <Local_Internal_Reference>
            <local_identifier_reference>ROVER_NAV_FRAME_9_0_506_1912_1294_952_4162_1442_82_42</local_identifier_reference>
            <local_reference_type>to_reference_coordinate_space</local_reference_type>
          </Local_Internal_Reference>
        </geom:Coordinate_Space_Reference>
      </geom:Derived_Geometry>
      <geom:Derived_Geometry>
        <geom:instrument_azimuth unit="deg">136.558</geom:instrument_azimuth>
        <geom:instrument_elevation unit="deg">25.7329</geom:instrument_elevation>
        <geom:solar_azimuth unit="deg">272.057</geom:solar_azimuth>
        <geom:solar_elevation unit="deg">29.4129</geom:solar_elevation>
        <geom:Coordinate_Space_Reference>
          <Local_Internal_Reference>
            <local_identifier_reference>SITE_FRAME_9</local_identifier_reference>
            <local_reference_type>to_reference_coordinate_space</local_reference_type>
          </Local_Internal_Reference>
        </geom:Coordinate_Space_Reference>
      </geom:Derived_Geometry>
      <geom:Motion_Counter>
        <geom:name>RMC</geom:name>
        <geom:Motion_Counter_Index>
          <geom:index_id>SITE</geom:index_id>
          <geom:index_value_number>9</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>DRIVE</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>POSE</geom:index_id>
          <geom:index_value_number>506</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>ARM</geom:index_id>
          <geom:index_value_number>1912</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>SHA</geom:index_id>
          <geom:index_value_number>1294</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>DRILL</geom:index_id>
          <geom:index_value_number>952</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>RSM</geom:index_id>
          <geom:index_value_number>4162</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>HGA</geom:index_id>
          <geom:index_value_number>1442</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>BITCAR</geom:index_id>
          <geom:index_value_number>82</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>SEAL</geom:index_id>
          <geom:index_value_number>42</geom:index_value_number>
        </geom:Motion_Counter_Index>
      </geom:Motion_Counter>
    </geom:Geometry_Lander>
    <geom:Geometry_Lander>
      <geom:geometry_state>Initial</geom:geometry_state>
      <geom:description>Initial state of geometry before onboard updates (e.g. visual odometry)</geom:description>
      <local_identifier>geom_initial_state</local_identifier>
      <geom:Motion_Counter>
        <geom:name>RMC</geom:name>
        <geom:Motion_Counter_Index>
          <geom:index_id>SITE</geom:index_id>
          <geom:index_value_number>9</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>DRIVE</geom:index_id>
          <geom:index_value_number>0</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>POSE</geom:index_id>
          <geom:index_value_number>506</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>ARM</geom:index_id>
          <geom:index_value_number>1912</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>SHA</geom:index_id>
          <geom:index_value_number>1294</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>DRILL</geom:index_id>
          <geom:index_value_number>952</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>RSM</geom:index_id>
          <geom:index_value_number>4162</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>HGA</geom:index_id>
          <geom:index_value_number>1442</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>BITCAR</geom:index_id>
          <geom:index_value_number>82</geom:index_value_number>
        </geom:Motion_Counter_Index>
        <geom:Motion_Counter_Index>
          <geom:index_id>SEAL</geom:index_id>
          <geom:index_value_number>42</geom:index_value_number>
        </geom:Motion_Counter_Index>
      </geom:Motion_Counter>
    </geom:Geometry_Lander>
  </geom:Geometry>
  ...
</Discipline_Area>
```  
  
Example PDS4 label snippet from urn:nasa:pds:messenger_mdis_1001:nac_edr:en0066113370m::1.0:  
```
<Discipline_Area>
  ...
  <geom:Geometry>
    <geom:Image_Display_Geometry>
      <geom:Display_Direction>
        <geom:horizontal_display_axis>Sample</geom:horizontal_display_axis>
        <geom:horizontal_display_direction>Left to Right</geom:horizontal_display_direction>
        <geom:vertical_display_axis>Line</geom:vertical_display_axis>
        <geom:vertical_display_direction>Top to Bottom</geom:vertical_display_direction>
      </geom:Display_Direction>
      <geom:Object_Orientation_RA_Dec>
        <geom:Reference_Pixel>
          <!-- RA_DEC_REF_PIXEL (center) -->
          <geom:vertical_coordinate_pixel unit="pixel">256</geom:vertical_coordinate_pixel>
          <geom:horizontal_coordinate_pixel unit="pixel">256</geom:horizontal_coordinate_pixel>
        </geom:Reference_Pixel>
        <geom:reference_pixel_location>Center</geom:reference_pixel_location>
        <geom:right_ascension_angle unit="deg">193.57142</geom:right_ascension_angle>
        <!-- RIGHT_ASCENSION -->
        <geom:declination_angle unit="deg">3.65744</geom:declination_angle>
        <!-- DECLINATION -->
        <geom:celestial_north_clock_angle unit="deg">20.538</geom:celestial_north_clock_angle>
        <!-- (180 - TWIST_ANGLE) -->
        <geom:Reference_Frame_Identification>
          <geom:name>J2000</geom:name>
        </geom:Reference_Frame_Identification>
      </geom:Object_Orientation_RA_Dec>
      <geom:Object_Orientation_RA_Dec>
        <!-- reticle point right ascension and declination -->
        <geom:Reference_Pixel>
          <!-- upper left reticle -->
          <geom:vertical_coordinate_pixel unit="pixel">1</geom:vertical_coordinate_pixel>
          <geom:horizontal_coordinate_pixel unit="pixel">1</geom:horizontal_coordinate_pixel>
        </geom:Reference_Pixel>
        <geom:reference_pixel_location>Center</geom:reference_pixel_location>
        <geom:right_ascension_angle unit="deg">194.52990</geom:right_ascension_angle>
        <!-- RETICLE_POINT_RA [1] -->
        <geom:declination_angle unit="deg">4.10103</geom:declination_angle>
        <!-- RETICLE_POINT_DECLINATION [1]-->
        <geom:celestial_north_clock_angle unit="deg">20.538</geom:celestial_north_clock_angle>
        <!-- (180 - TWIST_ANGLE) -->
        <geom:Reference_Frame_Identification>
          <geom:name>J2000</geom:name>
        </geom:Reference_Frame_Identification>
      </geom:Object_Orientation_RA_Dec>
      <geom:Object_Orientation_RA_Dec>
        <!-- reticle point right ascension and declination -->
        <geom:Reference_Pixel>
          <!-- upper right reticle -->
          <geom:vertical_coordinate_pixel unit="pixel">1</geom:vertical_coordinate_pixel>
          <geom:horizontal_coordinate_pixel unit="pixel">512</geom:horizontal_coordinate_pixel>
        </geom:Reference_Pixel>
        <geom:reference_pixel_location>Center</geom:reference_pixel_location>
        <geom:right_ascension_angle unit="deg">193.13710</geom:right_ascension_angle>
        <!-- RETICLE_POINT_RA [1] -->
        <geom:declination_angle unit="deg">4.62073</geom:declination_angle>
        <!-- RETICLE_POINT_DECLINATION [1]-->
        <geom:celestial_north_clock_angle unit="deg">20.538</geom:celestial_north_clock_angle>
        <!-- (180 - TWIST_ANGLE) -->
        <geom:Reference_Frame_Identification>
          <geom:name>J2000</geom:name>
        </geom:Reference_Frame_Identification>
      </geom:Object_Orientation_RA_Dec>
      <geom:Object_Orientation_RA_Dec>
        <!-- reticle point right ascension and declination -->
        <geom:Reference_Pixel>
          <!-- lower left reticle -->
          <geom:vertical_coordinate_pixel unit="pixel">512</geom:vertical_coordinate_pixel>
          <geom:horizontal_coordinate_pixel unit="pixel">1</geom:horizontal_coordinate_pixel>
        </geom:Reference_Pixel>
        <geom:reference_pixel_location>Center</geom:reference_pixel_location>
        <geom:right_ascension_angle unit="deg">194.01102</geom:right_ascension_angle>
        <!-- RETICLE_POINT_RA [1] -->
        <geom:declination_angle unit="deg">2.70233</geom:declination_angle>
        <!-- RETICLE_POINT_DECLINATION [1]-->
        <geom:celestial_north_clock_angle unit="deg">20.538</geom:celestial_north_clock_angle>
        <!-- (180 - TWIST_ANGLE) -->
        <geom:Reference_Frame_Identification>
          <geom:name>J2000</geom:name>
        </geom:Reference_Frame_Identification>
      </geom:Object_Orientation_RA_Dec>
      <geom:Object_Orientation_RA_Dec>
        <!-- reticle point right ascension and declination -->
        <geom:Reference_Pixel>
          <!-- lower right reticle -->
          <geom:vertical_coordinate_pixel unit="pixel">512</geom:vertical_coordinate_pixel>
          <geom:horizontal_coordinate_pixel unit="pixel">512</geom:horizontal_coordinate_pixel>
        </geom:Reference_Pixel>
        <geom:reference_pixel_location>Center</geom:reference_pixel_location>
        <geom:right_ascension_angle unit="deg">192.60923</geom:right_ascension_angle>
        <!-- RETICLE_POINT_RA [1] -->
        <geom:declination_angle unit="deg">3.22527</geom:declination_angle>
        <!-- RETICLE_POINT_DECLINATION [1]-->
        <geom:celestial_north_clock_angle unit="deg">20.538</geom:celestial_north_clock_angle>
        <!-- (180 - TWIST_ANGLE) -->
        <geom:Reference_Frame_Identification>
          <geom:name>J2000</geom:name>
        </geom:Reference_Frame_Identification>
      </geom:Object_Orientation_RA_Dec>
    </geom:Image_Display_Geometry>
    <geom:Geometry_Orbiter>
      <geom:geometry_start_time_utc>2006-09-07T10:49:30.8481Z</geom:geometry_start_time_utc>
      <!-- START_TIME -->
      <geom:geometry_stop_time_utc>2006-09-07T10:49:30.9080Z</geom:geometry_stop_time_utc>
      <!-- STOP_TIME -->
      <geom:Distances>
        <geom:Distances_Specific>
          <geom:spacecraft_central_body_distance unit="km">45488131.57301</geom:spacecraft_central_body_distance>
          <!-- TARGET_CENTER_DISTANCE  -->
          <geom:spacecraft_heliocentric_distance unit="km">91848927.57160</geom:spacecraft_heliocentric_distance>
          <!-- SPACECRAFT_SOLAR_DISTANCE  -->
          <geom:target_heliocentric_distance unit="km">107477348.47574</geom:target_heliocentric_distance>
          <!-- SOLAR_DISTANCE -->
        </geom:Distances_Specific>
      </geom:Distances>
      <geom:Surface_Geometry>
        <geom:Surface_Geometry_Specific>
          <geom:subsolar_latitude unit="deg">-2.54713</geom:subsolar_latitude>
          <!-- SUB_SOLAR_LATITUDE -->
          <geom:subsolar_longitude unit="deg">165.93962</geom:subsolar_longitude>
          <!-- SUB_SOLAR_LONGITUDE -->
          <geom:subspacecraft_latitude unit="deg">-7.46977</geom:subspacecraft_latitude>
          <!-- SUB_SPACECRAFT_LATITUDE -->
          <geom:subspacecraft_longitude unit="deg">223.97177</geom:subspacecraft_longitude>
          <!-- SUB_SPACECRAFT_LONGITUDE -->
        </geom:Surface_Geometry_Specific>
      </geom:Surface_Geometry>
      <geom:Vectors>
        <geom:Vectors_Cartesian_Specific>
          <geom:Vector_Cartesian_Position_Spacecraft_To_Target>
            <!-- SC_TARGET_POSITION_VECTOR -->
            <geom:x_position unit="km">44189983.32423</geom:x_position>
            <geom:y_position unit="km">10379531.03758</geom:y_position>
            <geom:z_position unit="km">-2946323.68343</geom:z_position>
            <geom:light_time_correction_applied>Received_Light_Time_Stellar_Abb</geom:light_time_correction_applied>
          </geom:Vector_Cartesian_Position_Spacecraft_To_Target>
          <!-- SC_SUN_POSITION_VECTOR -->
          <geom:Vector_Cartesian_Position_Sun_To_Spacecraft>
            <geom:x_position unit="km">-28569152.01038</geom:x_position>
            <geom:y_position unit="km">80694440.20494</geom:y_position>
            <geom:z_position unit="km">33293188.03406</geom:z_position>
            <geom:light_time_correction_applied>Received_Light_Time_Stellar_Abb</geom:light_time_correction_applied>
          </geom:Vector_Cartesian_Position_Sun_To_Spacecraft>
          <geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_Sun>
            <!-- SC_SUN_VELOCITY_VECTOR -->
            <geom:x_velocity unit="km/s">39.19590</geom:x_velocity>
            <geom:y_velocity unit="km/s">16.09593</geom:y_velocity>
            <geom:z_velocity unit="km/s">4.97735</geom:z_velocity>
            <geom:light_time_correction_applied>Received_Light_Time_Stellar_Abb</geom:light_time_correction_applied>
          </geom:Vector_Cartesian_Velocity_Spacecraft_Relative_To_Sun>
        </geom:Vectors_Cartesian_Specific>
      </geom:Vectors>
    </geom:Geometry_Orbiter>
  </geom:Geometry>
  ...
</Discipline_Area>
```  
  
# Edit History  
*See also: [GEOM change log](https://github.com/pds-data-dictionaries/ldd-geom/blob/main/CHANGELOG.md).*  
2026-02-09  Madison N. Hughes