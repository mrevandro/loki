<template>
    <div class="az-search">
        <div class="input_search">
            <input class="input-text" placeholder="Informe o código" v-model="inputText" @focus="onFocus()" @blur="onBlur()"/>
        </div>

        <a class="btn-search">
            <v-icon small>search</v-icon>
        </a>
    </div>
</template>
<script>
    export default {
        data() {
            return {
                inputText: null,
                size: '300px'
            }
        },
        methods: {
            onBlur() {
                document.getElementsByClassName('input_search')[0].classList.remove('extended')
            },
            onFocus() {
                document.getElementsByClassName('input_search')[0].classList.add('extended')
            }
        }
    }
</script>
<style lang="stylus">
    .az-search
        display: flex
        .input_search
            width: 300px
            background-color: #eee
            border-radius: 20px 0 0 20px
            transition: 0.2s
            .input-text
                height: 30px
                padding: 10px 15px
                width: 100%
                outline: none
                color: #777777

        .extended
            width: 500px
            background-color: #eee
            border-radius: 20px 0 0 20px
            transition: 0.2s
            .input-text
                height: 30px
                padding: 10px 15px
                width: 100%
                outline: none
                color: #777777

        ::placeholder
            /* Chrome, Firefox, Opera, Safari 10.1+ */
            color: #cccccc !important

        :-ms-input-placeholder
            /* Internet Explorer 10-11 */
            color: #cccccc !important

        .btn-search
            margin-right: 10px
            padding: 5px 10px
            background-color: #3a6861
            border-radius: 0 20px 20px 0
            i
                color: rgba(255, 255, 255, 0.8)
                font-size: 13px
                font-weight: bold

            .icon
                color: rgba(255, 255, 255, 0.8)

    .az-search .input_search
        .v-input-group
            margin: 0
            padding: 0 15px

            label
                font-size: 13px
                padding-left: 15px
                top: 0

            &__input input
                font-size: 13px

            &__details
                display: none
</style>