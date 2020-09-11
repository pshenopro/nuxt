<template>
    <section class="section-padding-100-70 sky-bg" id="timeline">
       <div class="wrapper-slider">
           <h2>Итория развития</h2>
           <div class="mySlider">
               <swiper ref="mySwiper" class="swiper main-timeline" :options="swiperOptions">
               <swiper-slide
                   :style="`background-image:url(${images[index]})`"
                   class="service_single_content text-left mb-100"
                   v-for="(item, index) of timeLine.slides"
                   :key="index">
                   <div class="layer"></div>
                   <p>{{item}}</p>
               </swiper-slide>

               <div class="swiper-pagination" slot="pagination"></div>
               </swiper>
               <div class="swiper-button-prev" slot="button-prev"></div>
               <div class="swiper-button-next" slot="button-next"></div>
           </div>
       </div>
    </section>
</template>

<script>
    import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
    import '@/node_modules/swiper/css/swiper.css'

    export default {
        components: {
            Swiper,
            SwiperSlide
        },
        props: {
            timeLine: Object,
        },
        data() {
            return {
                images: ['img/timeline-1.png', 'img/timeline-2.png', 'img/timeline-3.png', 'img/timeline-4.png', 'img/timeline-5.png', 'img/timeline-6.png'],
                swiperOptions: {
                    slidesPerView: 3,
                    spaceBetween: 70,
                    navigation: {
                        nextEl: '.swiper-button-next',
                        prevEl: '.swiper-button-prev',
                    },
                },
            }
        },
        methods: {

        },
        computed: {
            swiper() {
                return this.$refs.mySwiper.$swiper
            }
        },
    }
</script>

<style lang="scss">
    #timeline {
    /*    background-color: #fff;*/
    /*    background-image: url(../static/img/stock-bg1-l.png), url(../static/img/stock-bg1-r.png);*/
    /*    background-repeat: no-repeat;*/
    /*    background-size: 500px;*/
    /*    background-position: left center, right center;*/
        .wrapper-slider {
            margin: 0 auto;
            position: relative;
        }
        .mySlider {
            width: 100%;
            display: flex;
            align-items: center;

            .service_single_content {
                background-size: 50%;
                background-position: right bottom;
            }
        }
        .swiper-button-prev,
        .swiper-button-next {
            color: #000;
            top: 60%;

            &:focus {
                outline: none;
                border: none;
            }
        }
        h2 {
            color: #000;
            text-align: center;
            padding-bottom: 40px;
        }

        .container {
            overflow: hidden;
        }

        .swiper-button-prev {
            left: 100px;
        }
        .swiper-button-next {
            right: 100px;
        }

        .swiper-container {
            width: 1180px;
            padding-left: 20px;
            padding-right: 20px;
            overflow: hidden;

            .swiper-slide {
                flex-direction: column;
                justify-content: flex-start;
                align-items: flex-start;
                position: relative;
                background-color: #f3f7fa;
                height: 260px;

                .layer {
                    position: absolute;
                    top: 0;
                    right: 0;
                    left: 0;
                    bottom: 0;
                    width: 100%;
                    height: 100%;
                    background: #fff;
                    opacity: .4;
                }

                h6 {
                    color: #000;
                    z-index: 9;
                }

                p {
                    color: #000;
                    width: 285px;
                    z-index: 9;
                    line-height: 1.4;
                    font-size: 20px;
                }
            }
        }
    }
    .main-timeline {
        &::before {
            content: none;
        }
    }
    .service_single_content {
        border-radius: 10px;
        background-color: #fff;
        background-repeat: no-repeat;
        background-position: center;
        background-size: cover;
        -webkit-box-shadow: 0 5px 10px 1px rgba(0, 0, 0, 0.11);
        box-shadow: 0 5px 10px 1px rgba(0, 0, 0, 0.11);
        border: none;
        padding: 40px 20px;
        margin-bottom: 30px !important;
    }
    /*.main-timeline {
        min-width: 300px;
        max-width: 500px;
        margin: auto;

        &::before {
            content: none;
        }

        p {
            font-size: 1em;
            line-height: 1.75em;
            border-top: 3px solid;
            -webkit-border-image: -webkit-gradient(linear, left top, right top, from(#743ad5), to(#d53a9d));
            -webkit-border-image: linear-gradient(to right, #743ad5 0%, #d53a9d 100%);
            -o-border-image: linear-gradient(to right, #743ad5 0%, #d53a9d 100%);
            border-image: -webkit-gradient(linear, left top, right top, from(#743ad5), to(#d53a9d));
            border-image: linear-gradient(to right, #743ad5 0%, #d53a9d 100%);
            border-image-slice: 1;
            border-width: 3px;
            margin: 0;
            padding: 40px;
            counter-increment: section;
            position: relative;
            color: #34435E;
        }
        p:before {
            content: counter(section);
            position: absolute;
            border-radius: 50%;
            padding: 4px;
            height: 1.45em;
            width: 1.45em;
            background-color: #34435E;
            text-align: center;
            line-height: 1.25em;
            color: #ffffff;
            margin-left: -11px;
            font-size: 1em;
        }

        p:nth-child(odd) {
            border-right: 3px solid;
            padding-left: 0;
        }
        p:nth-child(odd):before {
            left: 100%;
            margin-left: -10px;
        }

        p:nth-child(even) {
            border-left: 3px solid;
            padding-right: 0;
        }
        p:nth-child(even):before {
            right: 98%;
            margin-left: -11px;
        }

        p:first-child {
            border-top: 0;
            border-top-right-radius: 0;
            border-top-left-radius: 0;
        }

        p:last-child {
            border-bottom-right-radius: 0;
            border-bottom-left-radius: 0;
        }
    }*/
</style>
