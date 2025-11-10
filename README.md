# first_mini_project
//+++++++++++++++++++++++++++++++++++++++++++++
//MINI PROJECT : simple game STONE,PAPER,SCISSOR
//+++++++++++++++++++++++++++++++++++++++++++++
#include <math.h>
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define STONE 1
#define PAPER 2
#define SCISSOR 3
//Function to implement the game
 int game (char you, char computer){
 // if YOU and the computer choose the same thing
  if (you == computer){
    return -1;
  }
  // if the user chose :'1' STONE and the computer choose : '2' the PAPER
 if ( you == '1' && computer == '2'){
    return 0;
    // if the user chose :'2' PAPER and the computer choose : '1' the STONE
 }else if (you == '2' && computer == '1'){
   return 1;
}
// if the user chose :'1' STONE and the computer choose : '3' the SCISSOR
  if ( you == '1' && computer == '3'){
    return 1;
    // if the user chose :'3' SCISSOR and the computer choose : '1' the STONE
  }else if (you == '3' && computer == '1'){

  return 0;
  }
  // if the user chose :'2' PAPER and the computer choose : '3' the SCISSOR
 if (you == '2' && computer == '3'){

    return 0;
// if the user chose :'3' SCISSOR and the computer choose : '2' the PAPER
 }else if ( you == '3' && computer == '2'){

   return 1;
 }

 }
 int main (){
 // Stores the random number
  int n;
  char you , computer, Result;
  // choose a random number every time
 srand (time(NULL));
 // make a random number less than 100, Divided it by 100
 n = rand ()%100;
 // Using simple probability 100 is roughly divided among stone, paper, and scissor

 if (n<33){
 // '1' denoting STONE
    computer ='1';
    
 }else if (n > 33 && n < 66){
  // '2' denoting PAPER
  computer = '2';
  // '3' denoting SCISSOR
 }else {computer = '3';}

   printf ("\n\n\n\t\t\t\t\t\t\t\t +Enter 1 for stone , 2 for paper ,3 scissor+\n\n\n\t\t\t\t");
// to input from the user
        scanf ("%c",&you);
        // function call to play them
 Result = game (you,computer);
  if (Result == -1){
    printf ("\n\n\t\t GAME DRAW!\n");
  }else if (Result == 1){
    printf ("\n\n\t\t WOW! YOU HAVE WON THE GAME!\n");

  }else {printf ("\n\n\t\t OH! YOU HAVE LOST THIS GAME!\n");}
    printf ("\n\n\t\t YOU chose : %c and the COMPUTER choose : %c \n",you,computer);
 return 0;
 }
