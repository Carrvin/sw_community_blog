<template>
  <div>
    <b-container>
      <b-card>
        <template #header>
          <h6 class="mb-0">{{ $t('blogPost.overallTitleLabel') }}</h6>
        </template>

        <b-container>

          <b-row>
            <b-col sm="3" class="text-left">
              <label>{{ $t('blogPost.titleLabel') }} *</label>
            </b-col>
            <b-col sm="9">
              <b-form-input
                id="form-input-title"
                type="text"
                v-model="post.title"
                :placeholder="$t('blogPost.titlePlaceholder')"
                trim>
              </b-form-input>
            </b-col>
          </b-row>

          <b-row class="mt-2">
            <b-col sm="3" class="text-left">
              <label>{{ $t('blogPost.contentLabel') }} *</label>
            </b-col>
            <b-col sm="9">
              <b-form-textarea
                id="form-input-content"
                v-model="post.content"
                :placeholder="$t('blogPost.contentPlaceholder')"
                rows="10"
                trim>
              </b-form-textarea>
            </b-col>
          </b-row>

          <b-row class="mt-2">
            <b-col sm="3" class="text-left">
              <label>{{ $t('blogPost.tagsLabel') }} *</label>
            </b-col>
            <b-col sm="9">
              <b-form-tags
                id="form-input-tags"
                v-model="post.tags"
                :placeholder="$t('blogPost.tagsPlaceholder')"
                tag-variant="secondary"
                remove-on-delete
                trim>
              </b-form-tags>
            </b-col>
          </b-row>

        </b-container>

        <template #footer>
          <b-alert
            :show="formHasValidationErrors"
            variant="danger">
            {{ $t('blogPost.fieldValidationMessage') }}
          </b-alert>

          <b-button
            @click="onSave"
            variant="primary">
            {{ $t('blogPost.submitBtnLabel') }}
          </b-button>
        </template>
      </b-card>
    </b-container>
  </div>
</template>

<script>
export default {
  props: {
    post: {
      type: Object,
      required: true,
    },
  },

  data() {
    return {
      formSubmitCalled: false,
    };
  },

  computed: {
    formHasValidationErrors() {
      const formFieldsFilled = this.post.title === ''
        || this.post.content === '' || this.post.tags.length === 0;
      return this.formSubmitCalled && formFieldsFilled;
    },
  },

  methods: {
    onSave() {
      this.formSubmitCalled = true;

      this.$emit('save');
    },
  },
};
</script>
