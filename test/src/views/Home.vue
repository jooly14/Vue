<template>
    <div>
        <h1>Welcome to {{title2}}!</h1>
        <input type="text" v-model="input1">
        <button @click="getData">GET</button>
        <button @click="setData">SET</button>
        <select class="form-control" v-model="region" @change="chgRegion">
            <option v-for="(d,i) in options" :key="i" :value="d.v">{{d.t}}</option>
        </select>
        <input id="checkbox1" type="checkbox" v-model="tableShow"><label for="checkbox1">ShowTable</label>
        <table class="table table-bordered" v-show="tableShow">
            <tr :key="i" v-for="(d,i) in options">
                <td>{{d.v}}</td>
                <td>{{d.t}}</td>
            </tr>
        </table>
    </div>
</template>
<script>
export default {
    data () {
        return{
            title : "개발자의 품격",
            title2 : "Seoul",
            input1 : "abcd",
            options : [
                {v:"S", t:"Seoul"},
                {v:"J", t: "Jeju"},
                {v:"B", t: "Busan"},
            ],
            region : "J",
            tableShow : true
        } 
    },
    watch:{
        input1(){
            console.log("input1's value : "+ this.input1);
        },
        region(){
            console.log("region's value : "+ this.region);
        }
    },
    methods :{
        getData(){
            alert(this.input1);
        },
        setData(){
            this.input1 = "12345";
        },
        chgRegion(){
            alert(this.region);
        }
    },
    beforeCreate(){
        console.log("beforeCreate");
    },
    created(){
        console.log("created");
    },
    beforeMount(){
        console.log("beforeMount");
    },
    mounted(){
        console.log("mounted");
    },
    beforeUpdate(){
        console.log("beforeUpdate");
    },
    updated(){
         console.log("updated");
    }
}
</script>