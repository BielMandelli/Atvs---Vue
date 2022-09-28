<template>
 <div class="container">
    <div class="row">
      
      <div class="col-md-6w">
        <a><img alt="Vue logo" src="./assets/dio.gif"/>
      </a></div>
      <!-- fim da imagem -->

      <div class="col-md-7">

            <h1>Bem vindo a Dio's Pizzaria!</h1>
            <p>
              Faça seu pedido imediatamente e ele chegará tão rápido que o tempo parece ter sido parado.
            </p>

            <div class="mb-3">
              <label class="form-label" style="color:BLACK">Quantidade de Adultos:</label>
              <input class="form-control" type="text" v-model="qntdA"/>
            </div>
            <div>
              <label class="form-label" style="color:BLACK">Quantidade de Crianças:</label>
              <input class="form-control" type="text" v-model="qntdC"/>
            </div>
            <button class="btn btn-primary btn-saf mt-3" v-on:click="calcular()">Realizar pedido</button>

      </div>
      <!-- fim do formulário -->

    </div>

    <div class="row">
      <div class="offset-md-4 col-md-8">
        <!-- area para exibir as variáveis -->
        <div v-if="dia != null && anjeza == 0">
          <p>Anotando pedido</p>
        </div>
          <div>
        <p>Você irá precisar de {{pizzagg}} Pizzas GG, {{pizzag}} Pizzas G, {{pizzam}} Pizzas M</p>
           

        
      </div>
    </div>

  </div>
  </div>
</template>


<script>
export default {
    name: 'App',
    data(){
        return{
            qntdA: 0,
            qntdC: 0,
            a:0,
            C:0,
            pizzagg : 0,
            pizzag : 0,
            pizzam : 0,
      }
    },

    methods : {
        calcular(){
            let sobra;
            
            this.a = this.qntdA * 3;
            this.c = this.qntdC * 2;
            let total = (this.a) + (this.c);
            this.pizzagg = parseInt(total / 12);
            sobra = total % 12;
            this.pizzag= parseInt(sobra / 10);
            sobra = total % 10;
             this.pizzam = parseInt(sobra / 8);
            sobra = sobra % 8;
            if(sobra > 0){
                this.pizzam++;
            }
        }
    }
  }
</script>

<style>
	@import "https://cdn.jsdelivr.net/npm/bootstrap@5.2.1/dist/css/bootstrap.min.css";
</style>
