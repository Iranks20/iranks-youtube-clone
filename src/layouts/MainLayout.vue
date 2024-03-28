<template>
  <q-layout view="lHh Lpr lFf">
    <q-header class="bg-white text-black">
      <q-toolbar class="q-gutter-sm">

        <q-btn
          flat
          dense
          round
          icon="menu"
          aria-label="Menu"
          @click="toggleLeftDrawer"
          class="text-black"
        />

        <q-toolbar-title>
          <img src="~assets/youtubelogo.svg" alt="YouTube Logo" style="height: 20px;">
        </q-toolbar-title>
        <div class="search-bar">
          <q-input
            filled
            v-model="search"
            placeholder="Search"
            class="search-input"
            dense
          >
            <template v-slot:append>
              <q-icon name="search" class="cursor-pointer" />
            </template>
          </q-input>
          <q-icon name="mic" class="cursor-pointer-mic" />
        </div>

        <q-space />

        <q-btn flat dense round icon="video_call" aria-label="Create" class="text-black" />
        <q-btn flat dense round icon="apps" aria-label="Apps" class="text-black" />
        <q-btn flat dense round icon="notifications" aria-label="Notifications" class="text-black" />
        
        <q-avatar>
          <img src="~assets/avatar.jpg" alt="User Avatar">
        </q-avatar>

      </q-toolbar>
    </q-header>


    <q-drawer
      v-model="leftDrawerOpen"
      :mini="leftDrawerOpen && miniState"
      show-if-above
      bordered
      width="260"
      class="my-drawer"
      @mouseover="miniState = false"
      @mouseout="miniState = !leftDrawerOpen"
      @click.capture="toggleLeftDrawer"
    >
      <q-list>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon name="home" />
          </q-item-section>
          <q-item-section v-show="!miniState">
            Home
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon name="ondemand_video" />
          </q-item-section>
          <q-item-section v-show="!miniState">
            Shorts
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon name="subscriptions" />
          </q-item-section>
          <q-item-section v-show="!miniState">
            Subscriptions
          </q-item-section>
        </q-item>
        <q-item clickable v-ripple>
          <q-item-section avatar>
            <q-icon name="video_library" />
          </q-item-section>
          <q-item-section v-show="!miniState">
            Library
          </q-item-section>
        </q-item>
        <!-- More items here following the same structure -->
      </q-list>
    </q-drawer>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script setup>
import { ref } from 'vue'
import EssentialLink from 'components/EssentialLink.vue'

defineOptions({
  name: 'MainLayout'
})

const leftDrawerOpen = ref(false)

function toggleLeftDrawer () {
  leftDrawerOpen.value = !leftDrawerOpen.value
}
</script>

<style>
.q-toolbar {
  height: 60px;
}


.search-bar {
  display: flex;
  align-items: center;
  width: 500px;
}

.search-input {
  flex-grow: 1;
  border-radius: 10px;
  
}

.q-input {
  max-width: 590px;
}

.q-btn {
  line-height: 0;
}

.q-avatar img {
  height: 24px;
  width: 24px;
  border-radius: 50%;
}

.cursor-pointer {
  cursor: pointer;
}
.cursor-pointer-mic {
  cursor: pointer;
  font-size: 2em;
}

@media (max-width: 599px) {
  .q-toolbar-title,
  .q-btn {
    display: none;
  }

  .q-input {
    max-width: calc(100vw - 48px);
  }
}
.bg-grey-1 {
  background-color: #f9f9f9;
}

.rounded-borders {
  border-radius: 10px;
}

.q-drawer {
  width: 260px;
}

.q-drawer--mini .q-item-section {
  display: none;
}

.q-drawer--mini .q-item-section.avatar {
  margin-right: 0;
}
</style>
