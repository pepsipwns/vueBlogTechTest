<template>
    <div class="p-2">
        <div class="card" style="width: 18rem">
            <img :src="image" class="card-img-top" alt="..." />
            <div class="card-body">
                <h5 class="card-title">{{ title }}</h5>
                <p class="card-text preview-text">{{ text }}</p>
                <div class="row align-items-center justify-content-center">
                    <NuxtLink
                        :to="'Blog/' + id"
                        class="btn btn-primary col-12 order-2 col-lg-5 order-lg-1"
                    >Read More</NuxtLink>
                    <div class="col-12 order-1 col-lg-7 order-lg-2 text-end">
                        <span class="icon pe-2">
                            <font-awesome-icon :icon="['fas', 'comment-alt']"></font-awesome-icon>
                            <span class="ps-1 icon-text">3</span>
                        </span>
                        <span class="icon pe-2">
                            <font-awesome-icon :icon="['fas', 'eye']"></font-awesome-icon>
                            <span class="ps-1 icon-text">3,198</span>
                        </span>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: ["createdAt", "author", "image", "title", "intro", "text", "id"],
};
</script>
