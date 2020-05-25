<template>
<div>
<!-- Individual Card Data -->
<div class="card">
  <div class="image">
  <img  :src="require('@/assets/'+ booksImage)"  width="100%" height="100%"/>
   <div class="top-right" v-if="booksData.dueDate > 0">
    <div class="border-due-image">
      <i class="material-icons">date_range</i>&nbsp;&nbsp;
      <span class="dueDate">Due in {{booksData.dueDate}} days </span>
    </div>
   </div>
  </div>
  <div id="progressbar">
  <div :style="{ width: progressObject + '%' }"></div>
  </div>
  <div class="card-description">
   <h1 class="card-header-title"> {{booksData.title}}</h1>
   <p class="card-text-description"> {{booksData.description}}</p>
   <span class="card-button">
   <span class="card-button-margin hide"><button class="button buttonTransparent">View Progress</button></span>
   <span class="card-button-margin"><button class="button">Resume</button></span>
   </span>
  </div>
  </div>
</div>
</template>

<script>
import '../css/global.css';
export default {
data () {
//Return ProgressRate value and BooksImage
    return {
              progressObject: this.booksData.progressRate,
              booksImage: this.booksData.image
          }

  },
  name: 'CoursesList',
  props: ['booksData'], //Props for booksData
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.card {
  background-color: var(--white-color);
  color: #000;
  height: auto;
  border-radius:5px;
  transition: 0.5s ease;

}

.card-description{
background-color: var(--white-color);
color: #000;
height: auto;
border-radius:5px;
border:1px solid var(--white-color);
box-shadow: 0px 0px 2px rgba(0,0,0,0.4);
}

.card-header-title {
    font-size: 1em;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 25px;
    color: var(--black-color);
}

.card-text-description{
font-size: 0.8em;
color:var(--black-color);
display: flex;
justify-content: center;
align-items: center;
padding: 0 30px 0px 30px;
}

#progressbar {
    background-color: var(--grey-color);
    border-radius: 0;
    padding: 3px;
          margin-top: -3.7px;
  }

  #progressbar div {
     background-color: var(--green-color);
     height: 5px;
  }

  .card-button{
  display: flex;
    justify-content: flex-end;
    align-items: center;
    padding: 20px;
  }

  .card-button-margin{
  margin:10px;
  }

  .button {
  background-color: var(--primary-color);
  border: solid 1px var(--primary-color);
  border-radius: 3px;
  box-sizing: border-box;
  box-shadow: inset 0 0 1px #fff;
  color: #fff;
  cursor: pointer;
  display: inline-block;
    font-size: 0.7em;
  height: 34px;
  outline: none;
  padding: 0 25px;
  text-align: center;
  text-decoration: none;
}
.hide {
  display: none;
}
.buttonTransparent{
  background: transparent;
  color:var(--gray-color);;
  border:1px solid var(--light-grey-color);
}

.card:hover {
  transform: scale(1.05);
  box-shadow: 5px 5px 15px rgba(0,0,0,0.6);
}

.card:hover .hide{
   display : block;
 }

 .image{
 position: relative;
  text-align: center;
  color: var(--white-color);
 }
 .top-right {
   position: absolute;
   top: 8px;
   right: 16px;
 }

 .border-due-image{
 border: 1px solid var(--black-color);

 background-color:  rgba(15,23,31, 0.7); /* Black w/opacity/see-through */
display: flex;
padding: 5px;
border-radius: 5px;
 }

 .dueDate{
 display:flex;
 justify-content: center;
 align-items:center;
  font-size: 0.6em;
 }

</style>
