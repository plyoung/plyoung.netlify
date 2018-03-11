+++
title = "Components"
weight = 30
+++

The BGS Components can be found under `menu: Component/BGS`. 

#### 2D

##### 2D/Sprite to Screen Scaler

Auto scales a sprite to screen size according to selected settings. *None, ScaleAndCrop, FitToWidth, FitToHeight, FitToWidthAndHeight, StretchWidth, StretchHeight, StretchWidthAndHeight*.

#### Data

##### Data/Meta Properties

This is used to add BGS variables on a GameObject. These variables can later be accessed by BGS systems and plug-ins pr your own scripts. Have a look at the [variables documentation](/bgs/bgs-vars/) to learn more about using BGS Variables.

#### Helpers

##### Helpers/Disable on Awake

This will disable the GameObject during Awake (when the object is loaded). This component will remove itself once it has done this.

##### Helpers/Don't Destroy on Load

This will set the GameObject to not be destroyed when a scene load occurs. This component will remove itself once it has done this. Normally all objects would be removed when a new scene/ level is loaded, except if the scene is loaded additively. This can prevent this the object from being destroyed in such a case.

##### Helpers/Simple Follower

Make this object follow the target object while a target is assigned.

##### Helpers/Sound Volume Updater

Automatically update the target audio source's volume when the associated volume type changes.




