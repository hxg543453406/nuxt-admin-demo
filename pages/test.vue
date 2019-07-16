<template>
    <div>
        <h1>例子</h1>
        <el-dropdown size="small" split-button type="primary" @command="changeLange">
            {{lang}}
            <el-dropdown-menu slot="dropdown">
                <el-dropdown-item command="zh">中文</el-dropdown-item>
                <el-dropdown-item command="en">English</el-dropdown-item>
            </el-dropdown-menu>
        </el-dropdown>
        <h3>{{$t('test.t1')}}</h3>
        <h3 v-text="$t('test.t2')"></h3>
    </div>
</template>

<script>
export default {
    // layout: 'error',
    data(){
        return {
            lang: 'English',
        }
    },
    methods: {
        changeLange(val) {
            let locale = this.$i18n.locale;
            if(locale === val) return

            this.$i18n.locale = val;
            this.lang = val === 'zh' ? '中文' : 'English'
            locale = val;
            this.$cookie.set('lang', val)
            localStorage.setItem('lang', locale)
            this.$store.commit('SET_LANG', locale)
            this.$store.commit('SET_SIDEBAR')
        }
    },

    asyncData(val){
        // console.log(val)
        // return {lang: '中文'}
    },

    fetch(app){
        // console.log(app)
        // console.log(app.req.headers.cookie)
        // let cookie =  app.req.headers.cookie || 'lang=en'
        // let locale = 'en'
        // app.store.commit('SET_LANG', locale)
    },

    mounted(){
        let locale = this.$cookie.get('lang') || 'en';
        this.lang = locale === 'en' ? 'English' : '中文'
        this.$i18n.locale = locale;
        // this.$store.commit('SET_LANG', locale)
    }
}
</script>

<style lang="scss" scoped>
</style>
