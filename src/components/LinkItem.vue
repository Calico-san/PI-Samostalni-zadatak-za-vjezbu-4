<script setup>
    const props = defineProps(["link", "active"]);
    const emit = defineEmits(["update:active"]);

    function klikniLink() {
        emit("update:active", props.link.name);
    }
</script>


<template>
  <div class="text-sm z-10 relative transition" @click="klikniLink" :class="[props.link.name == props.active ? 'underline text-purple-100' : 'cursor-pointer text-indigo-300 text-sm hover:text-indigo-200 hover:scale-105',
  props.link.active ? '' : 'text-indigo-500/50 text-sm pointer-events-none font line-through']">
    {{ props.link.name }}
    <b v-if="props.link.name == props.active" class="text-purple-400 -z-[5] absolute -left-0.5 blur-sm">
      {{ props.link.name }}
    </b>
  </div>
</template>