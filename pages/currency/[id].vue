<template>
<main>
    <NuxtLink to="/">Home</NuxtLink>
    <h1>{{ coin.name }} detail page</h1>
    <table border="1 px solid">
        <thead>
            <tr>
                <th>Symbol</th>
                <th>Rank</th>
                <th>Price - Us</th>
                <th>Market Cap - Us</th>
            </tr>
        </thead>
        <tr>
            <td>{{ coin.symbol }}</td>
            <td>{{ coin.rank }}</td>
            <td>{{ coin.price_usd }}</td>
            <td>{{ coin.market_cap_usd }}</td>
        </tr>
    </table>    
</main>

</template>


<script setup>
const route = useRoute()
const { data } = await useFetch('/api/ticker/?id=' + route.params.id)
const coin = data.value[0]
</script>