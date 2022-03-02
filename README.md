# NVR-DVR-H.264-playback-using-FFMpeg-in-CSharp

The C# sample code shows you how to use FFMPEG for LILIN NVR/DVR

Visit the source code at https://www.dropbox.com/sh/bc018wx468gqryn/AABh3j0D9F7Nu7TfqXankJm2a?dl=0

# NVR/DVR H.264 playback video

![image](https://github.com/LILINOpenGitHub/NVR-DVR-H.264-playback-using-FFMpeg-in-CSharp/blob/main/video/nvrdvr.gif)

# H.264 playback stream control structure
Directly send the playback control structure through “getpbstream” socket to control streaming content such as fast forward, fast rewind, stop, and pause. The control structure detail is as below: <BR>
<BR>
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

# HTTP H.264 Playback Stream Description:
struct RH
{
  DWORD startcode; // 0x5757
  DWORD rh_length ; // RH + frame length
  BYTE User_level;
  DWORD time; // time
  DWORD prev_rh_length;
  BYTE ch_id; //channel id
  BYTE v_format;
  BYTE v_res;
  BYTE frame_type;
  BYTE gop;
  BYTE data_type; // audio data or video
  BYTE reserved2;
}
Size of RH is 24 Byte
