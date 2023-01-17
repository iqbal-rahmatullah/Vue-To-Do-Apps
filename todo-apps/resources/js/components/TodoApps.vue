<template>
    <div class="container d-flex justify-content-center p-2">
        <div class="p-2">
            <h1>Todo Apps</h1>
            <form class="input-group">
                <input class="form-control" type="text" v-model="input">
                <button class="btn btn-info text-white" type="button" @click="addList">Submit</button>
            </form>
            <ul class="pt-3">
                <li v-for="(item, index) in list" :key="index">
                    {{ item.judul }} <span class="text-danger" @click="deleteList(index)">Hapus</span>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
    export default {
        data:function() {
            return{
                list: [
                    {
                        judul : "Menyapu"
                    },
                    {
                        judul : "Mengepel"
                    },
                    {
                        judul : "Turu"
                    },
                ],
                input : "",
            }
        },
        methods: {
            addList(){
                let newList = {
                    judul : this.input
                }
                this.list.push(newList)
                this.input = ""
            },
            deleteList(index){
                this.list.splice(index,1)
            }
        },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>