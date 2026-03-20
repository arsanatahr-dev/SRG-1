<html>
<head>
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<style>
html, body {
  margin: 0;
  padding: 0;
  background: transparent;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.video-container {
  width: 100%;
  max-width: 720px;
  aspect-ratio: 16/9;
}
video {
  width: 100%;
  height: 100%;
}
</style>
</head>
<body>

<div class="video-container">
  <video id="video" controls autoplay muted playsinline></video>
</div>

<script src="https://cdn.jsdelivr.net/npm/hls.js@latest"></script>
<script>
const video = document.getElementById('video');
const src = 'https://jmlive.jasamarga.com/hls/16/cfb71103-bc0a-4c71-945f-33544cb879ee/index.m3u8';

if (Hls.isSupported()) {
  const hls = new Hls({
    maxBufferLength: 30
  });
  hls.loadSource(src);
  hls.attachMedia(video);
} else if (video.canPlayType('application/vnd.apple.mpegurl')) {
  video.src = src;
}
</script>

</body>
</html>
