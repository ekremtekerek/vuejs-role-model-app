<template>
    <b-card
    :title="modelName"
    :img-src="modelPic"
    img-alt="Image"
    img-top
    tag="article"
    style="max-width: 20rem;"
    class="mb-2 mt-2"
  >
    <b-card-text>
      {{modelJob}} - {{modelNationality}} - {{modelBirthday}} 
    </b-card-text>
    <b-card-text>
      {{modelAbout}}
    </b-card-text>
    <div class="tagsClass">
        <b-card-text class="tagsText" v-for="(i, index) in tags" :key="index">
            #{{i}}
        </b-card-text>
    </div>
    <div class="bottom-buttons">
        <b-button @click="updateEmitIndex()" variant="outline-success">Update</b-button>
        <b-button  @click="deleteModelOpen()" variant="danger">Delete</b-button>
     </div>   
  </b-card>
</template>

<script>
export default {
     props: { 
        modelName : String,
        modelJob : String,
        modelNationality: String,
        modelBirthday:String,
        modelAbout:String,
        modelPic:String,
        tags:Array,
        index:Number
    },
    data() {
        return {
    
        }
    },

    methods: {
        updateEmitIndex() {
            this.$emit('updateEmitIndex', this.index)
        },

        deleteModelOpen() {
            this.$emit('deleteModelOpen', this.index)
        }
    },
}
</script>

<style>
    .tagsClass {
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        margin-bottom: 15px;
        justify-content: center;
    }

    .tagsText {
        background-color: #d5ede8;
        margin:4px;
        font-size: 16px;
        font-family: Calibri, sans-serif;
        padding:2px 10px;
        box-shadow: 0 0 3px #0e9acd;
        border-radius: 18px;
    }

    .card-text:last-child {
        margin-bottom: 4px;
    }

    .bottom-buttons {
        display: flex;
        flex-direction: row;
        justify-content: space-around;
    }

</style>