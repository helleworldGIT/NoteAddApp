<template>
  <div>
    <h1>
      Welcome to NoteAddApp! 🧑👧
    </h1>
    <p>
      Instructions:
      <br>
      Please click the "Add" button right below 👇 to add a note.
      <br>
      After that, you can edit the name and description of your note.
    </p>
    <button class="add" @click="createNote()">
      Add note
    </button>
    <div class="notes">
      <div class="note" v-for="(row, index) in notes" :key=row>
        <p class="close" @click="removeNote(index)">
          ✕
        </p>
        <h1 contenteditable="true">
          Title (click to edit me ✍)
        </h1>
        <p contenteditable="true">
          Description (click to edit me ✍)
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Notes',
  data(){
    return{
      notes: [],
      noteCounter: 0
    }
  },
  methods: {
    createNote(){
      this.noteCounter++
      this.notes.push(this.noteCounter)
    },
    removeNote: function(index) {
        this.notes.splice(index, 1)
      }
    }
  }
</script>

<style scoped lang="scss">
@import url('https://fonts.googleapis.com/css?family=Roboto+Slab&display=swap');

.add{
  background-color: #ed6663;
  color: #0f4c81;
  padding: 0.667rem;
  border-radius: 1.5rem;
    font-family: 'Roboto Slab', serif;
    font-family: 2rem;
    border: none;
    width: 8rem;
    outline: none;
    font-weight: bold;
    &:hover{
      cursor: pointer;
      box-shadow: 2px 3px 15px salmon;
      color: white;
      background-color: #0f4c81;
    }
}
.notes{
  display: flex;
  flex-wrap: wrap;
  flex-direction: row;
  justify-content: center;
  width: 90%;
  margin: auto;
  box-sizing: border-box;
  margin-top: 2rem;
  .note{
    .close{
      text-align: right;
      margin-right: 0.900rem;
      &:hover{
        font-weight: bold;
      }
    }
    font-family: 'Roboto Slab', serif;
    padding: 0.800rem;
    margin: 1.2rem;
    width: 20rem;
    height: auto;
    box-sizing: border-box;
    border-radius: 0.267rem;
    position: relative;
    top: 0;
    left: 0;
    transition: box-shadow 2s, left 2s, top 2s;
    box-shadow: 10px -10px 0 -3px white, 10px -10px 0 0 #ffaaa5,
                20px -20px 0 -3px white, 20px -20px 0 0 #ffd3b6,
                30px -30px 0 -3px white, 30px -30px 0 0 #dcedc1;
    background-color: #a8e6cf;
    &:hover{
    box-shadow: 0 0 0 -3px white, 0 0 0 0px #ffaaa5,
                0 0 0 -3px white, 0 0 0 0px  #ffd3b6,
                0 0 0 -3px white, 0 0 0 0px #dcedc1;
    top: -20px;
    left: 20px;
    cursor: pointer;
}
  }
}
</style>
