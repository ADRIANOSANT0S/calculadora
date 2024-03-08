<script setup>
    import { reactive, computed  } from 'vue';
    const estado = reactive({ 
        operation: [0, 'add', 0]
    })

    const calcular = computed(() => {
        const [number1, operation, number2] = estado.operation
        switch (operation) {
            case 'add':
                return number1 + number2;
                break;
            case 'subtract':
                return number1 - number2;
            case 'multiply':
                return number1 * number2;
            case 'divide': 
                return number1 / number2;
            default:
                return null;
        }   
    })
</script>

<template>
    <div class="bg-secondary vh-100 d-flex justify-content-center align-items-center">
    <div class="text-white text-center">
        <header class="mb-5">
            <h1>Calculadora</h1>
        </header>
        <div>
            <form action="">
                <div class="row">
                    <div class="col-md-4 mb-4">
                        <input v-model="estado.operation[0]" class="form-control" placeholder="Digite o primeiro valor" type="number" required />
                    </div>
                    <div class="col-md-2 mb-4">
                        <select v-model="estado.operation[1]" class="form-control text-center fw-bold">
                            <option value="add">+</option>
                            <option value="subtract">-</option>
                            <option value="multiply">*</option>
                            <option value="divide">/</option>
                        </select>
                    </div>
                    <div class="col-md-4 mb-4">
                        <input v-model="estado.operation[2]" class="form-control" type="number" placeholder="Digite o segundo valor" required />
                    </div>
                </div>
            </form>
            <div class="fw-bold col text-start">
                <span>O resultado: {{ calcular }}</span>
            </div>
            <div class="mt-5 text-center">
                <a class="link" href="https://github.com/ADRIANOSANT0S/calculadora">Github</a>
            </div>
        </div>
    </div>
</div>

</template>

<style scoped>
    .link {
        color: #fff;
        font-weight: bold;
    }

    .link:hover {
        opacity: .7;
    }
</style>