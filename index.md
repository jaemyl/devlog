# Sep 12, 2018

## Youtube Javascript Player
Seems exposed custom events like yt-action, yt-navigate, and etc, could be used to dig the interval of yt-app player

---

# Sep 11, 2018

## Youtube Iframe API [Link](https://developers.google.com/youtube/iframe_api_reference)

## Wifi Adapter not connecting issue
Got clue from dmesg by line 'mach_set_rtc_mmss: Invalid RTC value'
Had to manually set system time to silence the error message, which solved wifi adapter connection problem

---

# Aug 31, 2018

## Hearthstone Decktracker log.config [Link](https://github.com/jleclanche/fireplace/wiki/How-to-enable-logging)
Once the log.config is set, we can get poewr.log, which contains the hearthstone play logs. Using it, we can make basic decktracker clone.

---

# Aug 30, 2018

## chrmoe extensions for enotes.com and metabomb.net
Simple extensions to unblur or unveil the pages

---

# Aug 29, 2018

## YouTube Player API Reference for iframe Embeds [Link](https://developers.google.com/youtube/iframe_api_reference)

## html iframe

## Window.postMessage()

---

# Aug 28, 2018

## aws ec2 setup
Was easier to set up a mongodb and node server than I expected, because I just set up one instance in oregon? Possibly more tricky if I had tried to set up multiple instances for clustering mongodb and node. Anyway, aws ec2 was pretty easy to get started.

---

# Aug 27, 2018

## devbackend setup on heroku with mlab
setup my heroku server only to run as api endpoints for multiple apps. With CORS setup on heroku side, now the clients from github.io can access api endpoints on heroku.
heroku mlab in free tier only provides one db, but with multiple collections. So probably I just set separate collections for each app. Possibly good enough for prototyping?

---

# Aug 26, 2018

## google cloud functions for firebase [link](https://codelabs.developers.google.com/codelabs/firebase-cloud-functions/#0)
Seems to be easy to use with good documentation, but there are negative reviews about its reliability and flexibility.

## AWS lambda, ec2 and lightsail
Too many aws products out there. lightsail advertises it as good choice for quick startup.

---

# Aug 25, 2018

## git for windows platform from git-scm.com
updated to ver 2.18 from ver 2.13, and solved issue when 'npm run deploy'

## simulating --cell-size = min(33vw, 33vh) using css variable and @media query
```
:root {
  --cell-size: 33vw;
}
@media (min-aspect-radio: 1/1) {
  :root {
    --cell-size: 33vh;
  }
}
.tictactoe-board {
  display:grid;
  grid-template-columns: repeat(3, var(--cell-size));
  grid-template-rows: repeat(3, var(--cell-size));
}
```

## google firebase web codelab [link](https://codelabs.developers.google.com/codelabs/firebase-web/#0)
Wasted a bit of time to figure out auth failure on running the example. Turned out I mistakenly enabled rules on 'Cloud Firestore', not on 'Realtime Database'. Anyway, seems to be easy and good enough for simple web apps. Particularly liked it made the authentication easy.

---

# Aug 24, 2018

## Blokus web app [the link](https://g30133.github.io/blokus)
Programming Blokus pieces to rotate and flip was the most interesting part. Introduced another layer of indirection to describe the relative position of each units within a blokus piece.
```
// Piece.ts
interface Delta {
  dr:number
  dc:number
}
class Piece {
  unitsDeltas: Delta[]
  unitIxs: number[]
  
  setupPosition(nRows, nCols, startRow, startCol, rotationAngle, flipFace)
  emit(board)
}
```

## gh-pages node module
There is an [instruction](https://github.com/facebook/create-react-app/blob/master/packages/react-scripts/template/README.md#deployment) from creae-react-app for easy deployment on github page.


## Github page and Jekyll
Realized github page can be a good hosting option for static weg apps(**with javascript**), and also for devlog. :) Need to learn a bit of Jekyll btw.

---

# Aug 23, 2018

## Node Hosting
Have been researching about free node hosting for some time.
- Heroku
-- Heroku offers a free tier for hobbyists, but they shut down the servers after **30 minute idling**. Then, a new http request seems to trigger restarting the server and response comes after **~10 secs delay** in my tests. Also there is a limit on the number of DB rows(max 10K?) from free mLab add-on.
- RedHat OpenShift
-- Didn't try it, but their free tier seems to offer **just a little bit more generously than Heroku's??**.
- Amazon Elastic Beanstalk or Lamba
-- Eventual destination??

## YouTube IFrame Player API
Tested the examples. Was simple and easy to use.

---

# Aug 22, 2018

## Deploying node server on Heroku
Simple with just a couple of changes, once you know that. :)
```
// server.js
const MONGODB_URI = process.env.MONGODB_URI || `mongodb://localhost:27017/${DATABASE_NAME}`;
const APP_PORT = process.env.PORT || 3000
```
