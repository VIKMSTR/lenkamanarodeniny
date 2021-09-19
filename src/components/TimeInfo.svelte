<script>
    import dayjs from "dayjs";
    let current = dayjs();
    let birth = dayjs("1991-09-19");
    let age = current.diff(birth, "year", true);
    let ageInt = age - (age % 1);
    let daysTillNextBirthday = 0
    if (current.isBefore(`${current.year()}-09-19`)) {
        daysTillNextBirthday = Math.ceil(dayjs(`${current.year()}-09-19`).diff(current, "day",true))
    }else {
        daysTillNextBirthday = Math.ceil(dayjs(`${current.year()+1}-09-19`).diff(current, "day",true))
    }
    let message = "hi";
    export let birthday = current.get("month") == 8 && current.get("date") == 19;
    if (birthday) {
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
    <br/>
  
    <!-- {#if true} -->
        {#if birthday}
        <div class="another-rainbow rounded-md">
            <p class="md:text-8xl text-white p-12 font-black ">
                VŠECHNO NEJLEPŠÍ K {ageInt}. NAROZENINÁM!
            </p>
            <p class="text text-2xl text-white p-12 font-black ">
                Máme* tě rádi :)
            </p>
            <p class="text text-sm text-gray-600">
                * rodina, kamarádi, známí, Viktor, taneční komunita, koně, šneci, psi (kromě Sammyho), kočky (kromě Helmuta),
                opraváři kol a půjčovny lodí.
            </p>
        </div>
    {:else}
    <p class="text text-2xl text-yellow-400">
        Zbývá {daysTillNextBirthday} dnů do příštích narozenin!
    </p>
    {/if}
</div>

<style>
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
