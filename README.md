# HW13# 
# Symphony No. 9

A music player that songs with light fleshes.

## Summary

First of all, I was thinking about just making a music player and using the light sensor to control the volume. But later I found that it will be more fun to write a coding that could play music by itself. However, I am not really good at music. Thus I have to do lots of research about rhythms and piths, and transfer them into coding. Additionally I had to consider the pose and the music metre or the music time.

Thus the final project is the music player that has a light flashing with the music plays.


## Component Parts
an Arduino, USB Cable, Breadboard, and a piezo speaker
Defending the rhythm and timing. As well as the light.

## When your project is completed, you will then add the following sections:

## Timeline

Week 1:came up with ideas
Week 2: researches 
- Week 3: coding and tests
- Week 4: Present!
 
## Challenges
 
The is a challenge for me to analysis the rhythm and the array them into a song.
## Completed Work


#define NTD0 -1
#define NTD1 294
#define NTD2 330
#define NTD3 350
#define NTD4 393
#define NTD5 441
#define NTD6 495
#define NTD7 556

#define NTDL1 147
#define NTDL2 165
#define NTDL3 175
#define NTDL4 196
#define NTDL5 221
#define NTDL6 248
#define NTDL7 278

#define NTDH1 589
#define NTDH2 661
#define NTDH3 700
#define NTDH4 786
#define NTDH5 882
#define NTDH6 990
#define NTDH7 112
//c pinlv
#define WHOLE 1
#define HALF 0.5
#define QUARTER 0.25
#define EIGHTH 0.25
#define SIXTEENTH 0.625

int tune[]=
{
  NTD3,NTD3,NTD4,NTD5,
  NTD5,NTD4,NTD3,NTD2,
  NTD1,NTD1,NTD2,NTD3,
  NTD3,NTD2,NTD2,
  NTD3,NTD3,NTD4,NTD5,
  NTD5,NTD4,NTD3,NTD2,
  NTD1,NTD1,NTD2,NTD3,
  NTD2,NTD1,NTD1,
  NTD2,NTD2,NTD3,NTD1,
  NTD2,NTD3,NTD4,NTD3,NTD1,
  NTD2,NTD3,NTD4,NTD3,NTD2,
  NTD1,NTD2,NTDL5,NTD0,
  NTD3,NTD3,NTD4,NTD5,
  NTD5,NTD4,NTD3,NTD4,NTD2,
  NTD1,NTD1,NTD2,NTD3,
  NTD2,NTD1,NTD1
};
float durt[]=
{
  1,1,1,1,
  1,1,1,1,
  1,1,1,1,
  1+0.5,0.5,1+1,
  1,1,1,1,
  1,1,1,1,
  1,1,1,1,
  1+0.5,0.5,1+1,
  1,1,1,1,
  1,0.5,0.5,1,1,
  1,0.5,0.5,1,1,
  1,1,1,1,
  1,1,1,1,
  1,1,1,0.5,0.5,
  1,1,1,1,
  1+0.5,0.5,1+1,
};
int length;
int tonepin = 6;
int led1 = 13;
void setup()
{
  pinMode(tonepin,OUTPUT);
  pinMode(led1,OUTPUT);
  length=sizeof(tune)/sizeof(tune[0]);
}
void loop()
{
  for(int x=0;x<length;x++)
  {
    tone(tonepin,tune[x]);
    digitalWrite(led1, HIGH); 
    delay(400*durt[x]);
    digitalWrite(led1, LOW);
    delay(100*durt[x]);
    noTone(tonepin);
    
  }
  delay(2000);
}




## References and links

https://www.electronicshub.org/music-player-using-arduino/
