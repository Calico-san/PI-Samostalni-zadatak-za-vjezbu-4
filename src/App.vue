<script setup>
    import { ref } from 'vue'

    import Header from "@/components/Header.vue"
    import Navbar from "@/components/Navbar.vue"
    import PagePočetna from "@/components/PagePočetna.vue"
    import PageSlika from "@/components/PageSlika.vue"
    import PageGrafika from "@/components/PageGrafika.vue"
    import Footer from "@/components/Footer.vue"

    const links = [
        { name: "POČETNA", active: true },
        { name: "SLIKA", active: true },
        { name: "ZVUK", active: false },
        { name: "GRAFIKA", active: true },
        { name: "MODEL", active: false },
        { name: "VIDEO", active: false }
    ];

    const activeLink = ref("POČETNA");
</script>

<template>
    <div class="fixed w-full h-full flex justify-center poppins text-sm text-indigo-300
        bg-gradient-to-b from-[#1B1A55] via-[#2B428D] to-[#3B39BB]">

        <div style="background-image: url('./src/assets/images/pattern.jpg'); 
            background-size: 200px;" class="fixed w-full h-full bg-repeat opacity-[3%] -z-10"></div>

        <div class="bg-[#535C91]/25 border-x border-[#9290C3]/10 w-[700px] max-w-[700px] shadow-lg
            flex flex-col justify-between px-8 gap-4 overflow-auto">

            <Header />

            <Navbar :links="links" :active="activeLink" @update:active="activeLink = $event" />

            <div v-if="activeLink == 'POČETNA'">
                <PagePočetna />
            </div>

            <div v-if="activeLink == 'SLIKA'">
                <PageSlika />
            </div>

            <div v-if="activeLink == 'GRAFIKA'">
                <PageGrafika />
            </div>

            <Footer />

        </div>
    </div>
</template>