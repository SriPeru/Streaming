# HTML5 Video

HTML5 <video> element helps browsers to load Video from server with lesser effort.

**Sample HTML5 video**

    <video width=”320″ height=”240″ controls=”controls”>
        <source src=testmovie.mp4″ type=”video/mp4″ />
        <source src=testmovie.ogg” type=”video/ogg” />
        Your browser does not support the video tag.
    </video>

    With more information, help you to know more about the backward compatibility

    <video width="480" height="360" controls autoplay>
      <!-- .mp4 file must come first for Safari.  IE9 will also play. -->
      <source src="testmovie.mp4" />
      <!-- Firefox 4.x, Google Chrome, and Opera will play the .webm format -->
      <source src="testmovie.webm" />
      <!-- Firefox 3.5/3.6 will only play .ogv files -->
      <source src="testmovie.ogv" />
      <!-- If all else fails, the script below will try to launch the Flash player. -->
      <embed
          src="YTPlayer.swf"
          flashvars="movieName=testmovie.mp4&autoStart=true"
          width=480
          height=390
          allowFullScreen=true
          type="application/x-shockwave-flash"
          pluginspage="http://get.adobe.com/flashplayer" />
      </video>

#### Below are the configuration for Video/audio elements:

1. controls : adds controls to your video element such as play, volume and pause.

2. type : specifies type of format for the video file. It will play compatible format for browser[Check <a href="#browser_support">browser support</a>].

3. src : source or location of your audio file.

4. Height and Width : You can also specify height and width of your video element on your site page.

#### How to convert the videos to multiple web formats:

Below command converts to .mp4 files:
   ffmpeg -threads 4 -i input_video.mts -i_qfactor 0.71 -qcomp 0.6
         -qmin 10 -qmax 63 -qdiff 4 -trellis 0 -vcodec libx264 
         -s 640x360 -b:v 1000k -b:a 56k -ar 22050 output_video.mp4
and this command to convert to .webm files (libvpx vcodec):
   ffmpeg -threads 4 -i input_video.mts -s 640x360 -qmax 63 -b:v 1000k
         -b:a 56k -ar 22050 -acodec vorbis output_video.webm
and finally this command to convert to .ogv files (libtheora vcodec):
   ffmpeg -i input_video.mts -s 640x360 -qmax 63 -b:v 1000k
         -b:a 56k -ar 22050 -acodec vorbis output_video.ogv


[http://www.willus.com/author/streaming2.shtml](http://www.willus.com/author/streaming2.shtml)

Check out the encoding instructions in [http://diveintohtml5.info/video.html](http://diveintohtml5.info/video.html)

### Browser Support <a name="browser_support"></a>

<table>
<tbody>
<tr>
<th width="20%" align="left">
<h1><strong>Browser</strong></h1>
</th>
<th width="16%" align="left">
<h1><strong>MP4</strong></h1>
</th>
<th width="16%" align="left">
<h1><strong>WebM</strong></h1>
</th>
<th width="16%" align="left">
<h1><strong>Ogg</strong></h1>
</th>
</tr>
<tr>
<td>Internet Explorer 9</td>
<td>YES</td>
<td>NO</td>
<td>NO</td>
</tr>
<tr>
<td>Firefox 4.0</td>
<td>NO</td>
<td>YES</td>
<td>YES</td>
</tr>
<tr>
<td>Google Chrome 6</td>
<td>YES</td>
<td>YES</td>
<td>YES</td>
</tr>
<tr>
<td>Apple Safari 5</td>
<td>YES</td>
<td>NO</td>
<td>NO</td>
</tr>
<tr>
<td>Opera 10.6</td>
<td>NO</td>
<td>YES</td>
<td>YES</td>
</tr>
</tbody>
</table>

- WebM = WebM files with VP8 video codec and Vorbis audio codec
- Ogg = Ogg files with Theora video codec and Vorbis audio codec
- MP4 = MPEG 4 files with H264 video codec and AAC audio code