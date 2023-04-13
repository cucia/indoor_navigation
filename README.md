                                          INDOOR NAVIGATION SYSTEM USING AUGMENTED REALITY


 
1.Introduction

1.1 Purpose
In recent years, with the development of underground shopping malls and large-scale commercial
facilities, the need for indoor navigation systems has increased. Although the Global Positioning
System (GPS) is generally effective for outdoor navigation systems, it is not suitable for indoor
navigation because of poor reception of radio waves from the satellite. Therefore, it is necessary to
use a positioning method other than GPS for indoor navigation. Existing methods for indoor
positioning and navigation include using the radio wave strength of wireless local area networks
(LAN) and bluetooth, magnetic repositioning, position based on visual markers, radio frequency
identification (RFID) tags and dead reckoning. However, these methods have installation cost and
accuracy problems.
 We propose to solve these problems by developing indoor navigation based on position
measurement using ARCore SLAM: Simultaneous localisation and mapping. Indoor navigation is
quite different in terms of complexity compared to outdoor navigation. With outdoor navigation,
millions of people currently use the technology as it doesn’t require much performance; modern
smartphones and even smart watches have built-in GPS and maps. In addition, there have been
concerns about excessive power consumption as the user’s camera operates continuously to locate
AR markers. The purpose of this project is to implement an Augmented Reality based navigation
system using ARcore SLAM to guide a user inside large buildings in real time and to calculate the
best shortest path.
1.2 Scope
Due to the advance of the internet of things and business opportunities, indoor navigation systems
have been deployed in many large buildings, such as big train stations, shopping malls, hospitals,
airports, and government buildings. After installing a navigation mobile app, users can select a point
of interest on a destination list. Then, the app will determine a route to the destination, which is
usually the shortest path. Nowadays, the most commonly used user interface (UI) of navigation
applications is a 2D map with a route. Users are provided with navigation instructions, such as turn
left, turn right, and go straight, when they are close to an intersection. However, due to the
limitations of a 2D navigation map, it could add an additional cognitive load for users to construct
the relationship between the 2D navigation map and the real environment. Extra mental pressure
may also be induced and make users confused. Therefore, eliminating possible user confusion is
important for navigator UI design. Augmented Reality based indoor navigation app with indoor
positioning and navigation system allows to detect and track the position of the user inside the
building real time. Then calculate the best shortest path between the user and destination and drive
the user till the destination. Also compare the results with current indoor navigation models.
1.3 Major Contribution
 Unity is the development environment chosen for this project and the technology used is SLAM:
Simultaneous localisation and mapping, because of its ease of use and NavMesh advantages (to be
discussed later). The project consists out of four big parts, namely the ARCore based localisation, the
QR-code repositioning, the navigation (NavMesh), and lastly the AR view.
 Augmented Reality
 Augmented reality (AR) is an interactive experience of a real-world environment where the objects
that reside in the real world are enhanced by computer-generated perceptual information,
sometimes across multiple sensory modalities, including visual, auditory, haptic, somatosensory and
olfactory. AR can be defined as a system that incorporates three basic features: a combination of
real and virtual worlds, real-time interaction, and accurate 3D registration of virtual and real objects.
The overlaid sensory information can be constructive (i.e. additive to the natural environment), or
destructive (i.e. masking of the natural environment). This experience is seamlessly interwoven with
the physical world such that it is perceived as an immersive aspect of the real environment. In this
way, augmented reality alters one’s ongoing perception of a real-world environment, whereas
virtual reality completely replaces the user’s real-world environment with a simulated one.
Augmented reality is related to two largely synonymous terms: mixed reality and computermediated reality.
ARCore
 ARCore is Google’s platform for building augmented reality experiences. Using different APIs,
ARCore enables your phone to sense its environment, understand the world and interact with
information. Some of the APIs are available across Android and iOS to enable shared AR
experiences. ARCore uses three key capabilities to integrate virtual content with the real world as
seen through your phone’s camera: • Motion tracking allows the phone to understand and track its
position relative to the world. • Environmental understanding allows the phone to detect the size
and location of all type of surfaces: horizontal, vertical and angled surfaces like the ground, a coffee
table or walls. • Light estimation allows the phone to estimate the environment’s current lighting
conditions.
SLAM: Simultaneous Localisation and Mapping
Simultaneous localization and mapping (SLAM) is the computational problem of constructing or
updating a map of an unknown environment while simultaneously keeping track of an agent’s
location within it. While this initially appears to be a chicken-and-egg problem there are several
algorithms known for solving it, at least approximately, in tractable time for certain environments.
Popular approximate solution methods include the particle filter, extended Kalman filter, Covariance
intersection, and GraphSLAM. SLAM algorithms are based on concepts in computational geometry
and computer vision, and are used in robot navigation, robotic mapping and odometry for virtual
reality or augmented reality.


2.Overall Description

2.1 Modules of the System
The system mainly consists of a website and an application. Website can be accessed by admin and
the building owners in order to get the QR code generated. The QR codes of different starting
location details will be available in the website dashboard. Various building owners can log into the
website and can download the required QR codes and can place it at different locations.
 2.1.1 ARCore Localisation
 We used ARCore based indoor positioning and localisation. ARCore’s SLAM algorithm makes use of
other sensors, to complement the obtained spatial information and reduce the intrinsic drift. ARCore
packs all this and more in an easy to use SDK.
 2.1.2 QR-code (re)positioning
 Using the ZXing library, QR codes can be scanned using the camera of the phone. In order to use the
ZXing library in unity, the zxing.unity.dll needs to be placed in the plugin folder. The dll can be
downloaded from here. The QR codes are translated to simple strings, which are identical to the names
used for the gameobjects that represent the locations on the map.
 2.1.3 Unity NavMesh navigation
 Having precise localistation, we proceed to another important aspect of indoor navigation, namely
pathfinding. Finding an optimal route to a destination can be achieved via a couple of methods. You can
make optimal routes beforehand and take the route closest to where the person is standing (beneficial
for AR navigation view). Another possibility, is making a graph model for the outline of the map and
performing an A* algorithm.
 2.1.4 Augmented Reality path showing
Lastly, we arrive at last section of our indoor navigation app, showing the route to take using augmented
reality. The principle achieved in this section is an arrow that spawns in front of the user that points in
the direction the user needs to go as soon as a destination is chosen.


 3.Functionality
 
The project consists of a website and a mobile app. The website is deployed in the cloud. The mobile
application is to be installed by the user so as to navigate throughout the building.
3.1 Web Application
The web application is intended for providing details about the proposed system. The website also
provides login for admin and can access the generated QR codes inside the website dashboard. The
technologies used are HTML, CSS and JS.
3.1.1 Website Homepage
 The figure below shows the website homepage which displays all the information about the system.
3.1.2 Login and Dashboard
The admin can login student registers using the login id and password. From the website dashboard, the
admin can access for QR codes to be placed at different From the website dashboard, the admin can
access for QR codes to be placed at different
3.2 Mobile App
The mobile application is intended for users. The app uses the AStar path finding algorithm to find the
shortest path to the destination. The QR codes are placed at different locations inside the building. The
user can then scan these codes to identify the location. After scanning the QR code, the user can select
the destination from the drop down menu.
