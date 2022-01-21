<template>
   <li class="li">
    <p class="p">Марка</p>
    <p class="p">{{beer.brand}}</p>
  </li>
  <li class="li">
    <p class="p">Наименование</p>
    <p class="p">{{beer.name}}</p>
  </li>
   <li class="li"> 
    <p class="p">Стиль</p>
    <p class="p">{{beer.style}}</p>
  </li>
   <li class="li">
    <p class="p">Хмель</p>
    <p class="p">{{beer.hop}}</p>
  </li>
   <li class="li">
    <p class="p">Дрожжи</p>
    <p class="p">{{beer.yeast}}</p>
  </li>
  <li class="li">
    <p class="p">Солод</p>
    <p class="p">{{beer.malts}}</p>
  </li>
  <li class="li">
    <p class="p">Крепость</p>
    <p class="p">{{beer.alcohol}}</p>
  </li>
</template>

<script>
export default {
  props: {
    beer: {
      type: Object,
      required: true
    }
  }
}
</script>

<style>
.li {
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid rgba(0, 0, 0, 0.7);
  padding-bottom: 10px;
}

.li:last-of-type {
  margin-bottom: 100px;
}

.p {
  margin: 0;
  font-size: 20px;
  font-weight: 500;
  width: 50%;

}

@media screen and (max-width: 450px) {
  .p {
    font-size: 15px;
    padding: 0 10px;
  }
}

</style>


