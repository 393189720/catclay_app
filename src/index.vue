<template>
    <div id="app">
        <topHeader></topHeader>
        <text class="title">cccc {{target}}</text>
        <text class="desc">Now, let's use vue to build your weex app.</text>
        <div id="example">
            <p>Original message: "{{ message }}"</p>
            <p>Computed reversed message: "{{ reversedMessage }}"</p>
            <p>Computed reversed message2: "{{ message.split('').reverse().join('') }}"</p>
        </div>
        <div id="demo">{{ fullName }}</div>
        <footer></footer>
    </div>
</template>

<style>
    .wrapper {
        align-items: center;
        margin-top: 120px;
    }

    .title {
        padding-top: 40px;
        padding-bottom: 40px;
        font-size: 48px;
    }

    .logo {
        width: 360px;
        height: 156px;
    }

    .desc {
        padding-top: 20px;
        color: #888;
        font-size: 24px;
    }
</style>

<script>
    import topHeader from './topHeader.vue'
    import footer from './footer.vue'
    export default {
        el: '#app',
        data: {
            target: 'World',
            message: 'Hello44441',
            firstName: 'Foo',
            lastName: 'Bar'
        },
        methods: {
            update: function (e) {
                this.target = 'Weex'
                vm.fullName = 'John 00000'
                console.log('target:', this.target)
            }
        },
        components:{
            topHeader,
            footer
        },
        computed: {
            // 计算属性的 getter
            reversedMessage: function () {
                // `this` 指向 vm 实例
                return Date.now();
            },
            fullName: {
                // getter
                get: function () {
                    return this.firstName + ' ' + this.lastName
                },
                // setter
                set: function (newValue) {
                    var names = newValue.split(' ')
                    this.firstName = names[0]
                    this.lastName = names[names.length - 1]
                }
            }
        }
    }
</script>