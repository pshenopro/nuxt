<template>
    <div class="naccs section-padding-70-70">
        <div class="grid container">
            <h2>Кейсы</h2>
            <div class="gc gc--1-of-3">
                <div class="menu">
                    <div
                        v-for="item of cases.menu"
                        @click="menuClick(item.name)"
                        :class="[item.val ? 'active' : '']">
                        <span class="light"></span><span>{{item.name}}</span>
                    </div>
                </div>
            </div>
            <div class="gc gc--2-of-3">
                <ul class="nacc" ref="myUl">
                    <li :ref="item.name" :key="item.name" v-for="item of cases.menu" :class="[item.val ? 'active' : '']">
                        <div class="nacc-content" v-html="item.text">

                        </div>
                    </li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "section.cases",
        props: {
            cases: Object
        },
        data() {
            return {
                menu: [
                    {name:'Beer', val: true, text: 'Beer is the world\'s oldest[1][2][3] and most widely consumed[4] alcoholic drink; it is the third most popular drink overall, after water and tea.[5] The production of beer is called brewing, which involves the fermentation of sugars, mainly derived\n' +
                            '                                from cereal grain starches—most commonly from malted barley, although wheat, maize (corn), and rice are widely used.[6] Most beer is flavoured with hops, which add bitterness and act as a natural preservative, though other flavourings such as\n' +
                            '                                herbs or fruit may occasionally be included. The fermentation process causes a natural carbonation effect, although this is often removed during processing, and replaced with forced carbonation.[7] Some of humanity\'s earliest known writings refer\n' +
                            '                                to the production and distribution of beer: the Code of Hammurabi included laws regulating beer and beer parlours,[8] and "The Hymn to Ninkasi", a prayer to the Mesopotamian goddess of beer, served as both a prayer and as a method of remembering\n' +
                            '                                the recipe for beer in a culture with few literate peop'},
                    {name:'Wine', val: false, text: 'A vine (Latin vīnea "grapevine", "vineyard", from vīnum "wine") in the narrowest sense is the grapevine (Vitis), but more generally it can refer to any plant with a growth habit of trailing or scandent (that is, climbing) stems, lianas or runners.\n' +
                            '                                The word also can refer to such '},
                    {name:'Lemonade', val: false, text: 'Lemonade is any of various sweetened beverages found around the world, all characterized by lemon flavor. Most lemonade varieties can be separated into two distinct types: cloudy and clear; each is known simply as "lemonade" (or a cognate) in countries\n' +
                            '                                where dominant.[1] Cloudy lemonade, generally found in North America and India, is a traditionally homemade drink made with lemon juice, water, and sweetener such as cane sugar or honey.[2] Found in the United Kingdom, Ireland, South Africa, Australia,\n' +
                            '                                and New Zealand, clear l'}
                ]
            }
        },
        methods: {
            menuClick(name) {
                this.cases.menu.map(el => {
                    if (name === el.name) {
                        el.val = true
                        return el
                    }
                    el.val = false
                    return el
                })
            },
            returnHeight() {
                let arr = [];
                this.cases.menu.forEach(el => {
                    arr.push(this.$refs[el.name][0].offsetHeight)
                })

                this.$refs.myUl.style.height = Math.max(...arr) + 'px'
            }
        },
        computed: {

        },
        mounted() {
            this.returnHeight()
        }
    }
</script>

<style lang="scss">
    .grid {
        list-style: none;
    }

    .gc {
        box-sizing: border-box;
        display: inline-block;
        margin-right: -0.25em;
        min-height: 1px;
        padding-left: 40px;
        vertical-align: top;
    }

    .gc--1-of-3 {
        width: 33.33333%;
    }

    .gc--2-of-3 {
        width: 66.66666%;
    }

    .naccs {
        position: relative;
        width: 100%;

        h2 {
            padding-bottom: 30px;
        }

        .nacc-content {
            h3 {
                color: #000;
                font-size: 24px;
            }

            ul {
                opacity: 1;
                padding-left: 30px;

                li {
                    list-style: disc;
                    opacity: 1;
                    position: static;
                    transform: none;
                }
            }

            div {
                padding: 20px;
                margin-bottom: 25px;
                background: #ffffff;
                border-radius: 10px;
                box-shadow: 0px 0px 16px 9px rgba(14,14,14, .37);
            }
        }
    }

    .naccs .menu div {
        padding: 15px 20px 15px 40px;
        margin-bottom: 10px;
        color: #303f9f;
        background: #3f51b5;
        box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
        cursor: pointer;
        position: relative;
        vertical-align: middle;
        font-weight: 700;
        -webkit-transition: 1s all cubic-bezier(0.075, 0.82, 0.165, 1);
        transition: 1s all cubic-bezier(0.075, 0.82, 0.165, 1);
    }

    .naccs .menu div:hover {
        box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    .naccs .menu div span.light {
        height: 10px;
        width: 10px;
        position: absolute;
        top: 24px;
        left: 15px;
        background-color: #303f9f;
        border-radius: 100%;
        -webkit-transition: 1s all cubic-bezier(0.075, 0.82, 0.165, 1);
        transition: 1s all cubic-bezier(0.075, 0.82, 0.165, 1);
    }

    .naccs .menu div.active span.light {
        background-color: #fff;
        left: 0;
        height: 100%;
        width: 3px;
        top: 0;
        border-radius: 0;
    }

    .naccs .menu div.active {
        color: #fff;
        padding: 15px 20px 15px 20px;
    }

    ul.nacc {
        position: relative;
        height: 0px;
        list-style: none;
        margin: 0;
        padding: 0;
        -webkit-transition: 0.5s all cubic-bezier(0.075, 0.82, 0.165, 1);
        transition: 0.5s all cubic-bezier(0.075, 0.82, 0.165, 1);
    }

    ul.nacc li {
        opacity: 0;
        -webkit-transform: translateX(50px);
        transform: translateX(50px);
        position: absolute;
        list-style: none;
        -webkit-transition: 1s all cubic-bezier(0.075, 0.82, 0.165, 1);
        transition: 1s all cubic-bezier(0.075, 0.82, 0.165, 1);
        p {
            color: #fff;
        }
    }

    ul.nacc li.active {
        -webkit-transition-delay: 0.3s;
        transition-delay: 0.3s;
        z-index: 2;
        opacity: 1;
        -webkit-transform: translateX(0px);
        transform: translateX(0px);
    }

    ul.nacc li p {
        margin: 0;
    }
</style>
