<template>
  <!-- NAVBAR -->
  <NavbarVue />

  <!-- CAROUSEL -->
  <CarouselVue />
  <br /><br />
  <!-- ICON LEFT SIDE -->
  <div class="row g-0">
    <div class="col-md-3">
      <div class="card mx-5 my-3" style="width: 60%; background-color: #fbf2bf">
        <div class="container">
          <ul class="list-group list-group-flush">
            <li class="list-group-item" style="background-color: #fbf2bf">
            <img class="img-1" src="../src/assets/Rectangle13.svg">
            <img class="img-2" src="../src/assets/Vector.svg" style="background-color:#59cfd7">
            </li>
          </ul>
        </div>
      </div>
    </div>

    <!-- CARTS DATA -->
    <div class="col-md-9">
      <div class="container">
        <div class="card mt-3" style="width: 60%">
          <div class="row g-1">
            <div class="col-md-4">
              <img
                src="../src/assets/Rectangle4.svg"
                class="img-fluid"
                style="width: 100%; height: 100%"
              />
            </div>
            <div class="col-md-8">
              <div class="card-body">
                <h5 class="card-title">Udang Mentega</h5>
                <p class="card-text">
                  Rp. 35.000
                  <br />
                  <span class="badge bg-info" style="backgorund-color: #59cfd7"
                    >+</span
                  >
                  <span class="badge bg-light text-dark">1</span>
                  <span class="badge bg-info" style="backgorund-color: #59cfd7"
                    >-</span
                  >
                </p>
              </div>
            </div>
          </div>
        </div>

        <!-- CHECKOUT BUTTON -->
        <div class="d-grid gap-1 col-8">
          <button class="btn btn-danger" type="button">CHECKOUT</button>
          <p>Silahkan Lakukan Pembayaran Dengan Menyebutkan Username Anda !</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import NavbarVue from "./components/NavbarVue";
import Axios from "axios";
import CarouselVue from "./components/CarouselVue.vue";

const todoUrl = "http://localhost:3500/todo";
export default {
  data() {
    return {
      todoList: [],
      todoItem: {},
      editMode: false,
    };
  },
  components: {
    NavbarVue: NavbarVue,
    CarouselVue: CarouselVue,
  },
  methods: {
    handleEdit(id) {
      this.editMode = true;
      this.todoItem = this.todoList.find((item) => item.id == id);
    },
    handleCancel() {
      this.editMode = false;
      this.todoItem = "";
    },
    async handleToDoItem() {
      const id = this.todoItem.id;
      if (this.editMode) {
        await Axios.put(`${todoUrl}/${id}`, this.todoItem);
        this.editMode = false;
        this.todoItem.content = "";
      } else {
        await Axios.post(todoUrl, this.todoItem);
        this.todoItem.content = "";
      }
      Axios.get(todoUrl).then((response) => (this.todoList = response.data));
    },
    async handleDelete(id) {
      await Axios.delete(`${todoUrl}/${id}`);
      Axios.get(todoUrl).then((response) => (this.todoList = response.data));
    },
  },
  created() {
    Axios.get(todoUrl).then((response) => (this.todoList = response.data));
  },
};
</script>

<style scoped>
.card {
  background: #fafafa;
}
.card-title,
.card-text {
  color: #3a556a;
}

span {
  margin: 8px 5px 0px 5px;
  font-weight: bold;
  font-size: 1rem;
  color: #3a556a;
  background-color: #59cfd7;
}

.d-grid {
  margin-top: 20px;
}

h5 {
  margin-bottom: 0px;
}
ul {
  width: 60%;
  background-color: #fbf2bf;
}
.img-1 {
  position: relative;
}

.img-2 {
  position: relative;
  z-index: 1;
  /* left: -25px; */
  right:28px;
}
</style>


