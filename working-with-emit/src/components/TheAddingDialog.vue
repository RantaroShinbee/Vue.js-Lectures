<template>
  <b-modal
    role="dialog"
    ref="addingFormDialog"
    title="{context}"
    hide-header-close
    hide-footer
  >
    <div class="modal-body">
      <form>
        <div class="mb-3">
          <label for="nick-name" class="col-form-label">Nick Name:</label>
          <b-form-input
            type="text"
            class="form-control"
            id="nick-name"
            v-model="nickName"
          />
        </div>
        <div class="mb-3">
          <label for="age" class="col-form-label">Age:</label>
          <b-form-input
            type="number"
            class="form-control"
            id="age"
            min="1"
            max="200"
            v-model="age"
          />
        </div>
        <div class="mb-3">
          <label for="school" class="col-form-label">School:</label>
          <b-form-input
            type="text"
            class="form-control"
            id="school"
            v-model="school"
          />
        </div>
        <div class="mb-3">
          <label for="favourite" class="col-form-label">Favourite:</label>
          <b-form-input
            type="text"
            class="form-control"
            id="favourite"
            v-model="favourite"
          />
        </div>
        <div class="mb-3">
          <label for="home" class="col-form-label">Home:</label>
          <b-form-input
            type="text"
            class="form-control"
            id="home"
            v-model="home"
          />
        </div>
      </form>
    </div>
    <div class="modal-footer">
      <button type="submit" class="btn btn-primary" @click="submit()">
        Add
      </button>
      <button
        type="button"
        class="btn btn-secondary"
        data-bs-dismiss="modal"
        @click="hide()"
      >
        Close
      </button>
    </div>
  </b-modal>
</template>
<script>
export default {
  emits: ["add-one-student"],
  data() {
    return {
      nickName: '',
      age: 0,
      school: '',
      favourite: '',
      home: '',
      context: 'Add a New Student',
      action: '',
      isUpdate: false
    };
  },
  methods: {
    show() {
      this.$refs["addingFormDialog"].show();
    },
    hide() {
      this.$refs["addingFormDialog"].hide();
    },
    submit() {
      var studentItem = {
        nickName: this.nickName,
        age: this.age,
        school: this.school,
        favourite: this.favourite,
        home: this.home,
      };
      console.log(studentItem);
      if (!this.isUpdate) {
        this.$parent.$emit("add-one-student", studentItem);
      } else {
        $parent.$emit("add-one-student", studentItem);
      }

      this.resetToDefaultValues();
      this.hide();
    },
    resetToDefaultValues() {
      this.nickName = '';
      this.age = 0;
      this.school = '';
      this.favourite = '';
      this.home = '';
    },
    fillValuesIntoForm(values) {
      this.nickName = values.nickName;
      this.age = values.age;
      this.school = values.school;
      this.favourite = values.favourite;
      this.home = values.home;
      this.context = 'Update a Student';
      this.action = 'Update';
    }
  },
};
</script>
<style></style>