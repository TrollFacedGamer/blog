# Miner Robot Clicker
## Introduction
Around May of 2024 me and my class at the Brooklyn Steam Center began a project where we were each tasked with creating a clicker game. Clicker games are games where the player repetitively clicks a button to progress and generally come with additional features such as upgrades that can essentially autoclick for the player. However, clicker games have to be themed to make them interesting so the first step to making our clicker games was coming up with a theme and then create a general design on services such as draw.io and canva, with me personally used [canva](https://www.canva.com/design/DAGFybpuzCw/nvcM49gAaRk_RX6Vbh4diw/edit?utm_content=DAGFybpuzCw&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton) for the design and going for a robot and mining theme. We used images from sites like [freepik.com](https://www.freepik.com/popular-photos) and [shutterstock.com](https://www.shutterstock.com/search/robots-mining) to create a visual outline based on the theme for the webpage that we will base our clicker game on. Of course the images we got from the internet often did not meet our expectations and we had to use some creative ways to edit the images before usage. For example, I found some quality images for some robots, but they were part of the same image file, so I had to use command + shift + 4 to screenshot part of the images to isolate the robot image I wanted to use.

## HTML
After we completed the design of our clicker game we started the programming phase. The one of the first things we did after setting up the base of our HTML using ! + enter was to use [grid.layoutit.com](https://grid.layoutit.com/) to create a grid in our html. This was the first time I encountered a grid; it was a very interesting and a great learning experience. The grid let us cut our web page into a 3 section by 3 section webpage, which allowed us to place HTML elements side by side in different sections. Once we were done with the grid we placed in the Elements such as buttons and paragraphs to make the webpage take on game-like features. My clicker game’s name Miner Robot Clicker Is placed on the top most grid layer as a header. The buttons and description for the upgrades were placed in a table on the right half of the page. The main clicking button where players click to get points or ore in this case was placed on the left half of the page. A display for the total ore per second that was auto mined through the upgrades was placed below the main clicking button. The upgrade and error logs were placed below the total ore per second display. The sound toggle buttons that were a last minute addition were placed right below the log display. Lastly I placed a By: Benny Wang below the sound toggle buttons as my mark of authorship.

## Javascript
Once we were done with HTML we began coding the javascript part of our game, as Javascript is needed to make the game function. The first part of the Java script we coded was the main clicking button code that added points to the player. It wasn’t all that difficult but we did have to revisit the code for it to make it compatible with the upgrade that came later. Next came the code for upgrade purchases buttons and labels. The main difficulty in making the Javascript code for the upgrade purchase’s buttons and labels was making upgrade prices and stat dynamic and getting everything to display, but the most important aspect of this set of code was the code that made the auto clicking/mining systems give out its promised points(ore). The auto clicking/mining systems used a setInterval() function to execute the function that will give an appropriate amount of point(ore) based on the upgrades possessed by the player. This was then first time I used the setInterval() function and it gave me a few ideas of how to code other programs to run code in loops.

### Javascript Set Interval Code
```
setInterval("autoMine()", 5000);
function autoMine() {
    ore = ore + buff2LvValue * 1
    ore = ore + buff3LvValue * 10
    ore = ore + buff4LvValue * 50
    ore = ore + buff5LvValue * 150
    oreValue.innerText = ore
}
```

## CSS
There was also a bit of CSS coding. Me and my class were required to give our game unique fonts and i personally chose the [Pixelify Sans](https://fonts.google.com/specimen/Pixelify+Sans) font family, we used [google fonts](https://fonts.google.com/) to search for fonts. There were also additions such as background color and the lines for the table that held the upgrade buttons and description that required CSS to look be applied. In addition the grid mentioned early requires CSS to work and some of the images used had to be resized with CSS to fit properly.

### CSS Grid Code
```
.container {  display: grid;
    grid-template-columns: 1.2fr 0.8fr 1fr;
    grid-template-rows: 0.2fr 2.8fr 0.2fr;
    gap: 0px 0px;
    grid-auto-flow: row;
    grid-template-areas:
      "Heading Heading Heading"
      "Clicking Store Store"
      "Footer Footer Footer";
      height: 100vh;
  }
  
  .Heading { grid-area: Heading; }
  
  .Footer { grid-area: Footer; }
  
  .Store { grid-area: Store; }
  
  .Clicking { grid-area: Clicking; }
```

## Howl
After class was largely done with the code that made the game itself work, we moved on to bringings sound to our game. We used a [howler. js](https://github.com/goldfire/howler.js) an audio library to add sound effects to our games. However, we had to get the audio files before we could add any sound to our game. We used [opengameart](https://opengameart.org/), [undesign](https://undesign.learn.uno/audio/), and other free audio websites to source our sound effects. In particular the sourcing of the sound for the hitting of a pickaxe against stone was difficult and time consuming, as there were no recordings of metal hitting stone, and after much searching I ended up using a recording of glass breaking for the sound of the game’s pickaxe hitting stone.

### Javascript Howl code
```
//Audio
let music = new Howl({
    src: ['audios/emotional_piano.ogg'],
    autoplay: true, // start music immediately
    loop: true, // loop music endlessly
})
let soundMining = new Howl({
    src: ['audios/1965_glass-breaking-04.mp3'],
})
let soundPicaxe = new Howl({
    src: ['audios/knifesharpener2.mp3'],
})
let soundBeep = new Howl({
    src: ['audios/2052_beep-01.mp3'],
})
let soundShortBeep1 = new Howl({
    src: ['audios/1828_beep-short-01.mp3'],
})
let soundShortBeep2 = new Howl({
    src: ['audios/1829_beep-short-02.mp3'],
})
let soundMachine = new Howl({
    src: ['audios/2064_jackhammer-01.mp3'],
})
let soundWarning = new Howl({
    src: ['audios/warningbeep-Parking Garage Warning Buzzer 01.mp3'],
})
```