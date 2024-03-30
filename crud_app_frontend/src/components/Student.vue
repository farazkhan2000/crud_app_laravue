<template>
  <div class ="container my-5">
    <h2>Student Registation</h2>
                  <form @submit.prevent="save">
                  
                  <div class="form-group my-4">
                      <label>Student name</label>
                      <input type="text" v-model="student.name" class="form-control"  placeholder="Student name">
                  
                  </div>
                  <div class="form-group mb-4">
                      <label>Student Address</label>
                      <input type="text" v-model="student.address" class="form-control"  placeholder="Student Address">
                  
                  </div>
                  
                  <div class="form-group mb-4">
                      <label>Phone</label>
                      <input type="text" v-model="student.phone" class="form-control"  placeholder="Phone">
                  
                  </div>
                  
                  <button type="submit" class="btn btn-primary mb-4">Add Student</button>
                  </form>


<h2>Employee View</h2>
    <table class="table table-dark">
<thead>
  <tr>
    <th scope="col">ID</th>
    <th scope="col">Student Name</th>
    <th scope="col">Address</th>
    <th scope="col">Phone</th>
    <th scope="col">Option</th>
  </tr>
</thead>
<tbody>
  <tr v-for="student in result" v-bind:key="student.id">
        
        <td>{{ student.id }}</td>
        <td>{{ student.name }}</td>
        <td>{{ student.address }}</td>
        <td>{{ student.phone }}</td>
        <td class="d-flex gap-2">
          <button type="button" class="btn btn-warning" @click="edit(student)">Edit</button>
          <button type="button" class="btn btn-danger"  @click="remove(student)">Delete</button>
        </td>
      </tr>
  
</tbody>

</table>
   
  </div>
</template>
<script>
  
 import axios from 'axios';

export default {
  name: 'Student',
  data () {
    return {
      result: {},
      student:{
                 id: '',
                 name: '',
                 address: '',
                 phone: ''


      }
    }
  },
  created() { 
      this.StudentLoad();
  },
  mounted() {
        console.log("mounted() called.......");
       
    },

  methods: {
         StudentLoad()
         {
               var page = "http://127.0.0.1:8000/api/student";
               axios.get(page)
                .then(
                    ({data})=>{
                      console.log(data);
                      this.result = data;
                    }
                );
         },
         
        
         save()
         {
          if(this.student.id == '')
            {
              this.saveData();
            }
            else
            {
              this.updateData();
            }       

         },
         saveData()
         {
          axios.post("http://127.0.0.1:8000/api/student", this.student)
          .then(
            ({data})=>{
              alert("saveddddd");
              this.StudentLoad();
               this.student.name = '';
                this.student.address = '',
                this.student.phone = ''
                 this.id = ''
            }
          )

         },
         edit(student)
         {
          this.student = student;
         
         },
         updateData()
         {
            var editrecords = 'http://127.0.0.1:8000/api/student/'+ this.student.id;
            axios.put(editrecords, this.student)
            .then(
              ({data})=>{
                this.student.name = '';
                this.student.address = '',
                this.student.phone = ''
                this.id = ''
                alert("Updated!!!");
                this.StudentLoad();
              }
            );

         },

         remove(student){

           var url = `http://127.0.0.1:8000/api/student/${student.id}`;



           // var url = 'http://127.0.0.1:8000/api/student/'+ student.id;
            axios.delete(url);
            alert("Deleteddd");
            this.StudentLoad();
          }
    }
}
</script>