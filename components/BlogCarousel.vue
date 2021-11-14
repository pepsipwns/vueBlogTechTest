<template>
    <div class="container-fluid">
        <VueSlickCarousel :arrows="true" :dots="true" :slidesToShow="3" :slidesToScroll="3">
            <BlogCard
                v-for="i in 6"
                :key="i"
                :createdAt="articles[i].createdAt"
                :author="articles[i].author"
                :image="articles[i].image"
                :title="articles[i].title"
                :intro="articles[i].intro"
                :text="articles[i].text"
                :id="articles[i].id"
            ></BlogCard>
        </VueSlickCarousel>
    </div>
</template>

<script>
import VueSlickCarousel from 'vue-slick-carousel'
import 'vue-slick-carousel/dist/vue-slick-carousel.css'
// optional style for arrows & dots
import 'vue-slick-carousel/dist/vue-slick-carousel-theme.css'
export default {
    props: ["articles"],
    components: { VueSlickCarousel },
};
</script>
