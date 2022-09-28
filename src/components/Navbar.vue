<template>
  <div class="sidebar">
    <ul>
      <li class="sidebar__item active" v-on="{mouseover: handleHover, mouseleave: handleLeave}" id="item-1" ref="li-1">
        <a href="#">
        <span class="icon">
          <ion-icon name="home-outline"></ion-icon>
        </span>
        <span class="title">Home</span>
        </a>
      </li>
      <li class="sidebar__item" v-on="{mouseover: handleHover, mouseleave: handleLeave}" id="item-2" ref="li-2">
        <a href="#">
        <span class="icon">
          <ion-icon name="people-outline"></ion-icon>
        </span>
        <span class="title">Profile</span>
        </a>
      </li>
      <li class="sidebar__item" v-on="{mouseover: handleHover, mouseleave: handleLeave}" id="item-3" ref="li-3">
        <a href="#">
        <span class="icon">
          <ion-icon name="chatbox-ellipses-outline"></ion-icon>
        </span>
        <span class="title">Messages</span>
        </a>
      </li>
      <li class="sidebar__item" v-on="{mouseover: handleHover, mouseleave: handleLeave}" id="item-4" ref="li-4">
        <a href="#">
        <span class="icon">
          <ion-icon name="settings-outline"></ion-icon>
        </span>
        <span class="title">Settings</span>
        </a>
      </li>
      <li class="sidebar__item" v-on="{mouseover: handleHover, mouseleave: handleLeave}" id="item-5" ref="li-5">
        <a href="#">
        <span class="icon">
          <ion-icon name="help-circle-outline"></ion-icon>
        </span>
        <span class="title">Help</span>
        </a>
      </li>
      <li class="sidebar__item" v-on="{mouseover: handleHover, mouseleave: handleLeave}" id="item-6" ref="li-6">
        <a href="#">
        <span class="icon">
          <ion-icon name="skull-outline"></ion-icon>
        </span>
        <span class="title">Privacy</span>
        </a>
      </li>
      <li class="sidebar__item" v-on="{mouseover: handleHover, mouseleave: handleLeave}" id="item-7" ref="li-7">
        <a href="#">
        <span class="icon">
          <ion-icon name="log-out-outline"></ion-icon>
        </span>
        <span class="title">Signout</span>
        </a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  methods: {
    handleHover(e) {
      let refs = Object.values(this.$refs);
      let currentEl = refs.find(r=> e.path.includes(r));
      refs.forEach(el=> el.classList.remove('active'));
      currentEl.classList.add('active');  
    },
    handleLeave() {
      Object.values(this.$refs).forEach(el=> el.classList.remove('active'));
    }
  }
}
</script>


<style scoped>
  .sidebar {
    width: 60px;
    margin-top: 10px;
    min-height: 550px;
    position: fixed;
    top: 60px;
    left: 10px;
    background: #2B343B;

    box-shadow: 10px 0 0 #4187f6;
    border-left: 10px solid #2B343B;
    overflow-x: hidden;
    position: relative;

    transition: width .6s cubic-bezier(.63,-0.01,.41,1.04);

  }

  .sidebar:hover {
    width: 300px;
  }

  .sidebar ul {
    position: absolute;
    top: 20px;
    left: 0;
    padding-left: 5px;
    width: 100%;
  }

  .sidebar ul .sidebar__item {
    position: relative;
    width: 100%;
    list-style: none;
    border-top-left-radius: 10px;
    border-bottom-left-radius: 10px;

    margin-top: 10px;
    transition: color .4s ease;
  }

  .sidebar ul .sidebar__item:hover a .title {
    transform: translateX(-5px);
  }

  .sidebar ul .sidebar__item.active {
    background: #4187f6;
    color: #aec2e3;
  }

  .sidebar ul .sidebar__item.active a::before {
    content: "";
    position: absolute;
    top: -30px;
    right: 5px;
    background: #2B343B;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    box-shadow: 15px 15px 0 #4187f6;
  }
  .sidebar ul .sidebar__item.active a::after {
    content: "";
    position: absolute;
    bottom: -30px;
    right: 5px;
    background: #2B343B;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    box-shadow: 15px -15px 0 #4187f6;

  }

  .sidebar ul .sidebar__item a {
    width: 100%;
    position: relative;
    display: block;
    display: flex;
    text-decoration: none;
    color: #fff;
  }
  .sidebar ul .sidebar__item a .icon {
    position: relative;
    min-width: 60px;
    height: 60px;
    line-height: 70px;
    text-align: center;
  }
  .sidebar ul .sidebar__item a .icon ion-icon {
    font-size: 1.5em;
    z-index: 1;
  }
  .sidebar ul .sidebar__item a .title {
    display: block;
    line-height: 60px;
    height: 60px;
    padding-left: 10px;

    transition: all .4s ease;
  }

</style>
