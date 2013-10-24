Computer-Science
================

Projects in Computer Science
#Jongseong Lee Partner: Jayden Gardiner
#jlee963@gatech.edu
#We worked on this assignment alone using only this semester's course materials.

from Myro import *
import time

init('sim')

testRight = getObstacle('right')
testLeft = getObstacle('left')
testCenter = getObstacle('center')

def yellowWall():

#need to make this 6 inches or less
    startTime = time.clock()
    print(startTime)
    endTime = startTime + 120
    while startTime <=endTime:
        startTime = time.clock()
        print(startTime)
        pic1 = takePicture()
        mylist = list(getPixels(pic1))
        print(mylist)
        if testCenter < 2000:
            forward(.5)
        elif testRight < 2000:
            turnRight(.5, 2.7)
        elif testLeft < 2000:
            turnLeft(.5, 2.7)
        print(testRight, testLeft, testCenter)
    stop()



def markGreen(myPic):
  for pix in getPixels(myPic):
     r = getRed(pix)
     g = getGreen(pix)
     b = getBlue(pix)
     if r > 100 and b > 100 and g > 70:
        setRed(pix,255)
        setGreen(pix,255)
        setBlue(pix,255)
     else:
       setRed(pix,0)
       setGreen(pix,0)
       setBlue(pix,0)

def pctMarked(pic):
   totalPixels = 0
   whitePixels = 0
   for pix in getPixels(pic):
      if getRed(pix) == 255:
          whitePixels = whitePixels + 1

      totalPixels = totalPixels + 1

   result = whitePixels / float( totalPixels)   #float conversion for python2
   return result
