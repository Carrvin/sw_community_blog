<template>
  <div>
    <b-container>
      <b-row v-for="post in posts" :key="post.title">
        <b-col sm="12">
          <b-card :title=post.title class="mb-2">

            <b-card-text>
              {{ post.content }}
            </b-card-text>

            <b-container class="bv-example-row">
              <b-row align-h="start">
                <b-col v-for="tag in post.tags" :key="tag" class="col-auto">
                  <b-badge pill variant="secondary">{{ tag }}</b-badge>
                </b-col>
              </b-row>
            </b-container>

          </b-card>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
export default {
  props: {
    posts: {
      type: Array,
      required: true,
    },
  },
};
</script>
