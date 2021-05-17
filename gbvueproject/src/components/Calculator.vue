<template>
  <div class="hello">
    <input v-model.number="operand1" />
    <input  v-model.number="operand2" />
    = {{ result }}
   <div>
    <button @click="calculate('+')" id="sum">+</button>
    <button @click="calculate('-')" id="sub">-</button>
    <button @click="calculate('/')" id="div">/</button>
    <button @click="calculate('*')" id="mul">*</button>
    <button @click="calculate('x^n')" id="exp">x^n</button>
    <button @click="calculate('//')" id="divv">//</button>
 </div>
 



<div v-show="visible">
       <input type="checkbox" id="checkbox" v-on:click="visible=!visible">{{visible?'Скрыть экранную клавиатуру':'Отобразить экранную клавиатуру'}}
    </div>
   

 


<div>
  <button v-for="button in buttons" :key="button.number"> 
    {{ button.number }}
   </button>
 <button> ← </button>

</div>


<div>
   
<input type="radio" id="one" value="Первое значение" v-model.number="operand1">
<label for="one">Операнд 1</label>

<input type="radio" id="two" value="Второе значение" v-model.number="operand2">
<label for="two">Операнд 2</label>

 </div>

</div>


 

</template>



<script>
export default {
    data: () => ({
operand1: 0,
operand2: 0,
result: 0,
buttons: [
   { number: 0 } ,
   { number: 1 } ,
   { number: 2 } ,
   { number: 3 } ,
   { number: 4 } ,
   { number: 5 } ,
   { number: 6 } ,
   { number: 7 } ,
   { number: 8 } ,
   { number: 9 } ,
    ],
    visible: true, 
//checked,
//picked,
    }),
props: {
    },

    methods: {

calculate (operation) {
 
       switch (operation) {
            case '+':
            this.result = this.operand1 + this.operand2;
            break;
           
            case '-':
            this.result = this.operand1 - this.operand2;
             break;

            case '/':
           this.result = this.operand1 / this.operand2;
            break;

            case '*':
            this.result = this.operand1 * this.operand2;
             break;
            
            case 'x^n':
            this.result = this.operand1 ** this.operand2;
             break;

            case '//':
            this.result = Math.trunc(this.operand1 / this.operand2);
             break;

            default:
            alert( 'Неизвестное значение' );

        }

  
  
    },


    
    }

}
   
</script>

   
 <style scoped>
h3 {
     margin: 40px 0 0;
}
ul {
    list-style-type: none;
    padding: 0;
}


  </style>
