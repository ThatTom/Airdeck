<link rel="shortcut icon" type="image/x-icon" href="airdeckicon.png">

[![Airdeck](githubimage.png "Airdeck")](https://github.com/ThatTom/Airdeck)

### What is Airdeck?

Airdeck is a tool designed to allow XPlane simulator enthusiasts with an Elgato Streamdeck the chance to make a fully customised configuration with integration into the simulator with little experience in programming or design skill (Like me). This was originally created as a small project to allow interaction from my Streamdeck into XPlane 11 after starting to take the simulator more seriously and soon realised that this could be used by so many more Virtual Pilots. I will be planning to update the script greatly in the future and any suggestions/concerns are greatly received. Airdeck has also been designed to allow for one person to create the functionality and design and then share it with others very easily. At the time of writing this, the Airdeck currently requires NodeJS and as a result, would require it to be installed however I hope to make the process of using the Airdeck even easier in the future and currently instructions are provided below for the full install and setup of everything required.

##### Libaries used

* [ExtPlaneJs](https://github.com/wadedos/ExtPlaneJs)
* [node-elgato-stream-deck](https://github.com/Lange/node-elgato-stream-deck)

### Aircraft Panel

Each Aircraft that you want to create a panel for requires a .json file which will include the individual folders, each keys specification and the configuration for the aircraft as well. Below is a basic example of the required structure and a full version can be found [here](https://github.com/ThatTom/Airdeck/blob/master/exampleaircraftpanel.json).

```
{
  "defaultfolder": "base",

  "base - {Folder Name}":
  {
      "0  - {Key ID}":
      {
        {Function as required for this key}
      }
   }
}
```

### Included Airdeck Functions

Airdeck currently includes 6 functions in total these are: Single, Single Hold, Dual, Dual Variable, Folder and Aircraft. Each has it's own function to allow for full customisation.

##### Single

The single function is used for commands which you want to run when the key is pressed for example cutting the fuel supply or activating the altitude hold on the autopilot. This will begin the command on pushing the key down and stop again on release to allow for the key to held if needed for example start key on C172.

``` 
"{KEY ID 0 - 14}":
{
  "image": "{Image Loocation}",
  "type": "single",
  "function": "{Command you wish to run in XPlane}"
 }
 ```
 
##### Dual

The dual function is used when a single button requires two functions, for example, a light switch or battery switch. The function allows for two commands to be assigned and two images assigned for each on and off states. The state is toggled each time the key is pressed between off and on. This allows for two separate images or functions in the two states and functions or images can be the same in each.

``` 
"{KEY ID 0 - 14}":
{
  "type": "dual",
  "state": "{Default State On/Off}",

  "on":
  {
      "function": "{Command you wish to run in XPlane}",
      "image": "{Off State Image Loocation}",
  },
  "off":
  {
      "function": "{Command you wish to run in XPlane}",
      "image": "{On State Image Loocation}",
  }
}
 ```
 
 ##### Dual Variable

The dual variable function is used when a single button requires two functions and requires the state to be changed from a datref inside of XPlane. An example of this would be master caution, the function works by updating the state of the key on the Dataref change in-game to either on or off. This allows for two separate images or functions in the two states and functions or images can be the same in each.

``` 
"{KEY ID 0 - 14}":
{
  "type": "dual",
  "state": "{Default State On/Off}",

  "on":
  {
      "function": "{Command you wish to run in XPlane}",
      "image": "{Off State Image Loocation}",
  },
  "off":
  {
      "function": "{Command you wish to run in XPlane}",
      "image": "{On State Image Loocation}",
  } 
}
 ```
 
### Installation

Although every effort is made and is still being made to make Airdeck as easy to use as possible some installation is still required, all steps required for the installation can be found [here](https://github.com/ThatTom/Airdeck/wiki/Installation). These will be kept as up to date as is possible but if you do notice any errors or have any issues installing Arideck at any time then please join the [Discord](https://discord.gg/wCrFWDx) and don't hesitate to ask.
 
### Known Issues

Known issues will be added here was found/reported and will be resolved as soon as possible
