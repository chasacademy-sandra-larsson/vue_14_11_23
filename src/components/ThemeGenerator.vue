<template>
    <div>
        <button @click="generateTheme">Generate Theme</button>
        <div class="colors">
            <div v-for="(color, index) in currentTheme" :key="index" :style="{backgroundColor: color}" class="color">
                {{ color }}
            </div>
        </div>
        <button @click="saveToFavorites">Save to favorites</button>
    </div>
    <p>{{ favoriteCount }}</p>
</template>

<script lang="ts">
    import { useThemeStore } from '@/stores/themeStore';
    import { computed } from 'vue'

    export default {
        setup() {

        const themeStore = useThemeStore();

        const currentTheme = computed(() => themeStore.currentTheme)

        const favoriteCount = computed(() => themeStore.favoritesCount)


        const generateTheme = () => {
            themeStore.generateTheme()
         
        }

        const saveToFavorites = () => {
            themeStore.saveToFavorites()
            console.log("save to favs")
        }

            return { currentTheme,  favoriteCount, generateTheme, saveToFavorites};
        }
        
    }
</script>

<style scoped>

.colors {
    display: flex;
    margin-bottom: 20px;
}

.color {
    color: #fff;
    width: 100px;
    height: 100px;
    margin: 5px;
}

</style>