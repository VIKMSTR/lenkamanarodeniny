<script>
    import dayjs from "dayjs";
    let current = dayjs();
    let test = dayjs("2021-09-19");
    let birth = dayjs("1991-09-19");
    let age = current.diff(birth, "year", true);
    let ageInt = age - (age % 1);
    let testAge = test.diff(birth, "year", true);
    console.log(testAge);
    console.log(Number.isInteger(age));
    console.log(Number.isInteger(testAge));
    console.log(testAge % 1 != 0);
    let message = "hi";
    let birthday = false;
    if (Number.isInteger(age)) {
        message = "LENKA MÁ DNES NAROZENINY!";
        birthday = true;
    } else {
        if (age % 1 < 0.25) {
            message = "Lenka má " + ageInt + " let a kousek.";
        } else if (age % 1 > 0.75) {
            message =
                "Lenka má " +
                ageInt +
                " let a za chvíli jí bude o rok více! Začněte chystat dary!";
        } else {
            message = "Lenka má " + ageInt + " let a půl (zhruba).";
        }
    }
</script>

<div>
    <p class="text text-2xl text-blue-400">
        Dnes je {current.format("DD.MM.YYYY")}, což znamená, že {message}
    </p>

    {#if true}
        <!-- {#if birthday} -->
        <div class="another-rainbow rounded-md">
            <p class="text text-6xl text-white p-12 font-black ">
                VŠECHNO NEJLEPŠÍ K {ageInt}. NAROZENINÁM!
            </p>
            <p class="text text-2xl text-white p-12 font-black ">
                Máme* tě rádi :)
            </p>
            <p class="text text-sm text-gray-400">
                * rodina, kamarádi, známí, Viktor, taneční komunita, koně, šneci, psi (kromě Sammyho), kočky (kromě Helmuta),
                opraváři kol a půjčovny lodí.
            </p>
        </div>
    {:else}{/if}
</div>

<style>
    .redblock {
        background-color: red;
    }

    .another-rainbow {
        background: linear-gradient(
            238deg,
            #fd8800,
            #fd008f,
            #9700fd,
            #003dfd,
            #05c7e6,
            #4bd58d
        );
        background-size: 1200% 1200%;
        -webkit-animation: rainbow 30s ease infinite;
        animation: rainbow 30s ease infinite;
    }
    @-webkit-keyframes rainbow {
        0% {
            background-position: 0% 50%;
        }
        50% {
            background-position: 100% 50%;
        }
        100% {
            background-position: 0% 50%;
        }
    }
    @keyframes rainbow {
        0% {
            background-position: 0% 50%;
        }
        50% {
            background-position: 100% 50%;
        }
        100% {
            background-position: 0% 50%;
        }
    }
</style>
