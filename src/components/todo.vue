<template>
  <div class="container mt-5">
    <div class="row">
		<div class="card border-light w-75 m-auto">
			<div class="card-body">
				<h4 class="card-title text-center">Enter Todo List</h4>
				<form v-on:submit.prevent="inputHandler">
					<div class="form-group">
					<input type="text" class="form-control text-center" id="exampleInputEmail1" placeholder="Enter your list" v-model="input" @keydown="removeErrors" autocomplete="off">
					<div class="invalid_feedback" v-show="errors.empty">Please enter something and hit enter</div>
					</div>
					<button type="submit" class="btn btn-primary  w-100 btn-md">Submit</button>
				</form>
			</div>
		</div>
    </div>
	<div class="row mt-5">
		<div class="clearfix"></div>
		<div class="list-group w-75 m-auto">
		<a href="#" class="list-group-item list-group-item-action " v-for="(lists,index) in todoList" v-bind:key="index">
			{{lists}} <a href="#" class="btn btn-primary btn-sm text-white float-right" v-on:click="deleteList(index)">X</a>
		</a>
		</div>
	</div>
  </div>
</template>

<script>
export default {
  name: 'todo',
  data () {
    return {
		input: "",
		todoList: [],
		errors: {
			empty: false
		},
		is_invalid: false
    }
  },
  methods: {
	  inputHandler: function() {
		  if(this.input.length == 0) {
			  this.errors.empty = true;
			  this.is_invalid = true;
			  return false;
		  } else {
			  if(this.todoList.indexOf(this.input) !== -1) {
				  alert("task already exist");
			  } else {
			  this.todoList.unshift(this.input);
			  }
		  }
	  },
	  deleteList: function(index) {
		  this.todoList.splice(index,1);
	  },
	  removeErrors: function() {
		  this.errors.empty = false;
		  this.is_invalid = false;
	  }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.invalid_feedback {
	color:red;
}
.is-invalid {
	box-shadow: inset 0 -2px 0 #e51c23;
}
</style>
