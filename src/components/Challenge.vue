<template>
  <b-container>
    <b-card class="challenge-wrapper mx-auto">
      <b-row class="first-row">
        <b-col cols="3">
          <b-img v-bind="mainProps" rounded="circle" alt="Circle image"></b-img>
          <div class="author">@{{ challengerName }}</div>
        </b-col>
        <b-col class="center"><div class="timer">Timer</div></b-col>
        <b-col cols="3">
          <b-img v-bind="mainProps" rounded="circle" alt="Circle image"></b-img>
          <div class="author">@{{ challengeeName }}</div>
        </b-col>
      </b-row>
      <b-row>
        <b-col class="video-card">
          <div class="challenger-video"
            @mouseover="startChallengeVideo(true)"
          ></div>
          <div class="challengee-video"
            :class="{'z-index': hoveredChallengeeVideo}"
            @mouseover="startChallengeVideo(false)"
          ></div>
        </b-col>
      </b-row>
      <b-row class="center mt-1">
        <b-card class="statement">
          <span>{{ statement }}</span>
        </b-card>
      </b-row>
      <span class="hashtags">{{ hashtags }}</span>
    </b-card>
  </b-container>
</template>

<script>
export default {
  name: 'Challenge',
  data () {
    return {
      mainProps: { blank: true, blankColor: '#777', width: '75 auto', height: '75 auto', class: 'm1', center: true },
      hoveredChallengeeVideo: false
    }
  },
  methods: {
    startChallengeVideo (challenger) {
      if (challenger) {
        this.hoveredChallengeeVideo = false
      } else {
        this.hoveredChallengeeVideo = true
      }
    }
  },
  props: ['challengerName', 'challengeeName', 'statement', 'hashtags']
}
</script>

<style scoped lang="scss">
%flex-center{
  display: flex;
  align-items: center;
  justify-content: center;
}

.challenge-wrapper{
  width: 592px;
  height: auto;
  @extend %flex-center;
  margin-top: 1rem;
  border-radius: 25px;
  padding-bottom: 0;
  .card-body{
    padding-bottom: 0;
  }
}

.statement{
  width: 95%;
  border-radius: 25px;
  background-color: blue;
  color: white;
  .card-body{
    padding: 15px;
  }
}

.video-card{
  display: flex;
  width: 100%;
  max-width: 100%;
  padding: 0;
}

.challenger-video{
  height: 466.663px;
  width: 60%;
  background-color: #00ff90;
  border-radius: 25px;
  z-index: 10;
}

.challengee-video{
  height: 466.663px;
  width: 60%;
  margin-left: 40%;
  background-color: red;
  border-radius: 25px;
  position: absolute;
}

.timer{
  width: 9.5rem;
  height: 3rem;
  background-color: blue;
  color: white;
  border-radius: 35px;
  @extend %flex-center
}

.first-row{
  @extend %flex-center
}

.author{
  color: black;
  font-size: 1rem;
  width: auto;
  margin-right: 0.2rem;
}

.center{
  @extend %flex-center
}

.z-index{
  z-index: 15;
}

.hashtags{
  color: grey;
  font-size: 0.8rem;
  display: flex;
  margin: 5px 0 5px 0;
}
</style>
