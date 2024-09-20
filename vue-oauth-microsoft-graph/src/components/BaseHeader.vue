<template>

    <nav class="navbar">
        <ul>
            <li>
                <a href="#" @click.prevent="goHome">Home</a>
            </li>
            <li>
                <a href="#" @click.prevent="logIn">Log In</a>
            </li>
        </ul>
    </nav>
</template>


<style scoped>
.navbar {
    background-color: #42b983;
    padding: 10px;
}

ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    display: flex;
    justify-content: space-around;
}

li {
    display: inline;
}

a {
    color: white;
    text-decoration: none;
    padding: 10px 25px;
    font-size: 18px;
}

a:hover {
    background-color: #2c8a65;
    border-radius: 5px;
}
</style>