<template>
    <div class="container">
       <div class="jumbotron">
        <h4>Rank the candidates below in order of preference - 1st choice, 2nd choice, 3rd choice, etc.</h3>
        <div id="results" v-if="tally">
            <ul class="list-group" >
                <li class="list-group-item" v-for="c in cand">{{c.name}} is {{c.rank}}</li>
            </ul>
        </div>
        <div class="row" v-if="!tally">
            <div class="col-sm-4" v-for="(candidate, index) in candidates">
                <div>
                <h3>{{candidate.name}}</h3>
                <img :src="candidate.url"><img>
                <select @change="getName">
                    <option>-</option>
                    <option v-for="rank in ranks" @click="getRank(index, rank)" :value="candidate.name">{{rank}}</option>
                </select>
                </div>
            </div>
        </div>
        <button class="btn btn-primary" @click="vote" v-if="!tally">Cast vote</button>
     </div>
    </div>
</template>
<script>
    import sortBy from 'lodash'
    export default {
        data(){
            return{
                candidates: [],
                ranks: ["1st", "2nd", "3rd", "4th", "5th", "6th"],
                name: '',
                rank: '',
                tally: false,
                votes: []
            }
        },
        created(){
            this.loadCandidates();
        },
        methods: {
            loadCandidates(){
                this.candidates = [
                    {id:1, name: 'Bill Clinton', url: "http://www.wpclipart.com/American_History/presidents/Clinton_Bill.png"},
                    {id:2, name: 'Dwight D. Eisenhower', url: "http://www.wpclipart.com/American_History/presidents/Eisenhower_Dwight_D.png"},
                    {id:3, name: 'John F. Kennedy', url: "http://www.wpclipart.com/American_History/presidents/Kennedy_John_F.png"},
                    {id:4, name: 'Abraham Lincoln', url: "http://www.wpclipart.com/American_History/presidents/Lincoln_Abraham.png"},
                    {id:5, name: 'Ronald Reagan', url: "http://www.wpclipart.com/American_History/presidents/Reagan_Ronald.png"},
                    {id:6, name: 'Franklin Delano Roosavelt', url: "http://www.wpclipart.com/American_History/presidents/Roosavelt_Franklin_Delano.png"}
                ]
            },
            getName(e){
                this.name = e.target.value
            },
            getRank(index, rank){
               this.votes.push({index: index, name: this.name, rank: this.rank = rank})
            },
            vote(){
             this.tally = true
            }
        },
        computed: {
            cand(){
                return _.sortBy(this.votes, 'rank')
            }
        }
    }
</script>
<style>
    img{
        width: 125px;
        height: 150px;
        margin: 20px;
    }
    .row{
        margin-top: 50px;
    }
    .btn-primary{
        float: right;
    }
    #results{
        margin-top: 50px;
    }
</style>
