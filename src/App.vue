<template>
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
        IsValued: 'Enter name'
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
