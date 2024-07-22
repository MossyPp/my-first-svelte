<script lang="ts">
    let display: string = ""
    
    function appendToDisplay(input: string){
        display += input;
    }
    
    function clearDisplay(){
        display = ""
    }
    
    function calculate(){
        try{
            display = eval(display)
        }
        catch(error){
            display = "Error"
        }
        
    }
    </script>
    
    <body class="gap-1 p-[25px] justify-center items-center h-screen m-0 font-mono">
        <div id="calculator" class="bg-[rgb(2,2,6)] max-w-[500px] overflow-hidden rounded-[15px]">
            <input id="display" readonly value={display} class="w-full text-[5rem] text-left bg-[rgb(60,60,62)] text-[azure] p-5 border-[none]">
            <div id="keys" class="grid grid-cols-[repeat(4,1fr)] gap-2.5 p-[25px]">
                <button on:click={() => appendToDisplay('+')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(25,75%,47%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)];]">+</button>
                <button on:click={() => appendToDisplay('7')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(240,2%,24%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">7</button>
                <button on:click={() => appendToDisplay('8')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(240,2%,24%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">8</button>
                <button on:click={() => appendToDisplay('9')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(240,2%,24%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">9</button>
                <button on:click={() => appendToDisplay('-')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(25,75%,47%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)];]">-</button>
                <button on:click={() => appendToDisplay('4')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(240,2%,24%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">4</button>
                <button on:click={() => appendToDisplay('5')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(240,2%,24%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">5</button>
                <button on:click={() => appendToDisplay('6')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(240,2%,24%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">6</button>
                <button on:click={() => appendToDisplay('*')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(25,75%,47%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)];]">*</button>
                <button on:click={() => appendToDisplay('1')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(240,2%,24%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">1</button>
                <button on:click={() => appendToDisplay('2')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(240,2%,24%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">2</button>
                <button on:click={() => appendToDisplay('3')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(240,2%,24%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">3</button>
                <button on:click={() => appendToDisplay('/')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(25,75%,47%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)];]">/</button>
                <button on:click={() => appendToDisplay('0')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(240,2%,24%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">0</button>
                <button on:click={() => appendToDisplay('.')} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(240,2%,24%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">.</button>
                <button on:click={() => calculate()} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(25,75%,47%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)]">=</button>
                <button on:click={() => clearDisplay()} class="text-[azure] text-5xl font-mono font-[bold] bg-[hsl(25,75%,47%)] w-[100px] h-[100px] rounded-[50px] hover:bg-[hsl(25,75%,60%)] active:bg-[hsl(25,75%,75%)];]">CE</button>
            </div>
        </div>
    </body>
    
    