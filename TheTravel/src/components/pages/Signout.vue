<template>
  <div>
      <a href="#" @click.prevent="signout">登出</a>
  </div>
</template>

<script>
export default {
  data () {
    return {

    };
  },

  methods:{
    signout(){    
        const api = `${process.env.APIPATH}logout`;
        const vm = this;
        this.$http.post(api).then((response) => {
        console.log(response.data);
        if(response.data.success){
            vm.$router.push('/login'); //如果登入成功進入這
        }
        });
    },
  },
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css?family=Open+Sans+Condensed:700');
section{
    height: 100vh;
    width: 100%;
    background-image: url('https://images.unsplash.com/photo-1550010565-d20b4cb367b4?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80');
    background-size: cover;
}

.container{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%,-50%);
    width: 340px;
    text-align: center;
}

.login-form{
    position: relative;
    box-sizing: border-box;
    padding: 60px 10px; 
    transition: .5s
}

.login-form:hover{
    background: rgba(255, 255, 255, .1);
    box-shadow: 0 0 20px rgba(0, 0, 0, .2);
    
}

.login-form h1{
    margin: 0 0 20px;
    color: #fff;
    font-size: 30px;

}


.login-form input{
    display: block;
    width: 100%;
    padding: 10px 20px;
    box-sizing: border-box;
    margin-bottom: 20px;
    border-radius: 25px;
    outline: none;
    font-size: 14px;
    letter-spacing: 1px;
    color: #fff;
    border: none;
    background: rgba(255, 255, 255, .1);
    font-family: 'Open Sans Condensed', sans-serif;


}

.login-form input::placeholder{
    color: #fff;
}

.login-form input[type="button"]
{
    color: #fff;
    background: #0072ff;
    font-size: 16px;
    border: none;
    cursor: pointer;
}

.text{
    color: #fff;
    font-family: 'Open Sans Condensed', sans-serif;

}
</style>


