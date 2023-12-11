<script lang="ts">
    let result_1: string = 'Да/Нет';
    let num_1: any;
    let var_2: any = '';
    let var_3: any = 0;

    function handler_1 () {
        if (num_1 <= 1) {
            result_1 = 'нет';
            return;
        }
        if (num_1 === 2) {
            result_1 = 'да'
            return;
        }

        // Проверка деления на числа от 2 до квадратного корня из num
        for (let i = 2; i <= Math.sqrt(num_1); i++) {
            if (num_1 % i === 0) {
                result_1 = 'нет';
                return;
            }
        }

        result_1 = 'да';
        return;
    }

    function handler_2 () {
        let count = 0;

        switch (var_3) {
            case '1':
                count = (var_2.match(/[aeiou]/gi) || []).length;
                break;
            case '2':
                count = (var_2.match(/[bcdfghjklmnpqrstvwxyz]/gi) || []).length;
                break;
            case '3':
                count = (var_2.match(/\d/g) || []).length;
                break;
            case '4':
                count = (var_2.match(/\w+/g) || []).length;
                break;
        }

        alert(`Результат: ${count}`);
    }
</script>

<style>
    .cont {
        background-color: dimgray;
        width: 900px;
        height: 600px;
        display: flex;
        color: black;
    }

    .column-1 {
        display: flex;
        flex-direction: column;
        flex: 1;
        border-right: 3px dotted grey;
    }

    .column-2 {
        display: flex;
        flex-direction: column;
        flex: 1;
    }

    .block-1 {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        border-bottom: 1px solid black;
        height: 230px;
        padding-top: 25px;
        padding-right: 40px;
    }
    .block-2 {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        border-bottom: 1px solid black;
        height: 320px;
        padding: 5px 20px;
    }

    .block-3 {
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        height: 100%;
        width: 100%;
    }

    .block-4 {
        display: flex;
        height: 400px;
        width: 100%;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
        border-bottom: 1px solid black;
    }

    .block-5 {
        display: flex;
        height: 100%;
        width: 100%;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
    }

    button {
        background-color: lightgray;
        color: black;
        height: 30px;
    }
</style>

<div class="cont">
    <div class="column-1">
        <div class="block-1">
            <div style="display: flex; justify-content: space-between">
                <input bind:value={num_1} placeholder="ваше число">
                <p>Результат: {result_1}</p>
            </div>
            <button on:click={handler_1}>проверить простое число или нет</button>
        </div>

        <div class="block-2">
            <input value={var_2} placeholder="Введите строчку">

            <select bind:value={var_3}>
                <option value="1">посчитать кол-во гласных</option>
                <option value="2">посчитать кол-во согласных </option>
                <option value="3">посчитать кол-во цифр </option>
                <option value="4">посчитать кол-во слов </option>
            </select>

            <button on:click={handler_2}>посчитать</button>
        </div>

        <div class="block-3">
            <div>
                <input type="checkbox" name="babybe" checked />
                <label for="scales">цифры</label>

                <input type="checkbox" name="babybe" />
                <label for="horns">спец символы</label>

                <input type="checkbox" name="babybe" />
                <label for="horns">заглавные латинские буквы</label>

                <input type="checkbox" name="babybe" />
                <label for="horns">прописные латинские буквы</label>
            </div>
            <button>сгенерировать рандомный пароль</button>
            <p>Рандомный пароль</p>
        </div>
    </div>


    <div class="column-2">
        <div class="block-4">
            <div>
                <input placeholder="число один">

                <input placeholder="число два">
            </div>

            <div style="display: flex; justify-content: space-around; width: 100%">
                <div style="width: 60px">
                    <input type="radio" name="bebra" value="louie" />
                    <label for="louie">сумма</label>
                    <input type="radio" name="bebra" value="louie" />
                    <label for="louie">умножение</label>
                </div>

                <div style="width: 60px">
                    <input type="radio" name="bebra" value="louie" />
                    <label for="louie">разница</label>
                    <input type="radio" name="bebra" value="louie" />
                    <label for="louie">деление</label>
                </div>
            </div>

            <button style="width: 70%;">посчитать</button>

        </div>

        <div class="block-5">
            <div>
                <input placeholder="первое число">
                <input placeholder="второе число">
                <input placeholder="третье число">
                <input placeholder="четвертое число">
                <input placeholder="пятое число">
                <input placeholder="шестое число">
            </div>

            <button style="width: 70%">создать массив</button>
            <button style="width: 70%">сумма элементов</button>
            <button style="width: 70%">произведение элементов</button>

            <div style="display: flex; justify-content: space-between; width: 70%">
                <button style="width: 45%">мин элемент</button>
                <button style="width: 45%">макс элемент</button>
            </div>

        </div>
    </div>
</div>
