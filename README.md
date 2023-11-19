# StringAssignment
#include <stdio.h>
#include <string.h>
#include <ctype.h>
#define Size 3

int main()
{
    char s1[3][30]; // you can have 3 strings. Each string can go up to 29+1 characters
    int i;
    for(i=0;i<3;i++){
        printf("Input string %d:",i);
        fgets(s1[i],30,stdin);
        s1[i][strlen(s1[i])-1]='\0';
        //ใช้get มันจะenterเลยต้องมาแก้ให้ตัวท้ายไม่ใช่enter
    }
    
    char first[30],last[30];
    
   strcpy(first,s1[0]);
    for (i=1;i<Size;i++)
        if(strcmp(first,s1[i])>0 ) 
           strcpy(first,s1[i]);
    printf("First word is %s\n",first);
           
    strcpy(last,s1[0]);
    for (i=1;i<Size;i++)
        if(strcmp(last,s1[i])<0 ) 
        strcpy(last,s1[i]);
    printf("Last word is %s\n",last);
    
    // concaternate first + last
    // --> batrat
    strcat(first,last);
    printf("%s\n",first);
    
    for(i=strlen(first)-1;i>=0;i--){
        switch(first[i]){
            case 'a' :
            case 'e' :
            case 'i' :
            case 'o' :
            case 'u' : printf("%c",toupper(first[i]));
            break;
            default: printf("%c",first[i]);
            
        }
    }
    return 0;
}



