# NVR-DVR-H.264-playback-using-FFMpeg-in-CSharp

The C# sample code shows you how to use FFMPEG for LILIN NVR/DVR

Visit the source code at https://www.dropbox.com/sh/bc018wx468gqryn/AABh3j0D9F7Nu7TfqXankJm2a?dl=0

# NVR/DVR H.264 playback video

![image](https://github.com/LILINOpenGitHub/NVR-DVR-H.264-playback-using-FFMpeg-in-CSharp/blob/main/video/nvrdvr.gif)

#H.264 playback stream control structure
Directly send the playback control structure through “getpbstream” socket to control streaming content such as fast forward, fast rewind, stop, and pause. The control structure detail is as below:
struct binary_command
{
  DWORD channel;
  BYTE mode;
  BYTE action;
  time_t rep_time;
  BYTE rep_layout;
  BYTE rep_speed;
  BYTE rep_control;
  int rep_dir;
} ;
