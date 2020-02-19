<template>
  <li v-if="upgradePerk == 'true'" class="upgrade-perk">{{ text }}</li>
  <li v-else>{{ text }}</li>
</template>

<script>
export default {
    props: ["text", "upgradePerk"]
}
</script>

<style>
    .upgrade-perk{
        color: pink;
    }
</style>