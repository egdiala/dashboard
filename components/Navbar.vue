<template>
<div>
  <nav class="navbar flex">
    <div class="container mx-auto lg:py-4 lg:px-8 pl-4 py-4 pr-2 flex items-center justify-between">
      <div class="flex items-center space-x-4">
        <img src="./../static/Logo.png" alt="UntitledUI" class="lg:h-8 w-auto">
        <div class="lg:flex hidden items-center space-x-1">
          <Button v-for="(link, l) in navLinks" :key="l" :label="link.title" :to="link.path" text></Button>
        </div>
      </div>
      <div class="lg:flex hidden items-center space-x-4">
        <Button label="Upgrade now" icon="zap" outlined></Button>
        <div class="flex items-center space-x-1">
          <Button icon="settings" iconbutton></Button>
          <Button icon="bell" iconbutton></Button>
        </div>
        <img src="./../static/Avatar.png" alt="User" class="lg:h-8 rounded-full">
      </div>
      <Icon icon="menu" class="lg:hidden flex"></Icon>
    </div>
  </nav>
  <header class="navbar lg:flex hidden">
    <div class="container mx-auto lg:py-2.5 lg:px-8 pl-4 py-4 pr-2 flex justify-between">
      <div class="flex items-center space-x-1">
        <Button v-for="(sub, s) in subLinks" :key="s" :label="sub.title" :to="sub.path" text></Button>
      </div>
      <div class="flex items-center w-3/12">
        <Input icon="search" placeholder="Search"></Input>
      </div>
    </div>
  </header>
</div>
</template>

<script>
import './navbar.css';
import Button from './Button.vue';
import Input from './Input.vue';
import Icon from './Icon.vue';

export default {
    name: "BaseNavbar",
    components: { Button, Input, Icon },
    data() {
      return {
        navLinks: [
          {
            title: 'Home',
            path: '/home'
          },
          {
            title: 'Dashboard',
            path: '/'
          },
          {
            title: 'Projects',
            path: '/projects'
          },
          {
            title: 'Tasks',
            path: '/tasks'
          },
          {
            title: 'Reporting',
            path: '/report'
          },
          {
            title: 'Users',
            path: '/users'
          },
        ],
        subLinks: [
          {
            title: 'Overview',
            path: '/'
          },
          {
            title: 'Notifications',
            path: '/notification'
          },
          {
            title: 'Analytics',
            path: '/projects'
          },
          {
            title: 'Saved reports',
            path: '/tasks'
          },
          {
            title: 'Trade History',
            path: '/report'
          },
          {
            title: 'User reports',
            path: '/users'
          },
        ],
      }
    },
}
</script>