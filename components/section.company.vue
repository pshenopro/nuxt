<template>
    <div class="company-slider">
        <div class="container section-padding-100-70">
            <h2 style="padding-top: 50px;">Программатик Q-Bid это:</h2>
        </div>

        <client-only>
            <swiper ref="mySwiper" class="swiper" :options="swiperOptions">
                <swiper-slide v-for="item of company.slides" :key="item.name">
                    <div class="container">
                        <h3>{{item.name}}</h3>
                    </div>
                </swiper-slide>

                <div class="swiper-button-prev" slot="button-prev"></div>
                <div class="swiper-button-next" slot="button-next"></div>
                <div class="swiper-pagination" slot="pagination"></div>
            </swiper>
        </client-only>

        <section class="about-us-area ico-about-bg section-padding-100-70 clearfix">
            <div class="container">
                <div class="section-heading text-center">
                    <h2 class="fadeInUp">Что мы умеем?</h2>
                </div>
                <div class=" section-padding-0-70">
                    <div class="row align-items-center">
                        <div class="col-lg-6 offset-lg-0 col-xs-12">

                            <div class="services-block-four transparent" v-for="item of company.list" :key="item.content">
                                <div class="inner-box">
                                    <div class="icon-icon bg1">
                                        <img :src="item.icon" alt="">
                                    </div>
                                    <p class="text">{{item.content}}</p>
                                </div>
                            </div>

                        </div>
                        <div class="col-12 col-lg-6 mt-s">
                            <div class="service-img-wrapper mb-0">
                                <div class="image-box">
                                    <img src="img/can-do.png" class="center-block img-responsive phone-img" alt="">
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section class="services section-padding-100-70 d-sec">
            <div class="container">

                <div class="section-heading text-center">
                    <h2>Возможности для клиентов</h2>
                </div>

                <div class="row">
                    <div v-for="item of company.perfomans" :key="company.head"
                        class="col-12 col-md-6 col-lg-3">
                        <!-- Content -->
                        <div
                            class="service_single_content text-center mb-100 fadeInUp"
                            :style="`background-image: url(${item.pic})`">
                            <div class="content-facing">
                                <h6>{{item.head}}</h6>
                                <ul v-html="item.content"></ul>
                            </div>
                        </div>
                    </div>

                </div>

            </div>
        </section>
    </div>
</template>

<script>
    import {Swiper, SwiperSlide} from 'vue-awesome-swiper'
    import '@/node_modules/swiper/css/swiper.css'

    export default {
        components: {
            Swiper,
            SwiperSlide
        },
        props: {
            company: Object,
        },
        data() {
            return {
                swiperOptions: {
                    slidesPerView: 1,
                    navigation: {
                        nextEl: '.swiper-button-next',
                        prevEl: '.swiper-button-prev',
                    },
                }
            }
        },
        computed: {
            swiper() {
                return this.$refs.mySwiper.$swiper
            }
        },
    }
</script>

<style lang="scss">
    .company-slider {
        /*background: #fff;*/

        h2 {
            color: #fff;
        }
    }

    .swiper-container {
        width: 100%;
        display: flex;

        .swiper-button-prev,
        .swiper-button-next {
            color: #fff;
        }
        .swiper-button-prev {
            left: 150px;
        }
        .swiper-button-next {
            right: 150px;
        }

        .swiper-wrapper {
            display: flex;
        }

        .swiper-slide {
            display: flex;
            width: 100%;
            align-items: center;
            height: 600px;
            cursor: pointer;

            &::selection {
                background: none;
            }

            h3 {
                font-size: 42px;
                color: #fff;
                width: 560px;
                line-height: 1.4;
                text-align: left;
            }
        }
    }

    .about-us-area {
        background: #fff;

        .icon-icon {
            border: none;
            background: none;
            line-height: 1;
        }

        .inner-box {
            h3 {
                color: #000;
            }

            p.text {
                font-size: 16px;
                color: #888;
                margin-top: 8px;
                margin-bottom: 10px;
                line-height: 1.5;
            }
        }

        .section-heading {
            h2 {
                color: #000;
            }
            p {
                color: #888;
            }
        }
    }

    .services {
        background: #eff4ff;

        .section-heading {
            h2 {
                color: #000;
            }
        }


        .service_single_content {
            height: 250px;
            cursor: pointer;
            transition: all .3s;
            padding: 0;
            overflow: hidden;
            background-position: right bottom;
            background-size: 80%;

            h6 {
                color: #000;
                text-align: left;
                font-size: 22px;
                font-weight: 600;
            }

            ul {
                text-align: left;
                transform: translateY(400px);
                transition: all .3s;
                padding-left: 30px;

                li {
                    padding-bottom: 5px;
                    line-height: 1.2;
                    font-size: 14px;
                    color: #585656;
                    list-style: disc;
                }
            }

            &:hover {
                background-size: 110% !important;

                .content-facing {
                    background-color: rgba(255, 255, 255, 0.85);

                    ul {
                        transform: translateY(0);
                    }
                }
            }
        }

        .content-facing {
            display: flex;
            flex-direction: column;
            width: 100%;
            height: 100%;
            padding: 40px 20px;
            overflow: hidden;
            transition: all .3s;
        }
    }

</style>
