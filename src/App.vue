<template>
  <div id="app">
        Num
        <span class="clickMe" @click="showKeyboard1">{{ numVal }}</span>
        <span class="clickMe" @click="showKeyboard2">{{ telVal }}</span>
        <span class="clickMe" @click="showKeyboard3">{{ certIdVal }}</span>
        <span class="clickMe" @click="showKeyboard4">{{ floatVal }}</span>

        <br />
        Char
        <span class="clickMe" @click="showKeyboard5">{{ lowerCharaterVal }}</span>
        <span class="clickMe" @click="showKeyboard6">{{ upperCharaterVal }}</span>
        <span class="clickMe" @click="showKeyboard7">{{ charaterVal }}</span>

        <span class="clickMe" @click="showKeyboard10">{{ charNumVal }}</span>
        <span class="clickMe" @click="showKeyboard9">{{ passwordVal }}</span>
        <span class="clickMe" @click="showKeyboard8">{{ emailVal }}</span>

        <span class="clickMe" @click="showKeyboard11">{{ customVal }}</span>
  </div>
</template>

<script>
import keyboard from './components/keyboard.js'

export default {
name: 'App',
    data() {
        return {
            telVal:'请输入电话号码',
            numVal: '请输入数字',
            certIdVal: '请输入身份证号码',
            floatVal: '请输入数值',

            lowerCharaterVal: '请输入小写字母',
            upperCharaterVal: '请输入大写字母',
            charaterVal: '请输入字母',

            charNumVal: '请输入数字字母',
            passwordVal: '请输入密码',
            emailVal: '请输入邮箱',

            customVal: '请输入自定义字符',
            keyboardParam: {
                // type: 'number',
                // subType: 'float',
                // typeReg: '',
                // numberType: 'numberic',
                // length: '1,8',
                // hasOpe: false,
                // precision: '2',
                // maxValue: '70',
                // minValue: '9',
                // defaultValue: '',
                // theme: '',
                // message: '',
                // onCancel: (res) => {

                // },
                // onConfirm: (v, t) => {
                //     t.keyboardclose(200);
                // }
            }
        }
    },
    methods: {
        showKeyboard1(){
            this.keyboardParam.type = 'number'
            this.keyboardParam.length = '1,8';
            this.keyboardParam.subType = 'number';
            this.keyboardParam.theme = '#e1e1e1';
            this.keyboardParam.onConfirm = (v, t) => {
                this.numVal = v;
                t.keyboardclose(200);
            }
            keyboard(this.keyboardParam);
        },
        showKeyboard2() {
            this.keyboardParam.type = 'number'
            this.keyboardParam.length = '6';
            this.keyboardParam.subType = 'phone';
            this.keyboardParam.theme = '#ff0000';
            this.keyboardParam.onConfirm = (v, t) => {
                this.telVal = v;
                t.keyboardclose(200);
            }
            keyboard(this.keyboardParam);
        },
        showKeyboard3() {
            this.keyboardParam.type = 'number'
            this.keyboardParam.length = '6';
            this.keyboardParam.subType = 'certNo';
            this.keyboardParam.theme = '#ff0000';
            this.keyboardParam.onConfirm = (v, t) => {
                this.certIdVal = v;
                t.keyboardclose(200);
            }
            keyboard(this.keyboardParam);
        },
        showKeyboard4() {
            this.keyboardParam.type = 'number'
            this.keyboardParam.length = '1,6';
            this.keyboardParam.minValue = '20';
            this.keyboardParam.maxValue = '200';
            this.keyboardParam.subType = 'float';
            this.keyboardParam.theme = '#ff0000';
            this.keyboardParam.onConfirm = (v, t) => {
                this.floatVal = v;
                t.keyboardclose(200);
            }
            keyboard(this.keyboardParam);
        },

        showKeyboard5() {
            this.keyboardParam.type = 'character'
            this.keyboardParam.length = '1,6';
            this.keyboardParam.minValue = '20';
            this.keyboardParam.maxValue = '200';
            this.keyboardParam.subType = 'lowerChar';
            this.keyboardParam.theme = '#ff0000';
            this.keyboardParam.onConfirm = (v, t) => {
                this.lowerCharaterVal = v;
                t.keyboardclose(200);
            }
            keyboard(this.keyboardParam);
        },
        showKeyboard6() {
            this.keyboardParam.type = 'character'
            this.keyboardParam.length = '1,6';
            this.keyboardParam.minValue = '20';
            this.keyboardParam.maxValue = '200';
            this.keyboardParam.subType = 'upperChar';
            this.keyboardParam.theme = '#ff0000';
            this.keyboardParam.onConfirm = (v, t) => {
                this.upperCharaterVal = v;
                t.keyboardclose(200);
            }
            keyboard(this.keyboardParam);
        },
        showKeyboard7() {
            this.keyboardParam.type = 'character'
            this.keyboardParam.length = '1,6';
            this.keyboardParam.minValue = '20';
            this.keyboardParam.maxValue = '200';
            this.keyboardParam.subType = 'character';
            this.keyboardParam.theme = '#ff0000';
            this.keyboardParam.onConfirm = (v, t) => {
                this.charaterVal = v;
                t.keyboardclose(200);
            }
            keyboard(this.keyboardParam);
        },

        showKeyboard8() {
            this.keyboardParam.type = 'charNum'
            this.keyboardParam.length = '1,6';
            this.keyboardParam.minValue = '20';
            this.keyboardParam.maxValue = '200';
            this.keyboardParam.subType = 'email';
            this.keyboardParam.theme = '#ff0000';
            this.keyboardParam.onConfirm = (v, t) => {
                this.emailVal = v;
                t.keyboardclose(200);
            }
            keyboard(this.keyboardParam);
        },
        showKeyboard9() {
            this.keyboardParam.type = 'charNum'
            this.keyboardParam.length = '1,6';
            this.keyboardParam.minValue = '20';
            this.keyboardParam.maxValue = '200';
            this.keyboardParam.subType = 'password';
            this.keyboardParam.theme = '#ff0000';
            this.keyboardParam.onConfirm = (v, t) => {
                this.passwordVal = v;
                t.keyboardclose(200);
            }
            keyboard(this.keyboardParam);
        },

        showKeyboard10() {
            this.keyboardParam.type = 'charNum'
            this.keyboardParam.length = '1,6';
            this.keyboardParam.minValue = '20';
            this.keyboardParam.maxValue = '200';
            this.keyboardParam.subType = 'charNum';
            this.keyboardParam.theme = '#ff0000';
            this.keyboardParam.onConfirm = (v, t) => {
                this.charNumVal = v;
                t.keyboardclose(200);
            }
            keyboard(this.keyboardParam);
        },


        showKeyboard11() {
            this.keyboardParam.type = 'charNum'
            this.keyboardParam.length = '1,6';
            this.keyboardParam.minValue = '20';
            this.keyboardParam.maxValue = '200';
            this.keyboardParam.subType = 'custom';
            this.keyboardParam.theme = '#ff0000';
            this.keyboardParam.onConfirm = (v, t) => {
                this.lowerCharaterVal = v;
                t.keyboardclose(200);
            }
            keyboard(this.keyboardParam);
        },

    }
}
</script>

<style>
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
b, u, i, center,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td,
article, aside, canvas, details, embed, 
figure, figcaption, footer, header, hgroup, 
menu, nav, output, ruby, section, summary,
time, mark, audio, video, input {
	margin: 0;
	padding: 0;
    border: 0;
    outline:0;
    font-family: "PingFangSC","微软雅黑","SimSun","宋体";
	/* vertical-align:baseline; */
    background:transparent;
    box-sizing: border-box;
    -webkit-box-sizing: border-box;
    -moz-box-sizing: border-box;
    -ms-box-sizing: border-box;
    -o-box-sizing: border-box;
}
html {
    font-size: 20px;
}
body,html {
    width: 100%;
    height: 100%;
}
h1,h2,h3,h4,h5,h6 {
    font-size: 1.2rem;
    font-weight: normal;
}
ul,li {
    list-style: none;
}

.hidden {
    display: none;
}
a {
    text-decoration: none;
}

.clickMe {
    display: block;
    width: 180px;
    height: 28px;
    padding: 0 8px;
    font-size: 14px;
    line-height: 28px;
    color: #333;
    border: 1px #333 solid;
}
</style>
