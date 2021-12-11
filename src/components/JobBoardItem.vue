
<template>
  <div class="flex bg-white shadow-lg m-4 p-6 rounded">
    <div> 
      <img :src="getSrc" :alt="job.company" />
    </div>
    <div class="flex flex-col justify-between ml-4">
      <h3  class="primary font-bold">{{ job.company }}
      <span class="labels text   px-2 py-1 mx-2 rounded-full" v-show="job.new">NEW</span>
      <span class="bg-gray-800 text-white rounded-full px-2 py-1" v-show="job.featured">FEATURED</span>
      </h3>
      <h2 class="font-bold text-lg">{{ job.position }}</h2>
      <p class="text-gray-700">
        {{ job.postedAt }} &middot; {{ job.contract }} &middot;
        {{ job.location }}
      </p>
    </div >
     
    <div class="primary flex ml-auto items-center font-bold">
     <span class="labels font-bold p-0.5 mx-2">{{job.role}}</span>
     <span class="labels font-bold p-0.5  mx-2">{{job.level}}</span>
     <span class="labels font-bold p-0.5 mx-2" v-for="(language, index) in job.languages" :key=index>{{language}}</span> 
     <span class="labels font-bold p-0.5 mx-2" v-for="(tool, index) in job.tools" :key=index>{{tool}}</span> 
    </div>
  </div>
</template>

<script>
export default {
  props: ["job"],
  computed: {
    getSrc() {
      const path = this.job.logo;
      const modules = import.meta.globEager("../assets/images/*.svg");
      return modules[path].default;
    },
  },
};
</script>
<style >

.primary {
  color: hsl(180, 29%, 50%);
  font-family: 'Spartan', sans-serif;
  font-size: 15px;
}

.labels{
  color: hsl(180, 29%, 50%);
  background-color: hsl(180, 52%, 96%);
}
</style>
