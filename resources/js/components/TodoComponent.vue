<template>
    <div class="container">
        <form @submit.prevent="saveTodo">
            <div class="input-group mb-3 w-100">
                <input v-model="form.title"
                    type="text" class="form-control form-control-lg"
                    placeholder="Enter your plan here..." aria-label="Recipient's username"
                    aria-describedby="button-addon2" required
                >
                <div class="input-group-append">
                    <button class="btn btn-success btn-add"
                        type="submit" id="button-addon2"
                    >
                        +
                    </button>
                </div>
            </div>
        </form>
        <div class="align-items-center p-3 bg-white border-bottom">
            <span class="mr-2">
                <svg
                    xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-circle"
                    width="36" height="36" viewBox="0 0 24 24" stroke-width="1.5" stroke="#FFC107"
                    fill="none" stroke-linecap="round" stroke-linejoin="round"
                >
                    <path stroke="none" d="M0 0h24v24H0z"/>
                    <circle cx="12" cy="12" r="9" />
                </svg>
                <svg
                    xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-circle-check"
                    width="36" height="36" viewBox="0 0 24 24" stroke-width="1.5" stroke="#4CAF50" fill="none"
                    stroke-linecap="round" stroke-linejoin="round"
                >
                    <path stroke="none" d="M0 0h24v24H0z"/>
                    <circle cx="12" cy="12" r="9" />
                    <path d="M9 12l2 2l4 -4" />
                </svg>
            </span>
            <div class="overtext font-weight-bolder">
                Something
            </div>
            <span class="mr-2 ml-2">
                <svg class="svg-custom" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink"
                    aria-hidden="true" focusable="false" width="1.4em" height="1em"
                    style="-ms-transform: rotate(360deg); -webkit-transform: rotate(360deg); transform: rotate(360deg);"
                    preserveAspectRatio="xMidYMid meet" viewBox="0 0 1792 1280" data-toggle="modal"
                    data-target="#exampleModalCenter"
                >
                <path d="M1664 704q-152-236-381-353q61 104 61 225q0 185-131.5 316.5T896 1024T579.5 892.5T448 576q0-121
                    61-225q-229 117-381 353q133 205 333.5 326.5T896 1152t434.5-121.5T1664 704zM944 320q0-20-14-34t-34-14q-125
                    0-214.5 89.5T592 576q0 20 14 34t34 14t34-14t14-34q0-86 61-147t147-61q20 0 34-14t14-34zm848 384q0 34-20
                    69q-140 230-376.5 368.5T896 1280t-499.5-139T20 773Q0 738 0 704t20-69q140-229 376.5-368T896 128t499.5
                    139T1772 635q20 35 20 69z" fill="#626262"/>
                </svg>
            </span>
            <span class="mr-2">
                <!-- <svg alt="Add description" data-toggle="modal" data-target="#exampleModal"
                    class="svg-circleplus" viewBox="0 0 100 100"
                >
                <circle cx="50" cy="50" r="45" fill="none" stroke-width="7.5"></circle>
                <line x1="32.5" y1="50" x2="67.5" y2="50" stroke-width="5"></line>
                <line x1="50" y1="32.5" x2="50" y2="67.5" stroke-width="5"></line>
                </svg> -->
                <svg
                    xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-edit"
                    width="36" height="36" viewBox="0 0 24 24" stroke-width="1.5" stroke="#FFC107"
                    fill="none" stroke-linecap="round" stroke-linejoin="round"
                >
                    <path stroke="none" d="M0 0h24v24H0z"/>
                    <path d="M9 7 h-3a2 2 0 0 0 -2 2v9a2 2 0 0 0 2 2h9a2 2 0 0 0 2 -2v-3" />
                    <path d="M9 15h3l8.5 -8.5a1.5 1.5 0 0 0 -3 -3l-8.5 8.5v3" />
                    <line x1="16" y1="5" x2="19" y2="8" />
                </svg>
            </span>
            <!-- <span class="mr-2">
                <svg
                    xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-edit"
                    width="36" height="36" viewBox="0 0 24 24" stroke-width="1.5" stroke="#FFC107"
                    fill="none" stroke-linecap="round" stroke-linejoin="round"
                >
                    <path stroke="none" d="M0 0h24v24H0z"/>
                    <path d="M9 7 h-3a2 2 0 0 0 -2 2v9a2 2 0 0 0 2 2h9a2 2 0 0 0 2 -2v-3" />
                    <path d="M9 15h3l8.5 -8.5a1.5 1.5 0 0 0 -3 -3l-8.5 8.5v3" />
                    <line x1="16" y1="5" x2="19" y2="8" />
                </svg>
            </span>
            <span class="mr-2">
                <svg
                    xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-checkbox"
                    width="36" height="36" viewBox="0 0 24 24" stroke-width="1.5" stroke="#4CAF50"
                    fill="none" stroke-linecap="round" stroke-linejoin="round"
                >
                    <path stroke="none" d="M0 0h24v24H0z"/>
                    <polyline points="9 11 12 14 20 6" />
                    <path d="M20 12v6a2 2 0 0 1 -2 2h-12a2 2 0 0 1 -2 -2v-12a2 2 0 0 1 2 -2h9" />
                </svg>
            </span> -->
            <span>
                <svg
                    xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-trash ml-1"
                    width="36" height="36" viewBox="0 0 24 24" stroke-width="1.5" stroke="#FF5722"
                    fill="none" stroke-linecap="round" stroke-linejoin="round"
                >
                    <path stroke="none" d="M0 0h24v24H0z"/>
                    <line x1="4" y1="7" x2="20" y2="7" />
                    <line x1="10" y1="11" x2="10" y2="17" />
                    <line x1="14" y1="11" x2="14" y2="17" />
                    <path d="M5 7l1 12a2 2 0 0 0 2 2h8a2 2 0 0 0 2 -2l1 -12" />
                    <path d="M9 7v-3a1 1 0 0 1 1 -1h4a1 1 0 0 1 1 1v3" />
                </svg>
            </span>
        </div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                todos: '',
                change_id: false,
                show_id: false,
                confirm: false,
                form: new Form({
                    title: '',
                    description: ''
                }),
            }
        },
        methods: {
            deleteTodo(e){
                let data = new FormData();
                data.append('_method', 'DELETE');
                if (confirm){
                    axios
                        .post('/todo/' + e.id, data)
                        .then(res => {
                            this.todos = res.data;
                        })
                        .catch(err => {
                            console.log(err.response.data);
                        })
                }
            },
            getTodos(){
                axios
                    .get('/todo')
                    .then(res => {
                        this.todos = res.data;
                    })
                    .catch(err => {
                        console.log(err.response.data);
                    })
            },
            saveTodo(){
                let data = new FormData;
                if (this.form.title.length < 3)
                {
                    console.log('The title must be at least 3 characters');
                    return false;
                }
                data.append('title', this.form.title);
                axios.post('todo', data)
                    .then(res => {
                        if(response.data.status == 'error'){ alert(response.data.msg); }
                        else{this.form.reset();this.getTodos();}
                    })
                    .catch(err => {
                        console.log("ERROR: " + err.response.data);
                    })
            }
        },
        mounted(){
            this.getTodos()
        }
    }
</script>
