<template>
  <div class="about__user">
    <div class="about__title"><h2>Обо мне</h2></div>
<!--    <div class="about__images">-->
<!--      <img src="@/assets/images/user_standart.png" alt="">-->
<!--      <img src="@/assets/images/user_standart.png" alt="">-->
<!--      <img src="@/assets/images/user_standart.png" alt="">-->
<!--    </div>-->
    <div class="about_describtions">
      <h4>Имя Фамилия: </h4><h3>{{ name }}</h3>
      <h4>Почта: </h4><h3>{{ user.email }}</h3>
      <h4>Телефон: </h4><h3>{{ user.phone || 'Не указано' }}</h3>
    </div>
  </div>
</template>

<script>
import {mapGetters} from "vuex";

export default {
  name: "ProfileAbout",
  computed: {
    ...mapGetters({ user: 'user' }),
    name() {
      return this.user.last_name && this.user.first_name
          ? `${this.user.last_name} ${this.user.first_name} ${this.user.middle_name ?? ''}`
          : 'Не указано';
    }
  }
}
</script>

<style scoped>
.about__user {
  display: flex;
  flex-direction: column;

  width: 888px;
}

.about__images {
  width: 105%;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-top: 1%;
}

.about__images > img {
  width: 296px;
  height: 204px;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  margin-top: 1%;
}

.about_describtions {
  margin-top: 2%;
}
</style>