<template>

 <img :src="ImagePath" :style="{
  height: '50px',
  width: '50px',
 }">

  <svg :view-box.camel="viewBox" style="background-color:teal;"></svg>

  <h2>{{ name }} - {{ age }}&nbsp;</h2>
  <h2 v-html="province"></h2>
  <h2 v-text="country"></h2>
  <h2 v-bind:id="headingId">Heading title</h2>
  <select>
    <option>Select . .. </option>
    <option>Java</option>
    <option >PHP</option>
    <option v-bind:selected="isSelected">Javascript</option>
  </select>

  <input :checked="IsChecked" :type="IsSubmit" :name="IsName">&nbsp;check me
  <button v-bind:disabled="IsDisabled">Click me</button>
  <input :readonly="ReadOnlys" value="texting">
  <input :placeholder="IsValued">
  <h2 v-bind:class="isProgrammer ? 'isProgrammer' : 'IsnotProgrammer'">Bikman is Programmer</h2>
  <h2 v-bind:class="isPromoted && 'promoted'">IsPromoted Movie</h2>
  <h1 v-bind:class="isSoldOut ? 'sold_out':'new'">Sold movies</h1>
  <h2 class="underline" v-bind:class="status">Status</h2>
  <h2 v-bind:style="{
    color: HighLightColor,
    'font-size': textSize + 'px',
    padding: '20px'
  }">Main title</h2>

  <h2 :class="['new','promoted']">Newly promoted movie</h2>
  <h2 :class="[isPromoted && 'promoted',isSoldOut ? 'sold_out':'new']">Array condition class</h2>
  <h2 :class="{
    promoted:isPromoted,
    new:!isSoldOut,
    'sold_out':isSoldOut
  }">Object condition class</h2>

 <a :href="LinkPath" :target="OpenLinkNewTab">{{ linkname }}</a>
 <br>
 <div>Comment --End of vew binding--</div>

 <br>
 <br>
 <div>Comment --Start of part two Condition Randering--</div>
    <h2 v-if="num === 0">Number is Zero {{ num }}</h2>
    <h2 v-else-if="num > 0">Number is Positive {{ num }}</h2>
    <h2 v-else-if="num < 0">Number is Negative {{ num }}</h2>
    <h2 v-else>Input not a number {{ num }}</h2>

    <div v-if="display">
      <h2>Java</h2>
      <h2>PHP</h2>
      <h2>Javascript</h2>
    </div>

    <div v-if="displayDB">
      <h2>SQL</h2>
      <h2>MariaDB</h2>
      <h2>PostGred</h2>
    </div>

    <h2 v-show="showElement">V-show element in VueJS</h2>

 <div>Comment --End of part two Condition Randering--</div>
 <br><br>
 <div>Comment --Start of part three List Randering--</div>
    <h2 v-for="name in names" :key="name">{{ name }}</h2>
 <div>Comment --End of part three List Randering--</div>

 <br>
 <br>

 <div>Comment --- Start of methods ---</div>
 <h2>Add number {{ add() }}</h2>
 <h2>myltiply : {{myltiply(10)}}</h2>
 <h2>Substracting : {{ substract(subValue) }}</h2>
 <div>Comment --- End of methods ---</div>
</template>


<script>
  export default{
    name:'App',
    data(){
      return {
        name: 'Bikman',
        age: '29',
        province: '<b>Western</b>',
        headingId: 'heading',
        country: 'Rwanda',
        IsDisabled: true,
        isProgrammer: true,
        HighLightColor: 'orange',
        textSize: 50,
        status: 'success',
        isPromoted: true,
        isSoldOut: true,
        isSelected: true,
        IsChecked: true,
        IsSubmit: 'checkbox',
        IsName: 'SubmitData',
        IsValued: 'Enter name',
        ReadOnlys: true,
        LinkPath: 'http://wa.me/+250784287668',
        OpenLinkNewTab: '_blank',
        linkname: 'adibe tsap',
        ImagePath: '/favicon.ico',
        viewBox: '0 0 1500 1000',
        VieBoxBGColor: 'bgcolor',

        num: "hey",
        display: true,
        displayDB: true,
        showElement:false,

        names: ['Java','Php','Python'],

        multiplyNumber: 20,

        substractNumber: 100,

        subValue:22
      }
    },

    methods: {
        add(){
            return 5+90
        },

        myltiply(num){
            return num * this.multiplyNumber
        },

        substract(a){
            return a - this.substractNumber
        }

    }
  } 

</script>

<style>
#app{
  
  font-family:Alvenir,helvetica,Arial,sans-serif;
  -webkit-font-smoothing:antialiased;
  -moz-osx-font-smooothing:grayscale;
  text-align:center;
  color:#2c3e50;
  margin-top:60px;
}
.isProgrammer{
  color:blue;
}

.underline{
  text-decoration:underline;
}

.new{
  color:green;
}

.promoted{
  font-family:san-serif;
}

.sold_out{
  color:red;
}
</style>
