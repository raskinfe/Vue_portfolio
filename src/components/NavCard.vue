<template>
    <div class="navbar">
        <div class="name">
            <h1>{{fullName}}</h1>
        </div>
        <div class="link-items">
            <div v-for="(link, index) in linkContent" :key="index">
                <a :href="link.link">{{link.name}}</a>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'NavCard',
    props: {
        fullName: {
            type: String,
            default () {
                return "Kinfemichael Desse"
            },
        },
        linkContent: {
            type: Object,
        },
    },
}
</script>
<style scoped lang="scss">
.navbar{
    display: flex;
    max-height: 250px;
    background: #333131;
    flex-direction: row;
    gap: 40px;
    padding: 10px 20px;
    width: 100%;
    z-index: 20;
    .name{
        color: rgb(56, 134, 157);
    }
    .link-items {
        display: flex;
        flex-direction: row;
        gap: 36px;
        justify-content: end;
        align-content: end;
        align-items: center;
        right: 0;
        width: 60%;

        a {
            color: white;
            font-size: 1.4rem;

            &:hover {
                color: crimson;
            }
        }
    }
    
}
</style>
