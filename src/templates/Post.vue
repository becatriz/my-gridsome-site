<template>
  <BlogLayout>
    <div class="markdown-body">
      <h1>{{ $page.post.title }}</h1>
      <img :src="$page.post.featuredImage" alt="blog" />
      <div v-html="$page.post.content" />
    </div>
  </BlogLayout>
</template>

<page-query>
query Post ($id: ID!) {
  post: post (id: $id) {
    title
    content
    featuredImage
  }
}
</page-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.$page.post.title,
    };
  },
};
</script>
