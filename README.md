
# SSD

<img width="1548" alt="Demo" src="https://github.com/user-attachments/assets/3b39ddf3-c3e8-449b-8c69-e192eefba480">


####  Services

| Name      | DRM | Type     |
| :---        |    :----:   |           :----:  |
| bilibili.tv      | None        | TV + Movie   |
| fptplay.vn   | None        | TV (+Anime)    |
| iq.com   | Widevine        | TV + Movie    |
| vieon.vn   | Widevine        | TV + Movie    |
| youku.tv   | Widevine        | TV     |
| tv360.vn   | None        | TV     |




## How to use


```cmd
  -u="https://fptplay.vn/xem-video/hoi-sinh-the-gioi-phan-3-64c0e183c9a1c91f33a71485/tap-22"
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--url` | `-u` | **Required**. Input URL |


```cmd
  -q="1920"
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--quality` | `-q` | **Default (best)**. Download Resolution [Width] |

```cmd
  -vc="h264"
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--vcodec` | `-vc` | Video Codec to download `[h264 or  h265]` |


```cmd
  -ac="aac"
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--acodec` | `-ac` | Audio Codec to download `[acc]` |

```cmd
  -w="s01e02"
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--wanted` | `-w` | Wanted episodes, e.g. `S01`, `S01E01-S02E03` |

```cmd
  -a="vi,zh"
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--alang` | `-q` | **Default (original language)**. Language(s) wanted for Audios" |

```cmd
  -s="vi,zh"
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--slang` | `-s` | **Default (all)**. Language(s) wanted for Subtitles" |

```cmd
  -S=true
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--video-only` | `-S` | Only download video track `skip audio, subtitle` |

```http
  -A=true -a="vi"
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--audio-only` | `-S` | Only download audio track(s) `skip video, subtitle` |

```http
  -S=true -s="en,vi"
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--subtitle-only` | `-S` | Only download subtitle track(s) `skip video, audio` |

```cmd
  -r="my"
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--region` | `-r` | Region for download (IQIYI)`thailand=th, malaysia=my, taiwan=tw` |


```cmd
  -f=true
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--ffprobe` | `-f` | When a FourCC error occurs in Youku  |

```cmd
  -b=true
```

| Parameter | Aliases     | Description                |
| :-------- | :------- | :------------------------- |
| `--bypass` | `-b` | TV360 ByPass. Uses a trick to get the m3u8 (playlist) but can't get the master playlist. Only supports series, and no DRM is supported |

## L3 Provisidon
The software using GoWideVine is written in Go, similar to PyWideVine (but not publicly available).
If you need to create a new provision file, follow these steps:

- Install python and pywidevine

```cmd
$ pip install pywidevine
```

- [Dumping Your own L3 CDM with Android Studio](https://forum.videohelp.com/threads/408031-Dumping-Your-own-L3-CDM-with-Android-Studio)

- Create file
```cmd
pywidevine create-device -k "/PATH/TO/device_private_key" -c "/PATH/TO/device_client_id_blob" -t "ANDROID" -l 3
```



## Demo



https://github.com/user-attachments/assets/7c8a8105-7c43-41ce-82be-f8333f406f78



## Requirement

Install the software and set the path (environment variable), or place the binary in the tools folder (at the same level as the ssd folder).
No specific version required

- [NodesJS](https://nodejs.org/en)
- [MkvToolnix](https://mkvtoolnix.download/downloads.html)
- [MP4Decrypt](https://www.bento4.com/downloads/)
- [FFMPEG + FFPROBE](https://www.ffmpeg.org/download.html)

## Note

Errors are mainly caused by network issues (inability to read m3u8 files), server problems (failure to download files or null segments), or special cases (due to website changes). Therefore, logging is not necessary.
