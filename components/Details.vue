<template>
    <div id="details-section">
        <div v-for="(content, index) in players" :key="index">
            <div v-for="(player, index) in content" :key="index" :id="player.firstname + player.id" class="details-modal">
                <div class="col-5 player-img-section">
                    <img :src="player.picture" class="w-100">
                </div>
                <div class="col-7 d-flex flex-column justify-content-around">
                    <h2>{{ player.firstname }} {{ player.lastname }}</h2>
                        <div class="row">
                        <div class="col-4">
                        <h4>Rank</h4>
                        <p>#{{ player.data.rank }}</p>
                        </div>
                        <div class="col-4">
                            <h4>Points</h4>
                            <p>{{ player.data.points }}</p>
                        </div>
                        <div class="col-4">
                            <h4>Country</h4>
                            <p>{{ player.country.code }}</p>
                        </div>
                        </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import players from '~/data/headtohead'

export default{
    data() {
        return{
            players
        } 
    }
}
</script>