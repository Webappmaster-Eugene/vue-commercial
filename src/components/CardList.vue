<script setup>
import Card from '@/components/Card.vue'

const props = defineProps({
  items: Array
})

const emit = defineEmits(['addToFavorite'])
const onClickFavorite = (item) => {
  emit('addToFavorite', item)
}
</script>

<template>
  <div class="grid grid-cols-4 gap-10 mt-5">
    <Card
      v-for="item in items"
      :key="item.id"
      :id="item.id"
      :title="item.title"
      :price="item.price"
      :img="item.imageUrl"
      :onClickFavorite="() => onClickFavorite(item)"
      :isFavorite="item?.isFavorite && item?.isFavorite === true ? true : false"
    />
  </div>
</template>