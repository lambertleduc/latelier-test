<template>
    <div class="position-relative">
        <div class="reversed-backround"></div>
        <div class="container">
            <div id="main-section" >
                <input type="input" class="search-area" placeholder="Rechercher un joueur">
                <div v-for="(content, index) in playersSorted" :key="index">
                    <div v-for="(player, index) in content" :key="index" class="row player-card mx-0" :on-click="openModal(player.firstname + player.id)">
                        <div class="col-xl-5 player-img-section">
                           <img :src="player.picture" class="player-img align-center">
                        </div>
                        <div class="col-xl-7 d-flex flex-column justify-content-around">
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
            <Details/>
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
    },
    computed: {
        playersSorted: function () {
            return players
        }
    }, 
    methods: {
        openModal(prop) {
           // document.getElementById(prop).style.display = "block";
        }
    }
}
</script>
