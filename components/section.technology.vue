<template>
    <div class="technologys">
        <section class="pricing section-padding-100-70">

            <div class="container">
                <div class="section-heading text-left">
                    <h2 class="d-blue bold fadeInUp">Технологии</h2>
                    <p class="fadeInUp">
                        Вы не платите никаких наценок, потому что используете решения от реального разработчика и поставщика технологии.
                        Вы получаете прозрачные и эффективные programmatic-закупки и контроль над ними, не углубляясь в технологии.
                        Вы идете в ногу с рынком и получаете продукты с актуальными фичами, потому что мы постоянно расширяем функциональность наших решений.
                    </p>
                </div>
                <div class="row">
                    <!-- Single Table -->
                    <div
                        v-for="item of technology.slides"
                        class="col-lg-6 col-md-6 col-sm-12 section-padding-0-20 row-item">
                        <div class="single_price_table_content active text-left">
                            <div class="price_table_text">
                                <h2>{{item.head}}</h2>
                            </div>
                            <div class="table_text_details">
                                <ul v-html="item.content">
                                </ul>
                            </div>
                        </div>
                    </div>
                </div>
            </div>

        </section>
        <div class="clearfix"></div>
    </div>
</template>

<script>
    export default {
        props: {
            technology: Object,
        }
    }
</script>

<style lang="scss">
    .technologys {
        background-color: #fff;
        background-image: url(../static/img/stock-bg1-l.png), url(../static/img/stock-bg1-r.png);
        background-repeat: no-repeat;
        background-size: 500px;
        background-position: -10% center, 110% center;

        .row-item {
            margin-bottom: 20px;

            .single_price_table_content {
                height: 100%;
            }
        }

        h2 {
            color: #000;
            text-align: center;
            padding-bottom: 40px;
        }
        .section-heading {
            p {
                line-height: 1.4;
                color: #888;
            }
        }
        .price_table_text {
            text-align: left;
            h2 {
                text-align: left;
                color: #000;
                padding-bottom: 0px;
            }
        }
        .table_text_details {
            p {
                color: #888;
                padding-bottom: 15px;
                line-height: 1.3;
            }
            li {
                list-style: disc;
                padding-bottom: 15px;
                line-height: 1.3;
                color: #888;
            }
        }
    }
</style>
