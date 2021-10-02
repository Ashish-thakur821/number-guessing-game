# number-guessing-game
//This is the game of guessing the number
//This game is made on visual studio code with the help of c programming by me
//I hope you will enjoy it !!
#include<stdio.h>
#include<stdlib.h>
#include<time.h>
int main(){
    int number,guess,nguesses=1,nguesses1=1,nguesses2=1;
    srand(time(0));
    number= rand()%100 + 1;  //generates the random number between 1 to 100
    //printf("the number is %d\n",number);
    int select;
    printf("choose number of players between 1 or 2:-");
    scanf("%d",&select);
    if(select==1){
        do{
        printf("guess the number between 1 to 100:\n");
        scanf("%d",&guess);
        if(guess>number){
            printf("lower number please\n");            
        }
        else if(guess<number){
            printf("higher number please\n");
        }
        else{
            printf("Congratulations! you gussed it in %d attempts\n",nguesses);
        }
        nguesses++;
    }while(guess!=number);
    }
    else if(select==2){
        printf("player 1's turn starts\n");
        do{
            printf("guess the number between 1 to 100:");
            scanf("%d",&guess);
            if(guess>number){
                printf("lower number please\n");            
            }
            else if(guess<number){
                printf("higher number please\n");
            }
            else{
                printf("you gussed it in %d attempts\n",nguesses1);
            }
            nguesses1++;
        }while(guess!=number);
        printf("player 2's turn starts\n");
        srand(time(0));
        number= rand()%100 + 1;            // generates the number for player 2
        do{
            printf("guess the number between 1 to 100:");
            scanf("%d",&guess);
            if(guess>number){
                printf("lower number please\n");            
            }
            else if(guess<number){
                printf("higher number please\n");
            }
            else{
                printf("you gussed it in %d attempts\n",nguesses2);
            }
            nguesses2++;
        }while(guess!=number);
        if(nguesses1>nguesses2){
            printf(" Congratulation player 2! you won the match");
        }
        else if(nguesses1<nguesses2){
            printf("Congratulation player 1! you won the match");
        }
        else{
            printf("Match is tie\nyou both played well!\nlets try one more time ");
        }
    }
    else if(number!=1 && number!=2){                                                                                                                                                                                                                
        printf("invalid number\nplease try again");
    }
return 0 ;
}
