<template>
  <div>
    <div class="row align-items-start">
      <h2>Student List</h2>
    </div>
    <div class="row">
      <div class="col">
        <button type="button" class="btn btn-outline-primary" @click="showAddingDialog()">
          Add one
        </button>
      </div>
      <div class="col"></div>
      <div class="col"></div>
    </div>
    <div class="row">
      <br />
    </div>
    <div class="row">
      <table class="table table-bordered border-primary">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Nick Name</th>
            <th scope="col">Age</th>
            <th scope="col">School</th>
            <th scope="col">Favourite</th>
            <th scope="col">Home</th>
            <th scope="col">Action</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="item in itemList" :key="item.id">
            <th scope="row">{{ item.id }}</th>
            <td>{{ item.nickName }}</td>
            <td>{{ item.age }}</td>
            <td>{{ item.school }}</td>
            <td>{{ item.favourite }}</td>
            <td>{{ item.home }}</td>
            <td>
              <b-dropdown id="dropdown-1" text="Modify" variant="outline-warning" class="m-2">
                <b-dropdown-item @click="update(item)">Update</b-dropdown-item>
                <b-dropdown-item @click="remove(item)">Remove</b-dropdown-item>
              </b-dropdown>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    <div>
      <the-adding-dialog ref="addingDialog"></the-adding-dialog>
    </div>
    <div>
      <the-adding-dialog ref="updateDialong"></the-adding-dialog>
    </div>
  </div>

</template>

<script>
import TheAddingDialog from "./TheAddingDialog.vue";
export default {
  components: {
    TheAddingDialog,
  },
  props: {
    itemList: {
      type: Array,
      required: true,
    },
  },
  methods: {
    showAddingDialog() {
      this.$refs.addingDialog.show();
    },
    update(item) {
      this.$refs.updateDialong.fillValuesIntoForm(item);
      this.$refs.updateDialong.show();
    },
    remove(item) {
      this.selectedItem = item;
      alert('remove()' + this.selectedItem.id);
    }
  },
};
</script>
<style>
</style>