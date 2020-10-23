<template>
  <div>
    <NavBar />
    <Challenge
      v-for="challenge in allChellenges" :key="challenge.index"
      :challengerName = challenge.challengerName
      :challengeeName = challenge.challengeeName
      :statement = challenge.statement
      :hashtags = challenge.hashtags
    />
  </div>
</template>

<script>
import NavBar from '@/components/NavBar'
import 'bootstrap/dist/css/bootstrap.css'
import 'bootstrap-vue/dist/bootstrap-vue.css'
import Challenge from '@/components/Challenge'

export default {
  components: {
    Challenge,
    NavBar
  },
  data () {
    return {
      allChellenges: [{
        index: 1,
        challengerName: 'Anya',
        challengeeName: 'Boris',
        statement: 'Cats are smarter than dogs',
        hashtags: '#cats #dogs #smart'
      },
      {
        index: 2,
        challengerName: 'Nikita',
        challengeeName: 'Vanya',
        statement: 'Dogs are smarter than cats',
        hashtags: '#cats #dogs #smart'
      },
      {
        index: 3,
        challengerName: 'Misha',
        challengeeName: 'Katya',
        statement: 'Dogs are smarter than cats',
        hashtags: '#cats #dogs #smart'
      }]
    }
  }
}
</script>
