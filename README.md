# NVR-DVR-H.264-playback-using-FFMpeg-in-CSharp

The C# sample code shows you how to use FFMPEG for LILIN NVR/DVR

Visit the source code at https://www.dropbox.com/sh/bc018wx468gqryn/AABh3j0D9F7Nu7TfqXankJm2a?dl=0

# NVR/DVR H.264 playback video

![image](https://github.com/LILINOpenGitHub/NVR-DVR-H.264-playback-using-FFMpeg-in-CSharp/blob/main/video/nvrdvr.gif)

# H.264 playback stream control structure
Directly send the playback control structure through “getpbstream” socket to control streaming content such as fast forward, fast rewind, stop, and pause. The control structure detail is as below: <BR>
<BR>
struct binary_command <BR>
{ <BR>
  DWORD channel;  <BR>
  BYTE mode;  <BR>
  BYTE action; <BR>
  time_t rep_time; <BR>
  BYTE rep_layout;<BR>
  BYTE rep_speed;<BR>
  BYTE rep_control;<BR>
  int rep_dir;<BR>
} ;<BR>
<BR>
# HTTP H.264 Playback Stream Description:<BR>
struct RH<BR>
{<BR>
  DWORD startcode; // 0x5757<BR>
  DWORD rh_length ; // RH + frame length<BR>
  BYTE User_level;<BR>
  DWORD time; // time<BR>
  DWORD prev_rh_length;<BR>
  BYTE ch_id; //channel id<BR>
  BYTE v_format;<BR>
  BYTE v_res;<BR>
  BYTE frame_type;<BR>
  BYTE gop;<BR>
  BYTE data_type; // audio data or video<BR>
  BYTE reserved2;<BR>
}<BR>
Size of RH is 24 Byte<BR>
