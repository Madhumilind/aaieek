<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        yes
      </h1>
      <div class="links">
        <a
          href="https://github.com/Madhumilind"
          target="_blank"
          rel="noopener noreferrer"
          class="button--grey"
        >
          GitHub
        </a>
      </div>
    </div>
    <h1 class="title">Top Links</h1>
      <div>
        <news-item
          v-for="post in topPosts"
          :key="post.id"
          :item="post"
          @upvote="onUpvote(post)"
        />
      </div>
  </div>
</template>

<script>
import { mapActions, mapGetters } from 'vuex'
import postsPerimeter from '~/perimeters/postsPerimeter'
import NewsItem from '~/components/NewsItem'
export default {
  components: { NewsItem },
  fetch({ store }) {
    store.dispatch('getPosts')
  },
  computed: mapGetters(['topPosts']),
  methods: {
    ...mapActions(['upvotePost']),
    onUpvote(post) {
      if (this.$isAllowed('upvote', post)) {
        this.upvotePost({ postId: post.id })
      }
    }
  },
  perimeters: [postsPerimeter]
}
</script>

<!--<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style> -->
