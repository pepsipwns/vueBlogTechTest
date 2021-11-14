<template>
    <div
        class="hero bg-cover-center d-flex justify-content-center"
        :style="{ backgroundImage: `url(${source})` }"
    >
        <div class="hero-text container">
            <div class="row align-items-center">
                <div class="col-12 col-lg-4">
                    <h6 class="subtitle">{{ subtitle }}</h6>
                    <h1 class="text-white">{{ title }}</h1>
                    <p class="text-white">{{ text }}</p>
                </div>
                <div v-if="searchArticles != null" class="col-12 offset-0 col-lg-4 offset-lg-2">
                    <div class="d-flex">
                        <input
                            class="form-control me-2"
                            type="search"
                            placeholder="Search"
                            v-model="searchValue"
                            aria-label="Search"
                        />
                        <button
                            class="btn btn-primary"
                            v-on:click="searchArticles(searchValue)"
                        >Search</button>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import stockImg from "static/stock-hero-3.jpg"
export default {
    props: ["subtitle", "title", "text", "searchValue", "searchArticles", "image"],
    data() {
        return {
            stockImg: stockImg,
        }
    },
    computed: {
        source() {
            return this.image || stockImg;
        }
    }
};
</script>
