<template>
    <div class="card">
        <input class="num" v-model="val" />
        <div class="answer" v-if="ans">{{ans}}</div>
    </div>
    <div>
        <button class="btn success" @click="one">1
        </button>
        <button class="btn success" @click="two">2
        </button>
        <button class="btn success" @click="three">3
        </button>
        <div>
            <button class="btn success" @click="four">4
            </button>
            <button class="btn success" @click="five">5
            </button>
            <button class="btn success" @click="six">6
            </button>
        </div>
        <div>
            <button class="btn success" @click="seven">7
            </button>
            <button class="btn success" @click="eight">8
            </button>
            <button class="btn success" @click="nine">9
            </button>
        </div>
        <div>
            <button class="btn success" @click="clr">C
            </button>
            <button class="btn success" @click="zero">0
            </button>
            <button class="btn success" @click="eql">=
            </button>
        </div>
        <div>
            <button class="btn success" @click="plus">+
            </button>
            <button class="btn success" @click="minus">-
            </button>
            <button class="btn success" @click="multi">x
            </button>
            <div>
                <button class="btn success" @click="divi">/
                </button>
                <button class="btn success" @click="pn">.
                </button>
                <button class="btn success" @click="perc">%
                </button>
            </div>
        </div>
        <br>
    </div>
</template>

<script>

export default {
    name: 'PButton',
    props: {
        title: String
    },
    data() {
        return {
            isClick: 0,
            s: "",
            val: "",
            sign: "",
            ans: 0
        }
    },
    methods: {
        one() {
            if (this.val == '0')
                this.val = '';
            this.val += '1';
            this.s += '1';
            this.isClick = 1;
        },
        two() {
            if (this.val == '0')
                this.val = '';
            this.val += '2';
            this.s += '2';
            this.isClick = 2;
        },
        three() {
            if (this.val == '0')
                this.val = '';
            this.val += '3';
            this.s += '3';
            this.isClick = 3;
        },
        four() {
            if (this.val == '0')
                this.val = '';
            this.val += '4';
            this.s += '4';
            this.isClick = 4;
        },
        five() {
            if (this.val == '0')
                this.val = '';
            this.val += '5';
            this.s += '5';
            this.isClick = 5;
        },
        six() {
            if (this.val == '0')
                this.val = '';
            this.val += '6';
            this.s += '6';
            this.isClick = 6;
        },
        seven() {
            if (this.val == '0')
                this.val = '';
            this.val += '7';
            this.s += '7';
            this.isClick = 7;
        },
        eight() {
            if (this.val == '0')
                this.val = '';
            this.val += '8';
            this.s += '8';
            this.isClick = 8;
        },
        nine() {
            if (this.val == '0')
                this.val = '';
            this.val += '9';
            this.s += '9';
            this.isClick = 9;
        },
        zero() {
            if (this.val == '0')
                this.val = '';
            //this.val = '0';
            this.val += '0';
            this.s += '0';
            this.isClick = 10;
        },
        clr() {
            this.val = '';
            this.sign = '';
            this.isClick = 0;
            this.s = '';
            this.ans = 0;
        },
        plus() {
            this.ans += parseInt(this.val);
            this.s += '+';
            this.isClick = 11;
            this.sign = '+';
            this.val = '0';
            console.log(this.ans);
        },
        minus() {
            if (this.ans)
                this.ans -= parseInt(this.val);
            else if (this.ans == 0)
                this.ans += parseInt(this.val);
            this.isClick = 12;
            this.sign = '-';
            this.s += '-';
            this.val = '0';
            console.log(this.ans);
        },
        multi() {
            if (this.ans) {
                if (this.val == '0')
                    this.val = '1';
                this.ans *= parseInt(this.val);
                this.val = '0';
            }
            else if (this.ans == 0) {
                this.ans = 1;
                this.ans *= parseInt(this.val), this.val = '0';
            }
        },
        divi() {
            if (this.ans == 0) {
                this.ans = parseInt(this.val);
            }
            else {
                this.ans /= parseInt(this.val);
            }
            this.isClick = 14;
            this.val = '0';
        },
        perc() {
            if (this.ans)
                this.ans /= 100;
        },
        eql() {
            this.isClick = 20;
            if (this.sign == '+')
                this.ans += parseInt(this.val);
            else if (this.sign == '-')
                this.ans -= parseInt(this.val);

            console.log(this.ans);
        }
    }
}
</script>

<style scoped>
.btn {
    border: none;
    color: white;
    padding: 14px 28px;
    font-size: 16px;
    cursor: pointer;
}

.success {
    background-color: #04AA6D;
}

/* Green */
.success:hover {
    background-color: #46a049;
}


.card {
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
    max-width: 300px;
    margin: auto;
    text-align: center;
    font-family: arial;
}

.card button {
    size: 20px;
    font-size: 20px;
    display: inline-block;
}

.card button:hover {
    opacity: 0.7;
}

.num {
    border: 5px solid rgba(255, 0, 0, 0.826);
    border-radius: 1px;
}

.answer {
    border: none;
    border-radius: 4px;
}
</style>
