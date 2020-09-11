<template>
    <nav v-scroll="handleScroll" class="navbar navbar-expand-lg navbar-white fixed-top" :class="[scrollNav ? 'active' : '']" id="banner">
        <div class="container">
            <!-- Brand -->
            <NuxtLink to="/" class="navbar-brand">
                <Logo />
            </NuxtLink>
            <!-- Toggler/collapsibe Button -->
            <button class="navbar-toggler" type="button" data-toggle="collapse">
                <span class="navbar-toggler-icon"></span>
            </button>

            <!-- Navbar links -->
            <div id="app" class="collapse navbar-collapse">
                <ul class="navbar-nav ml-auto">
                    <li class="nav-item" v-for="item of nav" :key="item.name">
                        <NuxtLink class="nav-link" :to="item.path">{{item.name}}</NuxtLink>
                    </li>

                    <li class="lh-55px"><a href="#" class="btn login-btn ml-50">some text</a></li>
                </ul>
            </div>
        </div>
    </nav>
</template>

<script>
    import Logo from '@/components/logo'
    import Vue from 'vue'

    Vue.directive('scroll', {
        inserted: function (el, binding) {
            let f = function (evt) {
                if (binding.value(evt, el)) {
                    window.removeEventListener('scroll', f)
                }
            }
            window.addEventListener('scroll', f)
        }
    })

    export default {
        components: {
            Logo
        },
        data() {
            return {
                nav: [
                    {
                        name: 'Главная',
                        nameEng: '',
                        path: '/',
                    },
                    {
                        name: 'О компании',
                        nameEng: '',
                        path: '/',
                    },
                    {
                        name: 'Технологии',
                        nameEng: '',
                        path: '/',
                    },
                    {
                        name: 'Кейсы',
                        nameEng: '',
                        path: '/',
                    },
                    {
                        name: 'Контакты',
                        nameEng: '',
                        path: '/',
                    }
                ],
                scrollNav: false,
            }
        },
        methods: {
            handleScroll: function (evt, el) {
                if (pageYOffset > 199) {
                    this.scrollNav = true;
                    return
                }

                this.scrollNav = false;
            }
        },
    }
</script>

<style lang="scss">
    .navbar-brand {
        padding-top: 10px;
    }
    #banner {
        transition: all .3s;

        .login-btn {
            color: #fff;
            background: #7450fe;
            border-color: #7450fe;

            &:hover {
                color: #fff;
                background: #ff6a00;
                border-color: #ff6a00;
            }
        }
    }
    #banner.active {
        background: #46484aa8;
        padding: 0;

        .navbar-brand {
            padding-top: 0;
        }
    }
</style>
