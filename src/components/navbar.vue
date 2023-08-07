<template>
    <div class="navbar-block">
        <router-link to="/">
            <img class="logo" src="@/assets/logo.png" alt="logo">
        </router-link>
        <nav class="navbar">
            <router-link to="/">About us</router-link>
            <router-link to="/">Contacts</router-link>
            <router-link to="/">Test</router-link>
            <router-link to="/">Test</router-link>
            <router-link to="/">Test</router-link>
        </nav>
    </div>
</template>

<style lang="scss">

.navbar-block{
    padding: 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed;
    width: 100%;
    background-color: white;
    left: 0;
    z-index: 1000;
    top: 0;
    box-shadow: 0 0 10px 0 rgb(180, 180, 180);

    .logo{
        width: 70px;
    }

    .navbar{
        margin-right: 40px;
        a{
            margin-right: 20px;
            text-decoration: none;
            color: rgb(74 155 84);
            font-size: 20px;
            font-weight: 500;

            &:last-child {
                margin-right: 0;
            }
        }
    }
}


</style>