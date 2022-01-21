<template>
  <div class="container">
    <div class="image-container">
      <img :src="account.avatar" :alt="account.username"/>
    </div>
    <ul class="ul ul_profile2">
      <li class="li li_profile">
        <p class="p">Имя</p>
        <p class="p">{{account.first_name}}</p>
      </li>
      <li class="li li_profile">
        <p class="p">Фамилия</p>
        <p class="p">{{account.last_name}}</p>
      </li>
      <li class="li li_profile">
        <p class="p">Почта</p>
        <p class="p">{{account.email}}</p>
      </li>
      <li class="li li_profile">
        <p class="p">Телефон</p>
        <p class="p">{{account.phone_number}}</p>
      </li>
      <li class="li li_profile">
        <p class="p">Пол</p>
        <p class="p">{{account.gender}}</p>
      </li>
    </ul>
  </div>
  
</template>

<script>
export default {
  props: {
    account: {
      type: Object,
      required: true
    }
  },
}
</script>

<style >
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 30px;
}

.ul_profile {
  width: 90%;
  max-width: 900px;
  justify-content: center;
}

.ul_profile2 {
  max-width: 100%;
  padding: 0;
  height: 100%;
}

.li_profile {
  padding-top: 10px ;
  text-align: left;
}

.li_profile:last-of-type {
  margin-bottom: 0;
}

.p_center {
  width: 100%;
  text-align: center;
}

.image-container {
  padding-left: 5px;
  min-width: 300px;
  position: relative;
}

.image-container img {
  object-fit: contain;
  object-position: center;
  border-radius: 50%;
  width: 100%;
  height: 100%;
  display: flex;
  box-shadow: 8px 0px 2px rgb(143, 143, 143);
  transition: .1s linear;
  animation: scale .2s ease-in-out alternate;
  animation-iteration-count: 4;
}

.image-container img:hover {
  animation: shadow 1s infinite linear;
}

@keyframes scale {
  from {
    transform: scale(1);
  }

  to {
    transform: scale(1.02);
  }
}

@keyframes shadow {
  0% {
    box-shadow: 8px 0px 2px rgb(143, 143, 143);
    transform: skew(0deg);
  }
  25% {
    box-shadow: 0px 8px 2px rgb(143, 143, 143);
    transform: skew(-1deg);

  }
  50% {
    box-shadow: -5px 0px 2px rgb(143, 143, 143);
    transform: skew(-2deg);

  }
  75% {
    box-shadow: 0px -5px 2px rgb(143, 143, 143);
    transform: skew(-1deg);

  }
  100% {
    box-shadow:7px 0px 2px rgb(143, 143, 143);
    transform: skew(0deg);

  }
}

@media screen and (max-width: 800px) {
  .container {
    flex-direction: column;
    gap: 50px;
  }
  .image-container {
    padding-left: 0;
  }

}

@media screen and (max-width: 400px) {
  .ul_profile {
    width: 100%;
  }
  .li_profile {
    text-align: center;
    padding: 10px;
  }

  .image-container {
    width: 70%;
    min-width: 70%;
  }
}
</style>

