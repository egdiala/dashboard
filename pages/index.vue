<template>
  <Main class="space-y-8 lg:pb-24 pb-12">
    <section>
      <div class="container mx-auto lg:px-8 px-4">
        <div class="flex lg:flex-row lg:space-x-4 flex-col space-y-4 justify-between lg:items-start">
          <div class="flex-col space-y-1 lg:grow">
            <h1 class="text-gray-900 font-medium lg:text-3xl text-2xl">Welcome back, Olivia</h1>
            <p class="text-gray-500 font-normal text-base">Track, manage and forecast your customers and orders.</p>
          </div>
          <div class="flex space-x-3">
            <Button icon="upload-cloud" label="Import" outlined/>
            <Button icon="plus" label="Add" regular/>
          </div>
        </div>
      </div>
    </section>
    <section>
      <div class="container mx-auto lg:px-8 px-4">
        <div class="grid lg:grid-cols-3 lg:grid-rows-none grid-cols-none grid-rows-3 gap-6">
          <div v-for="(card, c) in cards" :key="c" class="border border-[#EAECF0] shadow rounded-lg p-6 space-y-6">
            <div class="flex items-center space-x-2">
              <h5 class="text-gray-900 font-medium text-base grow">{{ card.title }}</h5>
              <Icon icon="more-vertical" class="text-gray-500"></Icon>
            </div>
            <div class="flex space-x-4 items-center">
              <div class="flex-col space-y-4 grow">
                <h3 class="text-gray-900 font-semibold lg:text-4xl text-3xl">{{ card.amount }}</h3>
                <div class="flex space-x-2 items-center">
                  <div v-if="card.percent > 10" class="flex space-x-1 items-center"><Icon icon="arrow-up" class="text-green-400"></Icon> <span class="text-green-700 font-medium text-sm">{{ card.percent }}%</span></div>
                  <div v-else class="flex space-x-1 items-center"><Icon icon="arrow-down" class="text-red-400"></Icon> <span class="text-red-700 font-medium text-sm">{{ card.percent }}%</span></div>
                  <span class="text-gray-500 font-medium text-sm">vs last month</span>
                </div>
              </div>
              <svg v-if="card.percent > 10" width="131" height="66" viewBox="0 0 131 66" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M129.333 1C108.537 2.73299 107.25 44.2218 86.6667 49C69.6936 52.9402 61.0989 30.5738 44 33C25.4537 35.6316 19.5189 58.9382 1.33337 65H129.333V1Z" fill="#ECFDF3"/>
                <path d="M129.333 1C108.537 2.73299 107.25 44.2218 86.6667 49C69.6936 52.9402 61.0989 30.5738 44 33C25.4537 35.6316 19.5189 58.9382 1.33337 65H129.333V1Z" fill="url(#paint0_linear_1092_11831)"/>
                <path d="M1.33337 65C19.5189 58.9382 25.4537 35.6316 44 33C61.0989 30.5738 69.6936 52.9402 86.6667 49C107.25 44.2218 108.537 2.73299 129.333 1" stroke="#12B76A" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <defs>
                  <linearGradient id="paint0_linear_1092_11831" x1="65.3334" y1="1" x2="65.3334" y2="65" gradientUnits="userSpaceOnUse">
                    <stop offset="0.641167" stop-color="white" stop-opacity="0"/>
                    <stop offset="1" stop-color="white"/>
                  </linearGradient>
                </defs>
              </svg>
              <svg v-else width="131" height="66" viewBox="0 0 131 66" fill="none" xmlns="http://www.w3.org/2000/svg">
                <path d="M1.66669 1C22.4626 2.73299 23.7504 44.2218 44.3334 49C61.3065 52.9402 69.9012 30.5738 87 33C105.546 35.6316 111.481 58.9382 129.667 65H1.66669V1Z" fill="#FEF3F2"/>
                <path d="M1.66669 1C22.4626 2.73299 23.7504 44.2218 44.3334 49C61.3065 52.9402 69.9012 30.5738 87 33C105.546 35.6316 111.481 58.9382 129.667 65H1.66669V1Z" fill="url(#paint0_linear_1092_11813)"/>
                <path d="M129.667 65C111.481 58.9382 105.546 35.6316 87 33C69.9012 30.5738 61.3065 52.9402 44.3334 49C23.7504 44.2218 22.4626 2.73299 1.66668 1" stroke="#F04438" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                <defs>
                  <linearGradient id="paint0_linear_1092_11813" x1="65.6667" y1="1" x2="65.6667" y2="65" gradientUnits="userSpaceOnUse">
                    <stop offset="0.641167" stop-color="white" stop-opacity="0"/>
                    <stop offset="1" stop-color="white"/>
                  </linearGradient>
                </defs>
              </svg>
            </div>
          </div>
        </div>
      </div>
    </section>
    <section>
      <div class="container mx-auto lg:px-8 space-y-6">
        <div class="flex lg:flex-row flex-col lg:space-x-4 px-4 items-center">
          <!-- show on large screen, hide on small screen -->
          <div class="lg:flex space-x-3 items-center grow lg:order-1 hidden">
            <FilterItem>All time</FilterItem>
            <FilterItem>US, AU, +4</FilterItem>
            <Button label="More filters" outlined>
                <svg width="16" height="16" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M5 10H15M2.5 5H17.5M7.5 15H12.5" stroke="#344054" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
            </Button>
          </div>
          <!-- show on small screen, hide on large screen -->
          <div class="flex lg:flex-row flex-col items-center w-full lg:space-y-0 space-y-3 lg:w-3/12 lg:order-2 order-1">
            <Input icon="search" placeholder="Search"></Input>
            <div class="lg:hidden w-full">
              <Button label="Edit filters" outlined class="w-full">
                <svg width="16" height="16" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M5 10H15M2.5 5H17.5M7.5 15H12.5" stroke="#344054" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
              </Button>
            </div>
            <div class="lg:hidden w-full flex items-center space-x-3">
              <Chip>All time</Chip>
              <Chip>US, AU, +4</Chip>
            </div>
          </div>
        </div>
        <!-- Company table -->
        <div class="lg:w-full lg:left-auto lg:relative lg:right-auto lg:overflow-x-hidden left-0 right-0 overflow-x-scroll border border-[#EAECF0] lg:rounded-lg rounded-none lg:shadow-none shadow-md">
          <table class="table-auto w-full">
            <thead>
              <tr class="text-gray-500 text-left text-xs">
                <th class="px-6 py-3">
                  <div class="flex space-x-3 items-center">
                    <Checkbox/>
                    <div class="flex space-x-1 items-center"><span class="font-normal">Company</span><Icon icon="arrow-down"></Icon></div>
                  </div>
                </th>
                <th class="px-6 py-3 font-normal"><span class="inline-block">License use</span></th>
                <th class="px-6 py-3 font-normal">Status</th>
                <th class="px-6 py-3 font-normal">Users</th>
                <th class="px-6 py-3 font-normal">About</th>
                <th></th>
              </tr>
            </thead>
            <tbody class="border-y">
              <tr v-for="(company, n) in companies" :key="n" class="even:bg-white odd:bg-gray-50">
                <td class="px-6 py-3">
                  <div class="flex space-x-3 items-center">
                    <Checkbox/>
                    <div class="w-10 h-10">
                      <img :src="require(`./../static/${company.logo}.png`)">
                    </div>
                    <div class="flex flex-col">
                      <h5 class="text-gray-900 font-medium text-sm">{{ company.name }}</h5>
                      <span class="text-gray-500 font-normal text-sm">{{ company.web }}</span>
                    </div>
                  </div>
                </td>
                <td class="px-6 py-3">
                  <Progress :percentage="company.usage" />
                </td>
                <td class="px-6 py-3">
                  <Badge v-if="company.status == true" class="bg-green-100 text-green-700">Customer</Badge>
                  <Badge v-else class="bg-gray-100 text-gray-700">Churned</Badge>
                </td>
                <td class="px-6 py-3">
                  <div class="flex -space-x-2 items-center">
                    <div v-for="(user, u) in company.users.available" :key="u" class="flex w-9 h-9 rounded-full overflow-x-clip">
                      <img :src="require(`./../static/${user}.png`)">
                    </div>
                    <div v-if="company.users.unavailable" class="flex justify-center w-9 h-9 rounded-full overflow-x-clip border-2 border-white bg-purple-100 text-purple-700 font-medium items-center text-center text-xs">{{ company.users.unavailable }}</div>
                  </div>
                </td>
                <td class="px-6 py-3">
                  <div class="flex flex-col">
                      <h5 class="text-gray-900 font-normal text-sm">{{ company.title }}</h5>
                      <span class="text-gray-500 font-normal text-sm">{{ company.subtitle }}</span>
                  </div>
                </td>
                <td class="w-min p-4">
                  <div class="flex space-x-1 items-center">
                    <Button icon="trash-2" class="text-gray-500" iconbutton></Button>
                    <Button icon="edit-2" class="text-gray-500" iconbutton></Button>
                  </div>
                </td>
              </tr>
            </tbody>
          </table>
          <div class="lg:flex hidden items-center justify-between px-6 pb-4 pt-2.5">
            <div class="flex items-center space-x-3">
              <Button label="Previous" outlined></Button>
              <Button label="Next" outlined></Button>
            </div>
            <span class="text-gray-700 font-medium text-sm">Page 1 of 10</span>
          </div>
        </div>
        <div class="lg:hidden flex flex-col space-y-2 px-4">
          <hr class="bg-gray-200">
          <div class="flex items-center justify-between">
            <Button icon="arrow-left" iconbutton></Button>
              <span class="text-gray-700 font-medium text-sm">Page 1 of 10</span>
            <Button icon="arrow-right" iconbutton></Button>
          </div>
        </div>
      </div>
    </section>
  </Main>
