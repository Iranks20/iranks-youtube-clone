<template>
  <q-page padding>
    <div class="q-gutter-md" style="max-width: 1200px; margin: auto;">
      <div class="row q-col-gutter-md">
        <!-- Repeat this column for each image -->
        <div class="col-xs-12 col-sm-6 col-md-3" v-for="(image, index) in images" :key="index">
          <div class="video-thumbnail">
            <img :src="image.src" :alt="image.alt" class="thumbnail-img" />
            <div class="video-info">
              <div class="video-title">{{ image.title }}</div>
              <div class="channel-name">{{ image.channel }}</div>
              <div class="views-time">{{ image.views }} views • {{ image.daysAgo }} days ago</div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </q-page>
</template>

<script setup>
defineOptions({
  name: 'IndexPage'
});

const images = [
  {
    src: 'https://cdn.quasar.dev/img/parallax1.jpg',
    alt: 'Description for Image 1',
    title: 'Title for Image 1',
    channel: 'Channel Name 1',
    views: '20K',
    daysAgo: '13'
  },
  {
    src: 'https://cdn.quasar.dev/img/parallax2.jpg',
    alt: 'Description for Image 2',
    title: 'Title for Image 2',
    channel: 'Channel Name 2',
    views: '1.4K',
    daysAgo: '11'
  },
  {
    src: 'https://cdn.quasar.dev/img/mountains.jpg',
    alt: 'Description for Image 3',
    title: 'Title for Image 3',
    channel: 'Channel Name 3',
    views: '228K',
    daysAgo: '30'
  },
  {
    src: 'https://cdn.quasar.dev/img/quasar.jpg',
    alt: 'Description for Image 4',
    title: 'Title for Image 4',
    channel: 'Channel Name 4',
    views: '15K',
    daysAgo: '8'
  },
  {
    src: 'https://cdn.quasar.dev/img/parallax1.jpg',
    alt: 'Description for Image 1',
    title: 'Title for Image 1',
    channel: 'Channel Name 1',
    views: '20K',
    daysAgo: '13'
  },
  {
    src: 'https://cdn.quasar.dev/img/parallax2.jpg',
    alt: 'Description for Image 2',
    title: 'Title for Image 2',
    channel: 'Channel Name 2',
    views: '1.4K',
    daysAgo: '11'
  },
  {
    src: 'https://cdn.quasar.dev/img/mountains.jpg',
    alt: 'Description for Image 3',
    title: 'Title for Image 3',
    channel: 'Channel Name 3',
    views: '228K',
    daysAgo: '30'
  },
  {
    src: 'https://cdn.quasar.dev/img/quasar.jpg',
    alt: 'Description for Image 4',
    title: 'Title for Image 4',
    channel: 'Channel Name 4',
    views: '15K',
    daysAgo: '8'
  }
];
</script>

<style>
.video-thumbnail {
  position: relative;
  cursor: pointer;
}

.thumbnail-img {
  width: 100%;
  aspect-ratio: 16 / 9;
  object-fit: cover;
}

.video-info {
  padding: 8px;
}

.video-title {
  font-weight: bold;
}

.channel-name {
  color: #666;
  font-size: 0.85em;
}

.views-time {
  color: #999;
  font-size: 0.75em;
}

@media (max-width: 599px) {
  .thumbnail-img {
    aspect-ratio: unset;
  }
}
</style>
