<template>
    <div>
       <p v-if="jobs.length === 0">Jobs are being Fetched..</p>
       <div v-else v-for="job in jobs" :key="job.id">
           <JobBoardItem :job=job />
       </div>
        
    </div>
</template>
<script >
import data from '../resource/data.json';
import JobBoardItem from './JobBoardItem.vue';

export default {
  components: {
        JobBoardItem
    },
  data() {
    return {
      jobs: data
    }
  },
}
</script>