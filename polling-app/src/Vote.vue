<template>
    <div class="container">
       <div class="jumbotron">
        <h4>Rank the candidates below in order of preference - 1st choice, 2nd choice, 3rd choice, etc.</h3>
        <div class="row">
            {{votes}}
            <div class="col-sm-4" v-for="candidate in candidates">
                <h3>{{candidate.name}}</h3>
                <img :src="candidate.url"><img>
                <select @change="getName">
                    <option>-</option>
                    <option v-for="rank in ranks" @click="getRank(rank)" :value="candidate.name">{{rank}}</option>
                </select>
            </div>
        </div>
        <button @click="tally" class="btn btn-primary">Cast vote</button>
     </div>
    </div>
</template>
<script>
    export default {
        data(){
            return{
                candidates: [],
                ranks: ["1st", "2nd", "3rd", "4th", "5th", "6th"],
                id: '',
                rank: '',
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
            getRank(r){
               this.votes.push({name: this.name, rank: this.rank=r})
            },
            tally(){
               var v = this.votes.map( v => {
                   console.log(v.name, v.rank)
               })
            }
        },
        computed: {
            
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
</style>