<p align="center">
    <a href="https://github.com/Ayhan-Mohammadi/pytgcalls">
        <img src="https://user-images.githubusercontent.com/32808683/111091141-62473b00-8508-11eb-9c05-3e0fd4a21af3.png" alt="pytgcalls logo" />
    </a>
    <br>
    <b>A simple and elegant client that allows you to make group voice calls quickly and easily.</b>
    <br>
    <a href="https://github.com/Ayhan-Mohammadi/pytgcalls/tree/master/example">
        Examples
    </a>
    •
    <a href="https://pypi.org/project/py-tgcalls/">
        PyPi
    </a>
    •
    <a href="https://t.me/Ayhan_Mohammadi">
        Channel
    </a>
    •
    <a href="https://t.me/devexprgp">
        Chat
    </a>
</p>



This project allows making Telegram group call using MtProto and WebRTC, this is possible thanks to the power of NodeJS's WebRTC library and [@evgeny-nadymov]

## What are the supported clients?
The supported clients for now are Pyrogram and Telethon, but we accept other clients too, you can open a pull request with the edits

## How to install?
Here's how to install the PyTgCalls lib, the commands are given below:

``` bash
# With Git
pip install git+https://github.com/Ayhan-Mohammadi/pytgcalls -U

# With PyPi (Recommended)
pip install py-tgcalls -U
```

## Conversion command (Video)
From file to raw video
``` bash
ffmpeg -i {INPUT_FILE} -f rawvideo -pix_fmt yuv420p -vf scale=640:-1 {OUTPUT_FILE}
```

From H264/VP8/VP9 to Audio and Video
``` bash
ffmpeg -i {INPUT_FILE} -f s16le -ac 1 -ar {BITRATE} {OUTPUT_AUDIO_FILE} -f rawvideo -r {FRAMERATE} -pix_fmt yuv420p -vf scale={SCALING}:-1 {OUTPUT_VIDEO_FILE}
```

From YouTube video/live-stream to Audio and Video
``` bash
ffmpeg -i "$(youtube-dl -x -g "{YOUTUBE_LINK}")" -f s16le -ac 1 -ar {BITRATE} {OUTPUT_AUDIO_FILE} -f rawvideo -r {FRAMERATE} -pix_fmt yuv420p -vf scale={SCALING}:-1 {OUTPUT_VIDEO_FILE}
```

From YouTube Live stream to Video

> ### Important!
> The max resolution allowed by Telegram is of 720p at 30 fps
> Here also listed the scaling format
> - 360p = 640
> - 480p = 854
> - 720p = 1280
>
> If you have any problem with green screen or un-synchronized video, it can be one of these problems:
> - Invalid FFMPEG command
> - The video quality specified to convert is higher than the original video one
> - Invalid PyTgCalls video parameters
> - If you're using fifo, the Fifo max buffer size is too low and this cause the lag problem.

## Conversion commands

From file to raw format
``` bash
ffmpeg -i {INPUT_FILE} -f s16le -ac 1 -ar {BITRATE} {OUTPUT_FILE}
```

From stream link to raw format
``` bash
ffmpeg -y -i {STREAM_LINK} -f s16le -ac 1 -ar {BITRATE} {OUTPUT_FILE}
```

From YouTube video/live-stream to raw format
``` bash
ffmpeg -i "$(youtube-dl -x -g "{YOUTUBE_LINK}")" -f s16le -ac 1 -ar {BITRATE} {OUTPUT_FILE}
```

