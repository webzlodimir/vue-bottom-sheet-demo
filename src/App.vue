<template>
  <div id="app">
    <div class="container pt-5 pb-5">
      <h1>
        Vue Bottom Sheet
      </h1>
      <div class="mt-3 mb-3">
        <github-button href="https://github.com/webzlodimir/vue-bottom-sheet" data-size="large" data-show-count="true" aria-label="Star webzlodimir/vue-bottom-sheet on GitHub">Star on Github</github-button>
      </div>
      <p>
        A nice clean and touch-friendly bottom sheet component based on <a target="_blank" href="https://vuejs.org/">Vue.js</a> and <a target="_blank" href="https://hammerjs.github.io/">Hammer.js</a>
      </p>
      <h3 class="mb-3">Settings</h3>

      <div class="row">
        <div class="col-sm-4 col-12">
          <div class="form-check form-switch mb-3">
            <input
                class="form-check-input"
                type="checkbox"
                id="flexSwitchCheckChecked"
                v-model="overlay"
                checked
            />
            <label class="form-check-label" for="flexSwitchCheckChecked"
            >Overlay</label
            >
          </div>
          <div class="form-check form-switch mb-3">
            <input
                class="form-check-input"
                type="checkbox"
                id="closeSwitchCheckChecked"
                v-model="clickToClose"
                checked
            />
            <label class="form-check-label" for="closeSwitchCheckChecked"
            >Click outside card to close</label
            >
          </div>
          <div class="form-group mb-3">
            <label for="maxWidthInput" class="form-label">Max width:</label>
            <input
                name="maxWidthInput"
                id="maxWidthInput"
                v-model="maxWidth"
                type="text"
                class="form-control"
            />
          </div>
          <div class="form-group mb-3">
            <label for="maxHeightInput" class="form-label">Max height:</label>
            <input
                name="maxHeightInput"
                id="maxHeightInput"
                v-model="maxHeight"
                type="text"
                class="form-control"
            />
          </div>
        </div>
      </div>
      <button class="btn btn-primary" type="button" @click="open">
        Open bottom sheet
      </button>
      <vue-bottom-sheet
          :max-width="maxWidth"
          :max-height="maxHeight"
          :overlay="overlay"
          :click-to-close="clickToClose"
          ref="myBottomSheet"
      >
        test
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        test
      </vue-bottom-sheet>
    </div>
  </div>
</template>

<script>
import VueBottomSheet from '@webzlodimir/vue-bottom-sheet'
import GithubButton from 'vue-github-button'
export default {
  name: 'App',
  data() {
    return {
      overlay: true,
      maxWidth: '640px',
      maxHeight: '90%',
      clickToClose: true
    };
  },
  components: {
    VueBottomSheet,
    GithubButton
  },
  methods: {
    open() {
      this.$refs.myBottomSheet.open();
    },
    close() {
      this.$refs.myBottomSheet.close();
    }
  }
}
</script>

<style>
.sheet-content {
  padding: 0 20px;
}
</style>
