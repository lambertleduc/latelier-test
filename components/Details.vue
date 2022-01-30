<template>
    <div id="details-section">
        <div v-for="(content, index) in players" :key="index">
            <div v-for="(player, index) in content" :key="index" :id="player.firstname + player.id" class="player-container">
                <div class="col col-xl-5 player-stat-img">
                    <img :src="player.picture" class="w-100">
                </div>
                <div class="player-stat-text col col-xl-9">
                    <div class="player-stat-top">
                        <div>
                            <h1>{{ player.firstname }}</h1> 
                            <h1>{{ player.lastname }}</h1>
                        </div>
                        <div class="col col-xl-3"><img :src="player.country.picture" class="w-100"></div>
                    </div>
                    <div class="player-stat-description">
                        <div>
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
                            <div class="row">
                                <div class="col-4">
                                    <h4>Birthday</h4>
                                    <p>{{ getBirthday(player.data.age) }}</p>
                                </div>
                                <div class="col-4">
                                    <h4>Age</h4>
                                    <p>{{ player.data.age }}</p>
                                </div>
                            </div>
                            <div class="row">
                                <div class="col-4">
                                    <h4>Rank</h4>
                                    <p>#{{ player.data.weight }}</p>
                                </div>
                                <div class="col-4">
                                    <h4>Points</h4>
                                    <p>{{ player.data.height }}</p>
                                </div>
                            </div>
                        </div>
                        <div>
                            <h3 class="career-titles">Career Titles</h3>

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
    },
    methods: {
        getBirthday(age) {
            return new Date().getFullYear() - age
        }
    }
}
</script>