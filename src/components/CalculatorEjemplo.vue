<template>

    <div class="h-screen bg-blue-800 flex justify-center py-16">
        <div class="w-1/3">
            <!-- cabecera de la calucladora -->
            <div class="p-4 text-right shadow-2xl rounded-t-lg bg-white">
                <p class="font-semibold text-gray-700 h-6">{{getOperacion}}</p>
                <p class="font-bold text-3l text-gray-900 my-2">{{getResultado}}</p>
            </div>
            <!-- 
            botones -->
            <div class="grid grid-cols-4 grid-rows-5 shadow-2xl rounded-d-lg">

                <button class="h-16 text-xl text-qhite font-semibold bg-green-500
                border-green-400  hover:bg-green-600" @click="clickAC()">AC</button>

                <button class="h-16 text-xl text-qhite font-semibold bg-green-500
                border-green-400 hover:bg-green-600" @click="clickDel()">DEL</button>

                <button class="h-16 text-xl text-qhite font-semibold bg-green-500
                border-green-400 hover:bg-green-600" @click="click('.')">.</button>
                <button class="h-16 text-xl text-qhite font-semibold bg-blue-600
                border-gray-300 hover:bg-gray-300" @click="click('÷')"> ÷</button>

                <button class="h-16 text-xl text-qhite font-semibold bg-yellow-500
                border-green-400 hover:bg-yellow-600" @click="click('7')">7</button>
                <button class="h-16 text-xl text-qhite font-semibold bg-yellow-500
                border-green-400 hover:bg-yellow-600"  @click="click('8')">8</button>
                <button class="h-16 text-xl text-qhite font-semibold bg-yellow-500
                border-green-400 hover:bg-yellow-600" @click="click('9')">9</button>
               <button class="h-16 text-xl text-qhite font-semibold bg-blue-600
                border-gray-300 hover:bg-gray-300" @click="click('x')"> x</button>

                <button class="h-16 text-xl text-qhite font-semibold bg-yellow-500
                border-green-400 hover:bg-yellow-600"  @click="click('4')">4</button>
                <button class="h-16 text-xl text-qhite font-semibold bg-yellow-500
                border-green-400 hover:bg-yellow-600" @click="click('5')">5</button>
                <button class="h-16 text-xl text-qhite font-semibold bg-yellow-500
                border-green-400 hover:bg-yellow-600" @click="click('6')">6</button>
                <button class="h-16 text-xl text-qhite font-semibold bg-blue-600
                border-gray-300 hover:bg-gray-300" @click="click('-')"> -</button>

                <button class="h-16 text-xl text-qhite font-semibold bg-yellow-500
                border-green-400 hover:bg-yellow-600" @click="click('3')">3</button>
                <button class="h-16 text-xl text-qhite font-semibold bg-yellow-500
                border-green-400 hover:bg-yellow-600" @click="click('2')">2</button>
                <button class="h-16 text-xl text-qhite font-semibold bg-yellow-500
                border-green-400 hover:bg-yellow-600" @click="click('1')">1</button>
               <button class="h-16 text-xl text-qhite font-semibold bg-blue-600
                border-gray-300 hover:bg-gray-300" @click="click('+')"> +</button>

                <button class="h-16 text-xl text-qhite font-semibold bg-yellow-500
                border-green-400 hover:bg-yellow-600" @click="click('0')">0</button>
                <button class="h-16 text-xl text-qhite font-semibold bg-blue-600
                border-gray-300 hover:bg-gray-300" @click="click('%')"> %</button>
                <button class="h-16 text-xl text-qhite font-semibold bg-blue-600
                border-gray-300 hover:bg-gray-300" @click="click('^')"> mⁿ</button>
                <button class="h-16 text-xl text-qhite font-semibold bg-blue-600
                border-gray-300 hover:bg-gray-300"  @click="clickResultado()"> =</button>

            </div>

        </div>
    </div>
</template>

<script>
export default {
data(){
    return{
        getOperacion:'',
        getResultado:'0',
    }
},





methods:{

clickAC(){
    this.getResultado='0';
    this.getOperacion='0';
},


clickDel(){
   if (this.getResultado.length > 1) {
       this.getResultado=this.getResultado.substring(0,this.getResultado.length-1);

       
   } else {
       this.getResultado='0';
       
   }
},


    click(par){
   
   if (this.getResultado=='0') {
       this.getResultado=par;
   } else {
      this.getResultado+=par; 
   }
    },


clickResultado(){
    let operacion=this.getResultado;
    this.getOperacion=operacion;

operacion=operacion.replace('x','*');
operacion=operacion.replace('÷','/');
operacion=operacion.replace('^','**');
this.getResultado=eval(operacion);


}

}




};




</script>
<style>
button {
  border: 2px solid;
}
</style>


