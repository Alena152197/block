<template>
    <nav>
        <ul>
            <li>
                <NuxtLink to="/">Главная</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/blog">Блог</NuxtLink>
            </li>
            <li>
                <NuxtLink to="/contact">Контакты</NuxtLink>
            </li>
        </ul>
    </nav>
</template>

<style scoped>
nav {
    height: 7vh;
    width: 100%;
    left: 0;
    right: 0;
    top: 0;
    bottom: 0;
    background: linear-gradient(124deg, #e8b71d, #e3e81d, #1de840, #1ddde8, #2b1de8, #dd00f3, #dd00f3);
    background-size: 1800% 1800%;
    border-radius: 15px;

    -webkit-animation: rainbow 18s ease infinite;
    -z-animation: rainbow 18s ease infinite;
    -o-animation: rainbow 18s ease infinite;
    animation: rainbow 18s ease infinite;
}

@-webkit-keyframes rainbow {
    0% {
        background-position: 0% 82%
    }

    50% {
        background-position: 100% 19%
    }

    100% {
        background-position: 0% 82%
    }
}

@-moz-keyframes rainbow {
    0% {
        background-position: 0% 82%
    }

    50% {
        background-position: 100% 19%
    }

    100% {
        background-position: 0% 82%
    }
}

@-o-keyframes rainbow {
    0% {
        background-position: 0% 82%
    }

    50% {
        background-position: 100% 19%
    }

    100% {
        background-position: 0% 82%
    }
}

@keyframes rainbow {
    0% {
        background-position: 0% 82%
    }

    50% {
        background-position: 100% 19%
    }

    100% {
        background-position: 0% 82%
    }
}

ul {
    list-style: none;
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    gap: 20px;
    padding: 25px;
}

li a {
    color: black;
    text-decoration: none;
    font-weight: 700;
}

li a:hover {
    border: 3px inset red;
    border-radius: 5px;
    padding: 5px;
    background-color: wheat;

}
</style>