<template>
    <div>
        <h1 class="center wow animate__backInRight">Animate.js & Vue.js</h1>
        <h2 class="center">move.js</h2>
        <div class="square"></div>
        <button @click="doPlay">play</button>
    </div>
</template>

<script>
import move from 'move-js'
// 如果想要用jquery
// move.select = function(selector){
//     return $(selector).get(0);
// };
export default {
    name: 'Home',
    components: {},
    methods: {
        doPlay() {
            move('.square')
                    .set('background-color', 'blue')
                    .duration('4s')
                    .end(function(){
                        move('.square')
                            .set('background-color', 'red')
                            .end()
                    });
        }
    },
    mounted() {

    }
}
</script>

<style lang="scss" scoped>
.center {
    color: #b6a7ff;
    text-align: center;

}

.square {
    width: 50px;
    height: 50px;
    //background-color: #b6a7ff;
}
</style>
