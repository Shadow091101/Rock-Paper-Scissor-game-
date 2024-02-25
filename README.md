<!--# Rock-Paper-Scissor-game-
The computer randomly Generate R as Rock,P as Paper and S as scrissors and then user has to put his choice whtether he wants Rock,Paper or Scissor . the  result is same as per its original rules->

<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>

<body>
    <script>

        function RockPaperScissorsgame() {
            function generatecomputerchoice() {
                const choices = ["R", "P", "S"]
                const randomindex = Math.floor(Math.random() * choices.length)
                return choices[randomindex];
            }

            function determinewinner(userchoice, computerchoice) {
                if (userchoice == computerchoice) {
                     return "It's a Tie"
                }
                else if ((userchoice == 'R' && computerchoice == 'S') || (userchoice == 'P' && computerchoice == 'R') || (userchoice == 'S' && computerchoice == 'P')
                ) {
                     return "You win!"
                }
                else{
                    return "Computer Wins"
                }
            }

            while(true){
                const userchoice=prompt("Enter your choice: R for Rock,P for Paper and S for Scissors").toUpperCase();
                if(userchoice!='R'&& userchoice!='P'&&userchoice!="S"){
                    alert("Invalid choice! Please enter R,P or S");
                    continue;
                }
                const computerchoice=generatecomputerchoice();
                const result = determinewinner(userchoice, computerchoice);

                alert(`Your Choice:${userchoice}\n Computer's Choice:${computerchoice}\n ${result}`);
                
                const playagain=confirm("Do you want to play again?");
                if(!playagain){
                    break;
                }
            }
        }
        RockPaperScissorsgame();
    </script>

</body>

</html>
