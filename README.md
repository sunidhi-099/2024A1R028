# baseball-game
int calPoints(char** operations, int operationsSize) {
    int stack[operationsSize],top=-1,i;
    for(i=0;i<operationsSize;i++){
       if(strcmp(operations[i],"+")==0){
       stack[++top]=stack[top]+stack[top-1];
       }
       else if(strcmp(operations[i],"D")==0){
        stack[++top]=stack[top]*2;
       }
       else if(strcmp(operations[i],"C")==0){
        top--;
       }
       else{
        stack[++top]=atoi(operations[i]);
       }
    }
    int sum=0;
    while(top!=-1){
        sum+=stack[top--];
    }
    return sum;

}
