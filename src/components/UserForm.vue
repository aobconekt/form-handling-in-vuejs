<template>
    <div>
        <div class="row">
            <div class="col-md-4 col-md-offset-1">
                <form action="">
                    <div class="form-group">
                        <label for="email"> Email</label>
                        <input 
                            type="text" class="form-control" 
                            name="email" id="email" 
                            v-model="userData.email">
                    </div>
                    <div class="form-group">
                        <label for="password"> Password</label>
                        <input 
                            type="password" class="form-control" 
                            name="password" id="password"
                            v-model="userData.password">
                    </div>
                    <!-- checkbox -->
                    <div class="form-group">
                        <label for="">  Friendship </label>
                            <input 
                                type="checkbox" name="friendship" 
                                value="friendship" id="friendship"
                                v-model="purpose">
                          
                        <label for="">relationship </label>
                            <input 
                                type="checkbox" name="relationship" 
                                value="relationship" id="relationship"
                                v-model="purpose">
                            
                    </div>
                    <!-- radio -->
                    <div class="form-group">
                        <label for="">
                            <input 
                                type="radio" name="male" 
                                value="male" id="male"
                                v-model="gender">
                            Mail
                        </label>
                        <label for="">
                            <input 
                                type="radio" name="female" 
                                value="female" id="female"
                                v-model="gender">
                            Female
                        </label>
                    </div>

                    <div class="form-group">
                        <app-switch v-model="switchData"></app-switch>
                    </div>

                    <div class="form-group">
                        <textarea name="info" id="info" cols="50" rows="5" v-model="info"></textarea>
                    </div>
                    <div class="form-group">
                        <select 
                            name="priority" id="priority"
                            v-model="selectedPriority">
                            <option 
                            v-for="priority in priorities" :selected="priorities == Medium">{{priority}}</option>
                        </select>
                    </div>
                    <button class="btn btn-info" @click.prevent="submitted">Submit</button>
                </form>
            </div>
        <!-- details -->
        <div class="col-md-5 col-md-offset-1" v-if="isSubmitted">
            <div class="col-md-5 col-md-offset-4">
                <h1 class="text-centered">{{ userData.email }}</h1>
                <h3 class="text-centered">{{ userData.password }}</h3>
                <ul class="text-centered">
                    <li v-for="item in purpose"> {{ item }} </li>
                </ul>
                <h5>{{ gender }}</h5>
                <p>{{ info }}</p>
                <h6>{{selectedPriority}}</h6>
                <small>Switch: {{switchData}}</small>
            </div>
        </div>

        </div>
    </div>
</template>

<script>
import Switch from './Switch.vue';
export default {
    data: function(){
        return {
            userData: {
                email:'',
                password:''
            },
            purpose: [],
            gender: 'male',
            info: 'Please drop your comment here',
            selectedPriority: 'Medium',
            priorities: ['High', 'Medium', 'Low'],
            switchData: true,
            isSubmitted: false
        }
    },
    methods: {
        submitted(){
            this.isSubmitted= true;
        }
    },
    components: {
        AppSwitch: Switch
    }
    
}
</script>
