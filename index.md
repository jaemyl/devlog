# Aug 26, 2018

## google cloud functions for firebase [link](https://codelabs.developers.google.com/codelabs/firebase-cloud-functions/#0)

## AWS lambda

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
