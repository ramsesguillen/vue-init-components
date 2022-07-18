<template>
    <ul>
        <li v-for="(goal) in goals" :key="goal">
            <slot :goal="goal" another-prop="another..."></slot>
        </li>
    </ul>
</template>

<script>
    export default {
        data() {
            return {
                goals: ['Finish the course', 'Learn vue'],
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>