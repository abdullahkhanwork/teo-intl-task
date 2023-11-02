<template>
    <q-layout view="lHh Lpr lFf">
        <q-header elevated class="glossy">
            <q-toolbar>
                <q-btn flat dense round @click="leftDrawerOpen = !leftDrawerOpen" aria-label="Menu" icon="menu" />

                <q-toolbar-title>
                    Quasar App
                </q-toolbar-title>

                <div>Quasar v{{ $q.version }}</div>
            </q-toolbar>
        </q-header>

        <q-drawer v-model="leftDrawerOpen" show-if-above bordered class="bg-blue">
            <q-list>
                <q-item-label header>Essential Links</q-item-label>
                <RouterLink to="/">
                    <q-item clickable>
                        <q-item-section avatar>
                            <q-icon name="home" />
                        </q-item-section>
                        <q-item-section>
                            <q-item-label>Home</q-item-label>
                            <q-item-label caption>View</q-item-label>
                        </q-item-section>
                    </q-item>
                </RouterLink>
                <RouterLink to="/table-view">
                    <q-item clickable>
                        <q-item-section avatar>
                            <q-icon name="people" />
                        </q-item-section>
                        <q-item-section>
                            <q-item-label>Table</q-item-label>
                            <q-item-label caption>View</q-item-label>
                        </q-item-section>
                    </q-item>
                </RouterLink>
            </q-list>
        </q-drawer>

        <q-page-container>
            <RouterView />
        </q-page-container>
    </q-layout>
</template>

<script>
import { ref } from 'vue'
import { RouterLink, RouterView } from 'vue-router'

export default {
    name: 'LayoutDefault',

    setup() {
        return {
            leftDrawerOpen: ref(true)
        }
    }
}
</script>
