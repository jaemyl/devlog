# Aug 22, 2018

## Depoying node server on Heroku
Simple with just a couple of changes, once you know that. :)
```
// server.js
const MONGODB_URI = process.env.MONGODB_URI || `mongodb://localhost:27017/${DATABASE_NAME}`;
const APP_PORT = process.env.PORT || 3000
```

# Aug 23, 2018

## Node Hosting
Have been researching about free node hosting for some time.
- Heroku
-- Heroku offers a free tier for hobbyists, but they shut down the servers after **30 minute idling**. Then, a new http request seems to trigger restarting the server and response comes after **~10 secs delay** in my tests. Also there is a limit on the number of DB rows(max 10K?) from free mLab add-on.
- RedHat OpenShift
-- Didn't try it, but their free tier seems to offer **just a littple bit more generously than Heroku's??**.
- Amazon Elastic Beanstalk or Lamba
-- Eventual destination??

# Aug 24, 2018

## Blokus web app [the link](https://g30133.github.io/blokus)
Programming to support Blokus piece to be rotated and flipped was the most interesting part. Introduced another layer of indirection to describe the relative position of each units within a blokus piece.
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
