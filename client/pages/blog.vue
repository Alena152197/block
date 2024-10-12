<template>
    <h2>Блог</h2>
    <main>
        <div class="posts">
            <article v-for="(post, index) in posts" :key="post.id">
                <h3>{{ post.title }}</h3>
                <div class="link">
                    <img :src="base_url + post.img[0].url" :alt=post.img[0].alternativeText>
                    <NuxtLink :style="'background:'+post.categories[0].bg" :to="'/post/' + post.documentId">Подробнее</NuxtLink>
                </div>
                <p>{{ post.desc }}</p>
                <!-- <ul class="tag">
                    <li v-for="(category, index) in post.categories" :key="category.id">
                        <NuxtLink :style="'background:'+post.categories[index].bg" :to="'/category' + post.categories[0].documentId">{{ category.title }}</NuxtLink>
                    </li>
                </ul> -->
            </article>
        </div>

    </main>
</template>


<script setup>
const api = await $fetch('http://localhost:1337/api/posts?populate=*')
const posts = api.data

const base_url = "http://localhost:1337"
</script>


<style scoped>


h2 {
    text-align: center;

}

.posts {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 25px;

}

@media screen and (max-width: 1024px) {
    .posts {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 25px;
    }
}

@media screen and (max-width: 800px) {
    .posts {
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 25px;
    }
}

@media screen and (max-width: 400px) {
    .posts {
        display: grid;
        grid-template-columns: repeat(1, 1fr);
        gap: 25px;
    }
}

article {
    background-color: #87CEEB70;
    padding: 10px;
    border: 5px solid #00008B;
    border-radius: 15px;
    height: max-content;
}

article img {
    width: 100%;
    height: 150px;
    object-fit: cover;
    border-radius: 10px;
}

article h3 {
    height: 70px;
}

article p {
    height: 56px;
}

article p,
article h3 {
    display: -webkit-box;
    -webkit-line-clamp: 3;
    -webkit-box-orient: vertical;
    overflow: hidden;
    text-wrap: wrap;
}

article a {
    display: block;
    text-decoration: none;
    font-weight: 700;
    border: 2px inset blue;
    border-radius: 5px;
    padding: 5px;
    width: 100px;
    text-align: center;
}

article a:hover {
    padding: 7px;
    color: red;
}

</style>