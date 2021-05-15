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
</div>
</template>


<script>
export default {
    data: () => ({
operand1: 0,
operand2: 0,
result: 0
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
