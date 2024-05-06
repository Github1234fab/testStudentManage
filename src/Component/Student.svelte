 <script>
        let tab = [
                { name: "philippe", value: 45 },
                { name: "Adeline", value: 30 },
                { name: "Mamadou", value: 30 },
                { name: "Éléa", value: 45 },
                { name: "Hugo", value: 60 },
                { name: "Léa", value: 60 },
                { name: "Léo", value: 30 },
                { name: "Léna", value: 45 },
                { name: "Léon", value: 30 },
                { name: "Léonie", value: 30 },
                { name: "Léopold", value: 45 },
        ];
        let tabAfterClick = [];
        let studentNameChecked;
        let alertAlreadyChecked;


        console.log(tabAfterClick);

        function test(student) {
                if (tabAfterClick.includes(student)) {
                        console.log(`Vous avez déjà sélectionné: ${student.name}`);
                        alertAlreadyChecked = `Vous avez déjà sélectionné: ${student.name}`;
                        return;
                }
                tabAfterClick.push(student);
                console.log(tabAfterClick);
                studentNameChecked = `${student.name} ` + "a bien été ajouté";
                console.log(`${student.name} ` + "a bien été ajouté");
        }

        function isStudentChecked(student) {
                return tabAfterClick.includes(student);
        }

        function calculateTotalValue() {
                let total = 0;
                tabAfterClick.forEach((student) => {
                        total += student.value;
                });
                console.log(total);
        }
</script>

<h1>Student</h1>

<div class="container">
        <div class="wrapper-buttons">
              {#each tab as student}
            <button style:background-color={ isStudentChecked(student) ? "red" : null}  on:click={() => test(student)}
                    >{student.name}</button
            >
        {/each}
        </div>
</div> 






<p>{studentNameChecked}</p>
<p>{alertAlreadyChecked}</p>
<button on:click={calculateTotalValue}>Total heures</button>

<style>
        .container {
                display: flex;
                justify-content: center;
                align-items: center;
                height: 100vh;
        }
        .wrapper-buttons {
                display: flex;
                flex-wrap: wrap;
                justify-content: center;
                flex-direction: column;
                gap: 10px;
        }
        button {
                padding: 0.5rem 1rem;
        }
    
</style>
