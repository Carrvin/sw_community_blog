<template>
  <div>
    <BlogPostEdit :post=post @save='onBlogPostEditSave'/>
  </div>
</template>

<script>
import BlogPostEdit from '@/components/BlogPostEdit.vue';

export default {
  components: {
    BlogPostEdit,
  },

  data() {
    return {
      post: {
        title: 'Hallo schöne neue Welt',
        content: 'Der Content des Posts ...',
        tags: ['toll', 'nett', 'schön'],
      },
    };
  },

  methods: {
    onBlogPostEditSave() {
      console.log(this.post.title);
      console.log(this.post.content);
      console.log(this.post.tags);
    },
  },
};
</script>
