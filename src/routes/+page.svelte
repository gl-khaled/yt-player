<script lang="ts">
  import { YtDlp } from "ytdlp-nodejs";

  const ytdlp = new YtDlp();
  async function downloadVideo() {
    try {
      const output = await ytdlp.downloadAsync(
        "https://www.youtube.com/watch?v=_AL4IwHuHlY",
        {
          onProgress: (progress) => {
            console.log(progress);
          },
          // others args
        },
      );
      console.log("Download completed:", output);
    } catch (error) {
      console.error("Error:", error);
    }
  }

  downloadVideo();
</script>
