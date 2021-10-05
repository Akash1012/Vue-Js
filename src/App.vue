<template>
<div>{{greet}} {{name}} </div>
<div v-text="channel"></div>
<div v-html="channel"></div>
<div v-html="hack"></div>
<h2 v-bind:id="headingId">Heading</h2>
<button v-bind:disabled="isDisabled" >Bind</button>
<h2 class="underline">UnderLined Text</h2>
<h2 class="underline" v-bind:class="status">status</h2>
<h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
<h2 v-bind:class="isSoldout ? 'sold-out':'new'">Soldout? movie</h2>
<h2 v-bind:class="['new','promoted']">Newly promoted movie</h2>
<h2 v-bind:class="[isPromoted && 'promoted',  isSoldout ? 'sold-out':'new']">Array conditional Movie</h2>
<h2 v-bind:class="{
    promoted: isPromoted,
    new: !isSoldout,
    'sold-out': isSoldout
}">Object Conditional Movies</h2>


<h2 v-bind:style="{
    color: highlightColor,
    'font-size': headerSize + 'px',
    padding:'20px'
}">Object Inline Style</h2>

<h2 v-bind:style="headerStyleObject">Style Object 2</h2>
<div v-bind:style="[baseStyleObject,successStyleObject,dangerStyleObject]">Success Style</div>

</template>

<script>


export default {
    name:'App',
    data() {
        return {
            greet:'Hello',
            name: 'Akash',
            channel:'<b>CodeWithMe</b>',
            headingId:'heading',
            isDisabled:true,
            status:'danger',
            isPromoted:true,
            isSoldout: true,
            highlightColor:'orange',
            headerSize: 50,
            headerStyleObject: {
                color: 'orange',
                fontSize:'50px',
                padding:'20px'
            },

             baseStyleObject: {
                fontSize:'50px',
                padding:'10px'
            },

             successStyleObject: {
                color: 'green',
                backgroundColor:'lightgreen',
                border:'1px solid green'
            },

           dangerStyleObject: {
                color: 'darkred',
                backgroundColor:'red',
                border:'1px solid darkred'
            },
            hack:`<a href='#' onclick="alert('You have been hacked !')">Win a prize!</a>`
        }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.underline {
    text-decoration: underline;
}

.promoted {
    font-style: italic;
}
.new {
    color:green
}
.sold-out {
    color:red
}
</style>
