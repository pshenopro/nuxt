<template>
    <section class="hero-section blue-bg relative section-padding" id="home">
        <div class="hero-section-content" style="">

            <div class="container h-100">
                <div class="row h-100 mb-50 align-items-center">

                    <!-- Welcome Content -->
                    <div class="col-12 col-lg-7 col-md-12">
                        <div class="welcome-content">
                            <h1 class="w-text wow fadeInUp">{{header.h1}}</h1>
<!--                            <p class="g-text wow fadeInUp">{{header.desc}}</p>-->
                            <div class="promo-section">
                                <h3 class="special-head">
                                    <span>25%</span><p>среднее снижение стоимости конверсии <br>(5 предиктивных моделей в целевое действие онлайн/офлайн)</p>
                                </h3>
                                <h3 class="special-head">
                                    <span>70%</span><p>среднее снижение стоимости охвата <br>(кроссканальное решение)</p>
                                </h3>
                                <h3 class="special-head">
                                    <span>18%</span><p>среднее увеличение офлайн продаж</p>
                                </h3>
                                <h3 class="special-head">
                                    <span>41 </span><p>успешный кейс (pharma, fmcg, telecom, ecom)</p>
                                </h3>
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-5 col-md-12 section-padding-0-150">
                        <img src="img/head.png" class="mt-30" alt="">
                    </div>

                </div>
            </div>
        </div>
    </section>
</template>

<script>
    export default {
        name: "section.header",
        props: {
            header: Object
        }
    }
</script>

<style lang="scss">
    .hero-section-content {
        background-size: contain;
        background-repeat: no-repeat;
        background-position: right;
    }
    .hero-section img {
        max-width: 200%;
        margin-left: -200px;
    }
    .welcome-content {
        margin-top: 30px;
        padding-bottom: 140px;

        h1 {
            line-height: 1.2;
            padding-bottom: 40px;
            font-size: 52px;
        }

        .g-text {
            line-height: 1.5;
        }

        .special-head:before {
            content: none;
        }

        .promo-section h3 {
            padding-left: 0;
            font-size: 36px;

            p {
                font-size: 18px;
                color: #fff;
            }

            span {

                width: 75px;
                display: block;
                color: #fff;
                font-size: 42px;
            }
        }
    }
</style>
