<template>
    <text :style="style"><slot></slot></text>
</template>
<script>
    var domModule = weex.requireModule('dom')
    export default {
        name: 'v-icon',
        props: {
            size: {
                type: String,
                default: '34px'
            },
            color: {
                type: String,
                default: '#667180'
            }
        },
        computed: {
            style () {
                return {
                    fontFamily: 'iconfont',
                    color: this.color,
                    fontSize: `${this.size}px`
                }
            }
        },
        created () {
            domModule.addRule('fontFace', {
                'fontFamily': 'iconfont',
                'src': "url('//at.alicdn.com/t/font_gzccnevsgs3jtt9.ttf')"
            })
        }
    }
</script>