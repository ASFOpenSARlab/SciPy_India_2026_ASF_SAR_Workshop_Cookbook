# An Introduction to NISAR Level-2 GCOV data
<br/>

:::{note} All possible covariance channels: linear (H/V) + circular/linear (RH/RV) polarizations
:::{math}
\begin{aligned}
&\left[
\begin{array}{cccc|cc}
\color{green}\langle HH\,HH^* \rangle
  & \langle HH\,HV^* \rangle
  & \langle HH\,VH^* \rangle
  & \langle HH\,VV^* \rangle
  &
  &
\\[6pt]
{\color{lightgray}\langle HV\,HH^* \rangle}
  & \color{green}\langle HV\,HV^* \rangle
  & \langle HV\,VH^* \rangle
  & \langle HV\,VV^* \rangle
  &
  &
\\[6pt]
{\color{lightgray}\langle VH\,HH^* \rangle}
  & {\color{lightgray}\langle VH\,HV^* \rangle}
  & \color{green}\langle VH\,VH^* \rangle
  & \langle VH\,VV^* \rangle
  &
  &
\\[6pt]
{\color{lightgray}\langle VV\,HH^* \rangle}
  & {\color{lightgray}\langle VV\,HV^* \rangle}
  & {\color{lightgray}\langle VV\,VH^* \rangle}
  & \color{green}\langle VV\,VV^* \rangle
  &
  &
\\ \hline
&
&
&
&
\color{green}\langle RH\,RH^* \rangle
  & \langle RH\,RV^* \rangle
\\[6pt]
&
&
&
&
{\color{lightgray}\langle RV\,RH^* \rangle}
  & \color{green}\langle RV\,RV^* \rangle
\end{array}
\right]
&
\end{aligned}
\\[12pt]
\textcolor{black}{\text{Black}}:\ \text{Included off-diagonal covariance terms}\\
\textcolor{green}{\text{Green}}:\ \text{Included diagonal terms (backscatter)}\\
\textcolor{lightgray}{\text{Light gray}}:\ \text{Conjugate off-diagonal terms (not included)}
:::


## What is NISAR GCOV data?

GCOV is one of NISAR’s data science products. GCOV takes radar signals collected from NISAR and process them into images that are: 

- <b>{abbr}`Geocoded (Data is placed onto a map using latitude/longitude, or another coordinate system, so each pixel matches a real location on Earth)`</b>, meaning they are assigned to their corresponding place on the Earth.

- **{abbr}`Terrain corrected (Meaning mountains, hills, and other slopes will not distort the radar data)`**, meaning mountains, hills, and other slopes will not distort the radar data.

GCOV data includes several different of radar layers. **{abbr}`The diagonal covariance layers(Radar data layers that store the strength, or power, of the returned radar signal for each polarization)`** provide real-valued **{abbr}`backscatter(The portion of the radar signal returned to the satellite after interacting with the ground)`**. Backscatter is the portion of a radar signal that is reflected back toward the satellite after interacting with the Earth’s surface. The strength of the backscatter depends on surface roughness, moisture, and the type of material being observed. Backscatter information is commonly used to describe surface roughness for the application of interest.

GCOV data also contains layers called **{abbr}`off-diagonal covariance channels (Values that describe how different radar polarizations relate to each other)`**, which describe how different radar channels interact with each other, rather than how strong the received signals are. These layers can provide useful information about surface structure and orientation.

GCOV can contain radar data acquired in different polarization modes, including **{abbr}`horizontal(Radar waves that travel horizontally, or side-to-side, in a straight line)`** / **{abbr}`vertical(Radar waves that travel vertically, or up and down, in a straight line)`** (H/V, available in L-band) and, in some cases, **{abbr}`circular(Radar waves that have combined horizontally, H, and vertically, V, polarizations, allowing the signal to travel in a circular motion, R)`** (RH/RV, available in S-band only). Different modes can be utilized to help capture different aspects of how the Earth reflects radar signals. This cookbook provides examples for L-band data only.

<hr/>

## Which data layers are included with a GCOV product?


A GCOV file contains:

- Radar images that have already been corrected for hills, slopes, and terrain 

- Location information that tells you exactly where each pixel is on the map 

- Basic details about the data, such as when it was collected and which radar settings were used at the time of collection 

- Different frequency sections, depending on how the satellite was operating when the data was collected

- Various polarization modes, commonly  **{abbr}`horizontal(Radar waves that travel horizontally, or side-to-side, in a straight line)`** / **{abbr}`vertical(Radar waves that travel vertically, or up and down, in a straight line)`** (H/V) and, depending on location and operation settings, circular polarization (RH/RV, S-band only)

All of this is stored in an **{abbr}`HDF5 file(A systematically organized file structure used by NISAR)`**, which is similar to a folder that contains organized, labeled pieces of data.

<hr/>

## What are the applications for GCOV data?

GCOV is useful because it removes many of the complexities that create challenges in a radar analysis. Given that GCOV data  is already corrected for terrain and mapped to a coordinate system, one can immediately analyze patterns on the ground without needing to correct viewing angles, slopes, or satellite geometry. It gives you consistent, ready-to-use data across space and time.

In addition to its terrain-corrected imagery, GCOV includes extra radar layers that help scientists tell different types of surfaces apart. These additional layers, called **{abbr}`off-diagonal covariance channels (Values that describe how different radar polarizations relate to each other)`**, can help identify whether something is rough or smooth, wet or dry, or whether the signal is coming from the surface, vegetation, or inside snow. GCOV may also include measurements collected with different polarization modes, which allow the imagery to highlight various ground features that interact with the ground in unique ways.

 Some of its many uses include: 
- Tracking snow, ice, and freeze–thaw patterns

- Monitoring forests, vegetation, and land cover change

- Studying wetlands and surface water

- Mapping agricultural fields and soil moisture

- Detecting flooding, landslides, or burn severity

- General Earth surface monitoring where backscatter is needed

GCOV provides reliable, consistent, analysis-ready imagery for science, mapping, and environmental monitoring.

<hr/>
