<template>

  <div>
    <b-container>
      <b-card>
        <template #header>
          <h6 class="mb-0">{{ $t('newBlockEntry.overallTitleLabel') }}</h6>
        </template>

        <b-container>

        <b-form-row>
          <b-col sm="2">
            <label>{{ $t('newBlockEntry.titleLabel') }}</label>
          </b-col>
          <b-col sm="10">
            <b-form-input
              id="form-input-title"
              type="text"
              v-model="title"
              :placeholder="$t('newBlockEntry.titlePlaceholder')">
            </b-form-input>
          </b-col>
        </b-form-row>

        <b-form-row class="mt-2">
          <b-col sm="2">
            <label>{{ $t('newBlockEntry.contentLabel') }}</label>
          </b-col>
          <b-col sm="10">
            <b-form-textarea
              id="textarea-default"
              v-model="content"
              :placeholder="$t('newBlockEntry.contentPlaceholder')"
              rows="10">
            </b-form-textarea>
          </b-col>
        </b-form-row>

        </b-container>

        <template #footer>
          <b-button
            @click="submit"
            variant="primary">
            {{ $t('newBlockEntry.submitBtnLabel') }}
          </b-button>
        </template>
      </b-card>
    </b-container>
  </div>
</template>

<script>
export default {
  data() {
    return {
      title: '',
      content: '',
    };
  },

  methods: {
    submit() {
      console.log(this.title);
      console.log(this.content);
    },
  },
};
</script>
