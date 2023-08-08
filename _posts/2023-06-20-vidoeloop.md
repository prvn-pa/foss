---
layout: post
title: "Video Looping and Audio Extraction with FFmpeg"
date: 2023-06-20 12:39:00 +0900
background: '/img/ps-03.jpg'
---

## Introduction

FFmpeg is a powerful and versatile command-line tool that allows users to manipulate multimedia files with ease. Whether you're a content creator, video editor, or just someone who loves tinkering with multimedia, FFmpeg has a wealth of features to explore. In this blog post, we'll walk you through some essential FFmpeg commands to loop videos, trim clips, and extract audio effortlessly.

1. Looping a Video Bit

Do you have a video clip that you want to loop indefinitely? FFmpeg makes it a breeze with just one command:
```bash
ffmpeg -stream_loop -1 -i input.mp4 -c copy output.mp4
```
This command ensures that the input video (`input.mp4`) is seamlessly looped in the output video (`output.mp4`). The `-stream_loop -1` flag tells FFmpeg to loop the video infinitely.

2. Looping an Audio File

Looping audio files can be achieved with a similar approach. Before using the looping command, convert the mp3 file to the m4a format using Audacity or any other audio editing tool. Then, use the following command, replacing `.mp4` with `.m4a`:
```bash
ffmpeg -stream_loop -1 -i input.m4a -c copy output.m4a
```
This command lets you loop the audio file (`input.m4a`) indefinitely, creating the final output (`output.m4a`) with the repeated audio.

3. Trimming a Video Clip

Need to extract a specific segment from a lengthy video? FFmpeg can trim videos easily using the `-t` flag. For instance, to trim the video to 900 seconds (15 minutes), use this command:
```bash
ffmpeg -i input.mp4 -t 900 -c copy output.mp4
```
With this command, FFmpeg will create a new video (`output.mp4`) containing only the first 900 seconds of the original video (`input.mp4`).

4. Cutting a Video Between Specific Times

Sometimes, you may need to cut a video between particular start and end times. FFmpeg makes it a piece of cake with the following command:
```bash
ffmpeg -ss [start] -i input.mp4 -to [end] -c copy output.mp4
```
Replace `[start]` with the desired starting time and `[end]` with the desired end time. This command will create a new video (`output.mp4`) containing the segment between the specified start and end times.

5. Extracting Audio from a WebM File

Need to extract audio from a WebM video? FFmpeg's got you covered! Use the following command to extract audio in MP3 format:
```bash
ffmpeg -i input.webm -vn -ab 128k -ar 44100 -y output.mp3
```
This command will extract the audio from `input.webm` and save it as an MP3 file (`output.mp3`).

## Conclusion

FFmpeg is a treasure trove for multimedia enthusiasts, offering an array of powerful tools to manipulate videos and audio files effortlessly. Whether you want to loop a video, trim clips, or extract audio, FFmpeg provides the flexibility and precision you need.