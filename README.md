# control-statements

Assignment: "Control Statements"

convert the following snippet of high-level language codes into assembly language code using the smallest number of instructions:

values = [8, 80]; (Or any integer values)

result = 0;

do{

  x = USER INPUT; (After a message: "Choose one: [1] Addition, [2] Subtraction, [3] Multiplication, [4] Division, [5] [Default], [0] Exit")
  
  if (x == 0){
  
    break;
    
  }
  
  else if (x == 1){
  
    printf("Result: %d", values[0] + values[1]);
    
  }
  
  else if (x == 2){
  
    printf("Result: %d", values[0] - values[1]);
    
  }
  
  else if (x == 3){
  
    printf("Result: %d", values[0] × values[1]);
    
  }
  
  else if (x == 4){
  
    printf("Result: %d", values[0] / values[1]);
    
  }
  
  else (x == 5){
  
    printf("Result: %d", values[0] + values[1]);
    
  }
  
} while(TRUE);

printf("End of Program!");
