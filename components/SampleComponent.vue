<template lang="html">
    <div>
        <h1>{{ title }}</h1>
         <div class="blue">
            <slot name="named"/>
        </div>
        Hello, I'm {{ name }} 
        <div>
            {{ reverseName }}
        </div>
        <div>
            <button type="button" name="button"@click="plus">
                click times: {{ num }}
            </button>
        </div>
        <div :class="['hide', { seven: num === 7}]">
            click 7times
        </div>
        <div class="slot">
            <slot/>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        title: {
            type: String,
            default: 'Default Title'
        }
    },
    data() {
        return {
            name: 'Tetsuya!!!',
            num: 0
        }
    },
     mounted() {
        console.log('mounted');
    },
    methods: {
        plus() {
            this.num ++
        }
    },
    computed: {
        reverseName() {
            return this.name.split('').reverse().join('');
        },
   
    }
}
</script> 

<style lang="scss" scoped>
    .hide {
        display: none;
        &.seven {
            display: block;
        }
    }
    .slot {
        color: red;
    }
</style>