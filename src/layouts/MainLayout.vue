<template>
    <q-layout view="lHr lpR lfr">
        <q-header class="bg-primary text-black" height-hint="98">
            <q-toolbar>
                <q-toolbar-title>
                    <img class="custom-logo GPLAY__logo" src="https://cdn.quasar.dev/img/layout-gallery/logo-google-play.png">
                </q-toolbar-title>
                <q-tabs align="left" class="q-mr-md"> <!-- Add class q-mr-md to add margin to the right -->
                    <q-route-tab @click="scrollToSection('games')" label="Games" />
                    <q-route-tab @click="scrollToSection('apps')" label="Apps" />
                    <q-route-tab @click="scrollToSection('movies')" label="Movies" />
                    <q-route-tab @click="scrollToSection('books')" label="Books" />
                    <q-route-tab @click="scrollToSection('children')" label="Children" />
                </q-tabs>
            </q-toolbar>
        </q-header>

        <q-page-container>
            <router-view />
        </q-page-container>

        <q-footer class="bg-primary text-black">
            <q-toolbar>
                <q-toolbar-title>
                    Copyright © Google. All rights reserved.
                </q-toolbar-title>
            </q-toolbar>
        </q-footer>
    </q-layout>
</template>

<style>
.q-toolbar {
    padding: 0px !important;
}

.q-toolbar__title:first-child {
    padding-left: 32px !important;
}

.q-tab {
    padding: 0 20px !important;
    min-height: 75px !important;
}

.custom-logo {
    position: relative;
    top: 4px;
    width: 180px; /* You can adjust the width as per your requirement */
    height: auto; /* To maintain aspect ratio */
}

.q-tabs {
    flex-grow: 4; /* To occupy remaining space */
}

/* Add this CSS to make the tab labels lowercase */
.q-tab-label {
    text-transform: lowercase;
}
</style>

<script setup>
    const scrollToSection = (sectionId) => {
        const section = document.getElementById(sectionId);
        if (section) {
            const yOffset = -50; // Adjust this value as needed
            const y = section.getBoundingClientRect().top + window.pageYOffset + yOffset;
            window.scrollTo({ top: y, behavior: 'smooth' });
        }
    };
</script>
