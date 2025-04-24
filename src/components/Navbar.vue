<script setup>
    import LinkItem from "@/components/LinkItem.vue";

    const props = defineProps(["links", "active"]);
    const emit = defineEmits(["update:active"]);

    function aktivniLink(noviLink) {
        emit("update:active", noviLink);
    }
</script>


<template>
    <nav
        class="sticky top-0 w-full flex gap-4 flex-wrap items-center justify-around bg-[#070F2B]/25 backdrop-blur-sm py-2 px-8 rounded-lg">
        <LinkItem v-for="link in props.links" :link="link" :active="props.active" @update:active="aktivniLink" />
    </nav>
</template>