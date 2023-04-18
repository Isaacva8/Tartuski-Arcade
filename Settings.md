# Welcome to the Tartuski wiki!

In this wiki we have the configuration file of the theme and some demonstrative images about the controls that we have.

We take an initial theme and edit it to our liking, moving elements around, inserting images, removing irrelevant pieces of information, changing the selection of consoles and games, and putting in minimal information.

## Next we have a demonstrative pictures with some information :

**The first image is about the all consoles we have in emulator.**
 
![menu1](https://user-images.githubusercontent.com/131180909/232823587-ed3c0ef3-f412-4cf1-b116-5a1cdcf5cf8c.png)

In this first menu we edit:
- We place the selection of consoles on the left with a circular scroll.
- A background image complemented by a video about the background game, randomly selected from one of the console games we are selecting. It changes every time we reselect the console.
- We place the name of the console and the games it contains.

**The second image is about all the games we have within their respective console.**

![menu2](https://user-images.githubusercontent.com/131180909/232823911-1d6392c5-745b-4de6-81ac-506a468a33e7.png)

In this second menu we edit:
- On the top left we put your console, and on the other side the name and how many players can play.
- In the center we place the cover of the game and a trailer of the game we are selecting.
- At the bottom we place the selection of games with a circular scroll, and a selector frame that tells you what game we are watching.
- We place the background cover photo with opacity.

## At this point we have a file that includes everything we have explained before

<theme>
    <transitions>fadeAndSlide</transitions>

    <include>./navigationsounds.xml</include>
    <include>./colors.xml</include>

    <!-- Per-system band colors and platform info -->
    <include>./${system.theme}/colors.xml</include>
    <include>./${system.theme}/systeminfo.xml</include>

    <variables>
        <systemConsoleImage>./${system.theme}/images/consolegame.svg</systemConsoleImage>
        <systemControllerImage>./${system.theme}/images/controller.svg</systemControllerImage>
        <systemLogo>./${system.theme}/images/logo.svg</systemLogo>
    </variables>

    <view name="system">
        <carousel name="systemCarousel">
            <pos>0 0</pos>
            <size>0.28 1</size>
            <type>verticalWheel</type>
            <staticImage>./${system.theme}/images/logo.svg</staticImage>
            <itemsBeforeCenter>4</itemsBeforeCenter>
            <itemsAfterCenter>4</itemsAfterCenter>
            <itemSize>0.15 0.125</itemSize>
            <itemScale>1.23</itemScale>
            <itemRotation>11</itemRotation>
            <itemRotationOrigin>-3.03 0.5</itemRotationOrigin>
            <itemAxisHorizontal>true</itemAxisHorizontal>
            <itemHorizontalAlignment>center</itemHorizontalAlignment>
            <itemVerticalAlignment>center</itemVerticalAlignment>
            <wheelHorizontalAlignment>right</wheelHorizontalAlignment>
            <horizontalOffset>-0.05</horizontalOffset>
            <color>555555BB</color>
            <text>${system.fullName}</text>
            <textColor>F0F0F0</textColor>
            <fontPath>./core/fonts/Exo2-RegularCondensed.otf</fontPath>
            <fontSize>0.056</fontSize>
            <letterCase>uppercase</letterCase>
            <lineSpacing>1.2</lineSpacing>
        </carousel>
        <gameselector name="selectorRecent">
            <selection>lastplayed</selection>
            <gameCount>1</gameCount>
        </gameselector>
        <gameselector name="selectorRandom">
            <selection>random</selection>
            <gameCount>1</gameCount>
        </gameselector>
        <image name="randomBackgroundImage">
            <pos>0 0</pos>
            <size>1 1</size>
            <imageType>fanart, titlescreen</imageType>
            <gameselector>selectorRandom</gameselector>
            <interpolation>nearest</interpolation>
            <opacity>0.5</opacity>
            <saturation>0.8</saturation>
            <zIndex>3</zIndex>
        </image>
        <video name="randomGameVideo">
            <pos>0.30 0.23</pos>
            <maxSize>0.3 0.424</maxSize>
            <imageType>marquee, titlescreen</imageType>
            <gameselector>selectorRandom</gameselector>
            <audio>true</audio>
            <interpolation>linear</interpolation>
            <pillarboxes>false</pillarboxes>
            <scanlines>false</scanlines>
            <delay>1.7</delay>
            <fadeInTime>1.2</fadeInTime>
        </video>
        <text name="gameCounter">
            <pos>0.30 0.082</pos>
            <size>0.35 0.1</size>
            <systemdata>gamecount</systemdata>
            <fontPath>./core/fonts/Exo2-RegularCondensed.otf</fontPath>
            <fontSize>0.048</fontSize>
            <horizontalAlignment>left</horizontalAlignment>
            <color>C6C6C6</color>
            <backgroundColor>55555500</backgroundColor>
            <letterCase>uppercase</letterCase>
            <zIndex>50</zIndex>
        </text>
        <text name="systemName">
            <pos>0.30 0.01</pos>
            <size>0.46 0.1</size>
            <systemdata>fullname</systemdata>
            <fontPath>./core/fonts/Exo2-RegularCondensed.otf</fontPath>
            <fontSize>0.075</fontSize>
            <horizontalAlignment>left</horizontalAlignment>
            <color>E6E6E6</color>
            <backgroundColor>55555500</backgroundColor>
            <letterCase>uppercase</letterCase>
            <zIndex>50</zIndex>
        </text>

        <text name="info1, info2, info3, info4, info5, info6, info7, info8, info9, info10">
            <size>0.4 0.03</size>
            <fontPath>./core/fonts/Exo2-SemiBoldCondensed.otf</fontPath>
            <fontSize>0.021</fontSize>
            <horizontalAlignment>left</horizontalAlignment>
            <color>D6D6D6</color>
        </text>
        <text name="info1">
            <pos>30.58 0.695</pos>
            <horizontalAlignment>right</horizontalAlignment>
        </text>
        <text name="info2">
            <pos>30.58 0.716</pos>
            <horizontalAlignment>right</horizontalAlignment>
        </text>
        <text name="info3">
            <pos>30.58 0.737</pos>
            <horizontalAlignment>right</horizontalAlignment>
        </text>
        <text name="info4">
            <pos>30.58 0.758</pos>
            <horizontalAlignment>right</horizontalAlignment>
        </text>
        <text name="info5">
            <pos>30.58 0.799</pos>
            <horizontalAlignment>right</horizontalAlignment>
        </text>
        <text name="info6">
            <pos>30.58 0.820</pos>
            <horizontalAlignment>right</horizontalAlignment>
        </text>
        <text name="info7">
            <pos>30.58 0.841</pos>
            <horizontalAlignment>right</horizontalAlignment>
        </text>
        <text name="info8">
            <pos>30.58 0.862</pos>
            <horizontalAlignment>right</horizontalAlignment>
        </text>
        <text name="info9">
            <pos>30.58 0.883</pos>
            <horizontalAlignment>right</horizontalAlignment>
        </text>
        <text name="info10">
            <pos>30.58 0.904</pos>
            <horizontalAlignment>right</horizontalAlignment>
        </text>


        <rating name="randomGameRating">
            <pos>0.30 0.167</pos>
            <size>0.06 0.04</size>
            <gameselector>selectorRandom</gameselector>
            <color>FFEE00</color>
            <opacity>0.9</opacity>
        </rating>

        <helpsystem name="help">
            <pos>0.9885 0.955</pos>
            <origin>1 0</origin>
            <textColor>A6A6A6</textColor>
            <iconColor>A6A6A6</iconColor>
            <textColorDimmed>969696</textColorDimmed>
            <iconColorDimmed>969696</iconColorDimmed>
        </helpsystem>
    </view>
 
   
![image](https://user-images.githubusercontent.com/131180909/232867139-8acb8ba9-b64e-4a4e-8f45-a2d77a464e40.png)

![image](https://user-images.githubusercontent.com/131180909/232867299-ca4d8ee8-1cd8-44ac-b554-0fc23ceaee1b.png)

![image](https://user-images.githubusercontent.com/131180909/232867521-5331d8da-9ba5-4b69-abc3-db25e95f2749.png)

![image](https://user-images.githubusercontent.com/131180909/232867934-91e2656c-4d10-4e47-9811-75fba89b974d.png)

![image](https://user-images.githubusercontent.com/131180909/232868093-f4667b03-8359-4498-bfd7-7504f0a3c7a9.png)

