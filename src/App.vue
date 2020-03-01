<template>
    <div id="app">
        <div id="nav">
            <router-link to="/">组件形式</router-link>
            <span>｜</span>
            <router-link to="/Bind">指令形式</router-link>
        </div>
        <router-view />
    </div>
</template>

<style lang="scss">
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
}

#nav {
    padding: 30px;

    a {
        font-weight: bold;
        color: #cccccc;
        text-decoration: none;
        &.router-link-exact-active {
            color: #2c3e50;
        }
    }
}
</style>
