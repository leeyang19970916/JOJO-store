<template >
  <div>
    <nav
      class="
        navbar navbar-dark
         fixed-top
       
        bg-dark
        flex-md-nowrap
        p-0
        shadow
        d-flex justify-content-between
      "
    >
   
  <a href="#" class="navbar-brand col-md-3 col-lg-2 mr-0 px-3"
        >後台測試區</a
      >

      <button
        class="navbar-toggler position-absolute d-md-none collapsed"
        type="button"
        data-toggle="collapse"
        data-target="#sidebarMenu"
        aria-controls="sidebarMenu"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <input
        class="form-control form-control-dark w-100"
        type="text"
        placeholder="Search"
        aria-label="Search"
      />
     
  <ul class="navbar-nav  px-3">
        <li class="nav-item text-nowrap">
          <a class="nav-link" href="#" @click.prevent="signOut">Sign out</a>
        </li>
      </ul>
  
    
    </nav>
  </div>
</template>


<script>
export default {
  methods: {
    signOut() {
      const vm = this;
      const api = `${process.env.APIPATH}/logout`;
      vm.$http.post(api).then((response) => {
        console.log(response.data);

        if (response.data.success) {
          vm.$router.push("/");
        }
      });
    },
  },
};
</script >

