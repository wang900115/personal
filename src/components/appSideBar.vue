<template>
    <nav class="navbar">
        <router-link to="/" class="nav-link" :class="{ 'active-link': $route.path === '/' }">Home</router-link>
        <router-link to="/resume" class="nav-link"
            :class="{ 'active-link': $route.path === '/resume' }">Resume</router-link>

    </nav>
</template>


<style scoped>
.navbar {
    position: fixed;
    top: 0;
    right: 0;
    height: 100vh;
    width: 150px;
    background: linear-gradient(to bottom, rgb(255, 255, 255), rgb(75, 75, 75));
    padding: 2rem 1rem;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    box-shadow: -4px 0px 6px rgba(0, 0, 0, 0.1);
}

.nav-link {
    text-decoration: none;
    color: #ffffff;
    font-size: 1.2rem;
    font-weight: 500;
    margin-bottom: 1rem;
    transition: color 0.3s ease, transform 0.3s ease;
}

.nav-link:hover {
    color: white;
}

.active-link {
    color: black;
    transform: translateX(10px);
}
</style>
