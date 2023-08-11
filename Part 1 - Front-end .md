# TouchCoreSystem_Assignment
<template>
  <div>
    <video-player ref="videoPlayer" :options="videoOptions" @playing="onVideoPlaying" />
    <textarea v-model="subtitleText" @input="onSubtitleTextChanged"></textarea>
    <button @click="addSubtitle">Add Subtitle</button>
    <div v-for="subtitle in subtitles" :key="subtitle.timestamp">{{ subtitle.text }}</div>
  </div>
</template>

<script>
import VideoPlayer from 'vue-video-player';
import 'video.js/dist/video-js.css';

export default {
  components: {
    VideoPlayer,
  },
  data() {
    return {
      videoOptions: {
        controls: true,
        sources: [{
          src: '', // will be updated with the uploaded video URL
          type: 'video/mp4',
        }],
      },
      subtitles: [],
      subtitleText: '',
    };
  },
  methods: {
    onVideoPlaying() {
      // Update subtitles when video is playing
      const currentTime = this.$refs.videoPlayer.currentTime;
      this.updateSubtitlesDisplay(currentTime);
    },
    onSubtitleTextChanged() {
      // Update subtitleText data whenever the textarea is edited
    },
    addSubtitle() {
      // Add the current subtitleText and the timestamp to the subtitles array
    },
    updateSubtitlesDisplay(currentTime) {
      // Update subtitles display based on the currentTime
    },
  },
};
</script>

<style>
textarea {
  display: block;
  width: 100%;
  height: 100px;
  margin-bottom: 10px;
}
</style>
