<template>
  <base-card>
  <!--Going into a slot-->
    <form @submit.prevent="saveFormData">
      <div class="form-control">
        <label for="title">Title</label>
        <input ref="titleInput" type="text" id="title" name="title" placeholder="resource title">
      </div>
      <div class="form-control">
        <label for="description">Description</label>
        <textarea ref="descriptionInput" name="description" id="description" rows="3" aria-placeholder="description"></textarea>
      </div>
      <div class="form-control">
        <label for="link">Link</label>
        <input ref="linkInput" type="url" id="link" name="link" placeholder="e.g. https://google.com">
      </div>
      <div>
        <base-button type="submit" mode="active">
          Add Resource
        </base-button>
      </div>
    </form>
  </base-card>
</template>

<script>
import BaseCard from "../UI/BaseCard";
import BaseButton from "../UI/BaseButton";
export default {
  components: {BaseButton, BaseCard},
  methods: {
    saveFormData () {
      const inputTitle = this.$refs.titleInput.value;
      const inputDescription = this.$refs.descriptionInput.value;
      const inputLink = this.$refs.linkInput.value;

      if (inputTitle.trim() === '' || inputDescription.trim() === '' || inputLink.trim() === '') {
        //Show custom dialog

        return;
      }

      //Ensure data gets added to resource list
      this.addResource(inputTitle, inputDescription, inputLink);

      //Clear form
      this.$refs.titleInput.value = '';
      this.$refs.descriptionInput.value = '';
      this.$refs.inputLink.value = '';
    }
  },
  inject: ['addResource']
}
</script>

<style scoped>
/*Remove chromes weird input field outlines*/
input:focus, textarea:focus {
  outline: none;
}

input, textarea {
  border: 0;
  border-bottom: 2px solid #cccccc;
  border-radius:10px;
  box-shadow: 0 0 10px 0 rgba(0,0,0,0.25);
  font-family:inherit;
  font-size: inherit;
  margin: 10px 0; /*Top and bottom margin*/
  padding: 10px;
  width: 100%;
}

#description {
  resize: vertical;
}
</style>