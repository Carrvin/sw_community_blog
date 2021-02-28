<template>
  <div>
    <BlogPostList :posts=posts />
  </div>
</template>

<script>
import BlogPostList from '@/components/BlogPostList.vue';

export default {
  components: {
    BlogPostList,
  },

  data() {
    return {
      posts: [
        {
          title: 'Post #1 Title',
          content: 'Post #1 Content',
          tags: ['Storefront', 'Administration', 'Inheritance'],
        },
        {
          title: 'Post #2 Title',
          content: 'Der Content des Posts ...',
          tags: ['toll', 'nett', 'schön'],
        },
      ],
    };
  },
};
</script>
