<template>
    <li class="nav__list__li" v-for="link in links" :key="link.id">
        <router-link :to="link.routerTo" style="text-decoration: none; color: white">
            <div :id="link.id"
                 @mouseover="link.active = true"
                 @mouseleave="link.active = false"
                 :style="{
                 display: 'flex',
                 flexDirection: 'row',
                 alignItems: 'center',
                 justifyContent: 'center',
                 marginRight: '20px',
                 cursor: 'pointer'
             }"
            >
                <i class="fa" v-if="link.active">
                    <img :src="link.imgGif"/>
                </i>
                <i class="fa" v-else>
                    <img :src="link.imgStatic"/>
                </i>
                <span>
                    {{link.title}}
            </span>
            </div>
        </router-link>

    </li>
</template>

<script>
    export default {
        name: "my-li",
        props: {
            links: {
                type: Array,
                required: true
            }
        },
        data() {
            return {}
        },

    }
</script>

<style scoped>
    .nav__list__li {
        position: relative;
        list-style: none;
        font-size: 22px;
        font-family: "Arial Black";
    }

    .fa > img {
        width: 50px;
    }
</style>