</template>

<script>
import Main from "../components/Main.vue";
import Button from "../components/Button.vue";
import FilterItem from "../components/FilterItem.vue";
import Icon from "../components/Icon.vue";
import Checkbox from "../components/Checkbox.vue";
import Progress from "../components/Progress.vue";
import Badge from "../components/Badge.vue";
import Chip from "../components/Chip.vue";
export default {
    name: "IndexPage",
    components: { Main, Button, FilterItem, Icon, Checkbox, Progress, Badge, Chip },
    data() {
      return {
        cards: [
          {
            title: 'Total customers',
            amount: '2,420',
            percent: 40
          },
          {
            title: 'Members',
            amount: '1,210',
            percent: 10
          },
          {
            title: 'Active now',
            amount: '316',
            percent: 20
          }
        ],
        companies: [
          {
            logo: 'Avatarbrand',
            name: 'Catalog',
            web: 'catalogapp.io',
            usage: 75, // in percentage
            status: true,
            users: {
              available: ['Avataruser', 'Avataruser-1', 'Avataruser-2', 'Avataruser-3', 'Avataruser-4'],
              unavailable: '+5'
            },
            title: 'Content curating app',
            subtitle: 'Brings all your news into one place'
          },
          {
            logo: 'Avatarbrand-1',
            name: 'Circooles',
            web: 'getcirooles.com',
            usage: 67, // in percentage
            status: false,
            users: {
              available: ['Avataruser-5', 'Avataruser-6', 'Avataruser-7', 'Avataruser-8', 'Avataruser-9'],
              unavailable: '+8'
            },
            title: 'Design software',
            subtitle: 'Super lightweight design app'
          },
          {
            logo: 'Avatarbrand-2',
            name: 'Command+R',
            web: 'cmdr.ai',
            usage: 40, // in percentage
            status: true,
            users: {
              available: ['Avataruser-9', 'Avataruser-10', 'Avataruser-11', 'Avataruser-8', 'Avataruser-12'],
              unavailable: '+2'
            },
            title: 'Data prediction',
            subtitle: 'AI and machine learning data'
          },
          {
            logo: 'Avatarbrand-3',
            name: 'Hourglass',
            web: 'hourglass.app',
            usage: 83, // in percentage
            status: true,
            users: {
              available: ['Avataruser-4', 'Avataruser-1', 'Avataruser-5', 'Avataruser-6', 'Avataruser-10'],
            },
            title: 'Productivity app',
            subtitle: 'Time management and productivity'
          },
          {
            logo: 'Avatarbrand-4',
            name: 'Layers',
            web: 'getlayers.io',
            usage: 32, // in percentage
            status: false,
            users: {
              available: ['Avataruser-2', 'Avataruser-5', 'Avataruser-10', 'Avataruser-8', 'Avataruser-9'],
              unavailable: '+1'
            },
            title: 'Web app integrations',
            subtitle: 'Connect web apps seamlessly'
          },
          {
            logo: 'Avatarbrand-5',
            name: 'Quotient',
            web: 'quotient.co',
            usage: 22, // in percentage
            status: true,
            users: {
              available: ['Avataruser-4', 'Avataruser-2', 'Avataruser-10', 'Avataruser-5', 'Avataruser-11'],
              unavailable: '+6'
            },
            title: 'Sales CRM',
            subtitle: 'Web-based sales doc management'
          },
          {
            logo: 'Avatarbrand-6',
            name: 'Sisyphus',
            web: 'sisyphus.com',
            usage: 49, // in percentage
            status: true,
            users: {
              available: ['Avataruser-6', 'Avataruser-11', 'Avataruser-7', 'Avataruser-10', 'Avataruser-3'],
              unavailable: '+4'
            },
            title: 'Automation and workflow',
            subtitle: 'Time tracking, invoicing and expenses'
          },
        ]
      }
    },
}
</script>

<style>
.table-auto thead tr th div .feather-arrow-down {
    width: 16px;
    height: 16px;
}
</style>