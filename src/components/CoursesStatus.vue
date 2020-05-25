<template>
  <div class="content">
<!-- Tabs -->
<div class="filters">
   <span class="filter">To Do
   <span class="badgeCount">10</span>
   </span>
   <span class="filter">In Progress
    <span class="badgeCount">40</span>
   </span>
   <span class="filter">Completed
 <span class="badgeCount">50</span>
   </span>
    <span class="filter">All Courses
    <span class="badgeCount">89</span>
    </span>
 </div>

 <!-- Search and Filter -->
 <div class="container">
   <div class="item filterSearch"><input type="search" class="inputSearchBox searchBox" name="searchCourse" placeholder="Search Course" /></div>
   <div class="item filterSearchtext"><span class="searchTextmatch"><strong>23</strong> of 98 courses matches your search</span></div>
   <div class="item filterSortByIcon"><i class="material-icons">sort</i>Sort By</div>
   <div class="item filterSelect">
   <div class="selectbox2">
   <select>
    <option value="enrolled">Date Enrolled</option>
    <option value="category">Category</option>
  </select>
</div>
</div>

 </div>

<!-- End of Search and Filter -->
<div class="cards">
<div  v-bind:key="books.id" v-for="books in booksToDisplay">
  <CoursesList :books-data="books"> </CoursesList> </div>
  </div>
  </div>
</template>

<script>
import CoursesList from './CoursesList'
import Books from '../data-json.json'
export default {
  name: 'CoursesStatus',
  data () {
      return {
      books:[],
      }
    },
  components: {
    CoursesList
  },
  computed: {
  booksToDisplay: function () {

  // return books data. This can be later replaced with an API
    return this.books;
  }
  },
  created() {
  //assigning the value for Books;
      this.books =  Books;
    }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

/** FILTERS **/

.filters {
  display: flex;
  padding: 5px 10px;
	box-shadow:1px 6px 3px 0px var(--light-grey-color);
}
.filter {
  padding:10px;
	cursor:pointer;
	border-radius: 6px;
	transition: all 0.35s;
  color: var(--gray-color);
  font-weight: bold;
  font-size: 0.7em;
  margin: 0px 20px;
}

.filter.active {
box-shadow:1px 6px 3px 0px var(--light-grey-color);

}
.filter:hover {
  color:#000;
  border-radius: 0px;
  border-bottom: 3px solid var(--primary-color);

}

.filterSearch{
display: flex;
align-items: center;
}

.filterSearchtext{
display: flex;
align-items: center;
justify-content:flex-start;
}

.filterSearch{
display:flex;
justify-content: flex-start;
align-items:center;
}

.filterSort{
display:flex;
justify-content: flex-start;
align-items:center;
}

.filterSortBy{
display:flex;
justify-content: flex-end;
align-items:center;

}

.badgeCount {
display: inline-block;
min-width: 16px;
padding: 2px 3px;
border-radius: 3px;
font-size: 1em;
text-align: center;
background: var(--gray-color);
color: var(--white-color);


}
.filter:hover .badgeCount{
border: 1px solid var(--gray-color);
background: var(--primary-color);

}
/** FILTERS **/

/** SEARCH BOX **/
.searchBox {
background-image: url('../assets/search-24px.svg');
background-size: 20px 20px;
background-repeat: no-repeat;
background-position: left;
padding-right: 40px !important;
padding-top: 2px !important;
padding-bottom: 2px !important;
padding-left: 25px !important;
border: none;
height: 30px;
color:#000;
}

.inputSearchBox{
  background-color: var(--light-grey-color);
  border-radius:25px;
  margin:30px;
  &::placeholder {
    color: var(--light-grey-color);
     opacity: 1; /* Firefox */
  }
}

.searchTextmatch{
font-size: 0.7em;
}
/** SEARCH BOX **/

/** CONTAINER WITH SEARCH **/

.container {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: 100px;
  grid-gap: 5px;
}

.item {
  text-align: center;
}

.filterSortByIcon{
  display:flex;
  justify-content:flex-end;
  align-items:center;
      font-size: 0.7em;
      color:#B8C0C7;
      font-weight:bold;
}

.filterSelect{
display: flex;
    justify-content: flex-start;
    align-items: center;
    padding: 10px;

}

.selectbox2 {
    border: 1px solid var(--primary-color);
    border-radius: 3px;
    overflow: hidden;
    width:150px;
    background: #446cfc url("http://3.bp.blogspot.com/-PxvUdThV3hk/VFHNy_3HMxI/AAAAAAAACqQ/U1xOPHn-hxo/s1600/ic_arrow_drop_down_48px-32-2.png") no-repeat 90% 50%;
}

.selectbox2 select {
    padding: 5px 8px;
    width: 100%;
    border: none;
    box-shadow: none;
    background: transparent;
    background-image: none;
    -webkit-appearance: none;
     color: var(--black-color);
     font-size: 0.7em;
}

.selectbox2 select:focus {
    outline: none;
}

/** CONTAINER **/

/** CARDS **/

.cards {
  max-width: 1200px;
  margin: 0 auto;
  display: grid;
  grid-gap: 1rem;
  padding:10px;
  border-radius:5px;
}

@media (min-width: 320px) {
  .cards { grid-template-columns: repeat(1, 1fr); }
  .container { grid-template-columns: repeat(2, 1fr); grid-auto-rows: 50px; }
  .filterSortByIcon { justify-content: flex-end}
      .filter {margin:0px}
}

@media (min-width: 480px) {
  .cards { grid-template-columns: repeat(2, 1fr); }
  .container { grid-template-columns: repeat(2, 1fr); grid-auto-rows: 50px; }
  .filterSortByIcon { justify-content: flex-end}
      .filter {margin:0px}
}

@media (min-width: 600px) {
  .cards { grid-template-columns: repeat(2, 1fr); }
  .container { grid-template-columns: repeat(2, 1fr); grid-auto-rows: 50px; }
  .filterSortByIcon { justify-content: flex-end}
  .filter {margin:0px}


}
@media (min-width: 900px) {
  .cards { grid-template-columns: repeat(3, 1fr); }
  .container { grid-template-columns: repeat(4, 1fr); }
  .filter {margin:0px 20px}

}

/** CARDS **/

</style>
