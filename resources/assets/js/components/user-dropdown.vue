<template>
  <div class="dashboard-userDropdownMenu" v-show="visible" transition="dashboard-userDropdownMenu">
    <ul class="dashboard-userDropdownMenuItems">
      <li class="dashboard-userDropdownMenuItem"><a href="#">Settings</a></li>
      <li class="dashboard-userDropdownMenuItem"><a href="mailto:hello@astralapp.com">Support & Feedback</a></li>
      <li class="dashboard-userDropdownMenuItem"><a href="github.com/astralapp/astral" target="_blank">GitHub</a></li>
      <li class="dashboard-userDropdownMenuItem"><a href="https://www.creatorlove.com/syropian/astral" target="_blank"><i class="fa fa-heart"></i> Creator Love</a></li>
      <li class="dashboard-userDropdownMenuItem"><a href="/logout" @click.prevent="logout">Sign Out</a></li>
    </ul>
  </div>
</template>
<script>
import ls from "local-storage";
export default {
  name: "UserDropdown",
  props: ["visible"],
  methods: {
    logout(){
      ls.remove("jwt");
      ls.remove("access_token");
      this.$route.router.go("/auth");
    }
  }
}
</script>
