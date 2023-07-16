<template>
    <header>
        <div class="s-logo"><img alt="logo" class="logo" src="@/assets/img/mobile/Logo mobile.png"  /></div>
        <ul class="menu">
            <li><RouterLink to="/">Home</RouterLink></li>
            <li><RouterLink to="/stores">Nossas lojas</RouterLink></li>
            <li><RouterLink to="/news">Novidades</RouterLink></li>
            <li><RouterLink to="/sale">Promoções</RouterLink></li>
        </ul>

        <div class="s-input">
            <input type="text" placeholder="Digite o produto" >
            <button>Buscar</button>
        </div>
    </header>
</template>
<script>
    import { RouterLink } from 'vue-router'

    export default{
        name: 'HeaderComp'
    }

</script>