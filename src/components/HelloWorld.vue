<template>
    <div class="hello">
        <KForm :model="form" :rules="rules">
            <KFormItem label="用户名">
                <KInput v-model="form.name"></KInput>
            </KFormItem>
            <KFormItem label="密码">
                <KInput type="amount" v-model="form.password" ></KInput>
            </KFormItem>
        </KForm>
    </div>
</template>

<script>
    import KInput from "./KInput";
    import KFormItem from "./KFormItem";
    import KForm from "./KForm";
    export default {
        name: 'HelloWorld',
        components: {
            KInput,
            KFormItem,
            KForm
        },
        props: {
            msg: String
        },
        data() {
            return {
                form: {
                    name: "",
                    password: ""
                },
                rules:{
                    name: [{required:true,message:"请输入用户名"}],
                    password: [{required:true,message:"请输入密码"}]
                }
            }
        },
        methods: {
            handleInput(value1, value2) {
                console.log(this, value1, value2)
            }
        }
    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    h3 {
        margin: 40px 0 0;
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
</style>
