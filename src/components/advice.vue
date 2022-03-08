<template>
 <div id="advtem">
  <span> Advice #{{ adviceid }} </span>
  <h2>
   {{ `"${advice}"` }}
  </h2>
  <div id="divd">
   <svg width="444" height="16" xmlns="http://www.w3.org/2000/svg">
    <g fill="none" fill-rule="evenodd">
     <path fill="#4F5D74" d="M0 8h196v1H0zM248 8h196v1H248z" />
     <g transform="translate(212)" fill="#CEE3E9">
      <rect width="6" height="16" rx="3" />
      <rect x="14" width="6" height="16" rx="3" />
     </g>
    </g>
   </svg>
  </div>
  <div id="sv">
   <svg
    @click="getAdvice"
    width="24"
    height="24"
    color="hsl(228, 45%, 44%)"
    xmlns="http://www.w3.org/2000/svg"
   >
    <path
     d="M20 0H4a4.005 4.005 0 0 0-4 4v16a4.005 4.005 0 0 0 4 4h16a4.005 4.005 0 0 0 4-4V4a4.005 4.005 0 0 0-4-4ZM7.5 18a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm0-9a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm4.5 4.5a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm4.5 4.5a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Zm0-9a1.5 1.5 0 1 1 0-3 1.5 1.5 0 0 1 0 3Z"
     fill="#202733"
    />
   </svg>
  </div>
 </div>
</template>

<script>
 export default {
  data() {
   return {
    advice: "",
    adviceid: "",
   }
  },
  methods: {
   getAdvice() {
    fetch("https://api.adviceslip.com/advice")
     .then((response) => response.json())
     .then((data) => {
      this.advice = `${data.slip.advice}`
      this.adviceid = data.slip.id
     })
   },
  },
 }
</script>

<style scoped>
 * {
  box-sizing: border-box;
  color: rgb(255, 249, 249);
  background-color: hsl(217, 19%, 24%);
 }
 #advtem {
  display: grid;
  justify-items: center;
  align-items: center;
  height: 300px;
  width: 500px;
  border-radius: 10px;
 }
 span {
  display: block;
  margin-top: 50px;
  position: absolute;
  top: 350px;
  color: hsl(150, 100%, 66%);
 }
 h2 {
  align-self: center;
  text-align: center;
  width: 80%;
 }
 #sv {
  display: flex;
  justify-content: center;
  align-items: center;
  align-self: end;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: hsl(150, 100%, 66%);
  position: absolute;
  transform: translateY(50%);
 }
 #sv svg {
  width: 24px;
  height: 24px;
  border-radius: 10%;
 }
 #divd {
  position: absolute;
  transform: translateY(500%);
  margin-bottom: 20px;
 }
</style>
