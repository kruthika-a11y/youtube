# youtube

import sys

from pytube import YouTube #imports youtube video
link=input("enter the link:  " )
yt = YouTube(link) #accepts the input from user
print("Title: ",yt.title)
print("number of views: ",yt.views)
print("length of video: ",yt.length,"seconds")  #information about video
print("Description: ",yt.description)
print("Ratings: ",yt.rating)
print(yt.streams) #prints all available streams
print(yt.streams.filter(only_audio=True))
print(yt.streams.filter(only_video=True))
print(yt.streams.filter(progressive=True))

ys=yt.streams.get_highest_resolution()
print("Downloading..")
ys.download()
print("done!!")

