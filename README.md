Convert AVI to MP4 in Mac OS X with Automator and HandBrake
===========================================================

Convert your *.avi downloaded video files to *.mp4 with automator and HandBrake


##Convert with a Service

- Download HandBreakCLI (Command Line) from [HandBrake Downloads Page](http://handbrake.fr/downloads.php), and install into your prefered directory, for example into ```/Applications/HandBreakCLI```
- Open Automator -> New document -> Select Service.
- Select "movie files" in services receives selected and "Finder.app" in application.
- Drag the "Run Shell Script" action.
- Select "/bin/bash" in Shell and "as arguments" in Pass input. 
- Paste the script:

```shell
for if in "$@"
do
  /Applications/HandBrakeCLI -i "$if" -o "$if".mp4 --preset="Normal"
done
```
![ConvertService](converter_automator_service.png)
- Finally save the Service with the name "Convert to mp4".

Now you can convert your video files with Right-click -> Services -> Convert to mp4

Note: If you need delete your custom services, you can find it in ```/Users/YourUserName/Library/Services/```

##Convert automatically with a Folder Action

- Download HandBreakCLI (Command Line) from [HandBrake Downloads Page](http://handbrake.fr/downloads.php), and install into your prefered directory, for example into ```/Applications/HandBreakCLI```
- Open Automator -> New document -> Select Folder Action.  
![Automator](/wizard.png)
- Select the folder where you download your videos.
- Configure the workflow actions like the image below:  
![Automator](/configuration.png)
