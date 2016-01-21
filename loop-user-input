.data									    	#define variable that will be stored in Static memory location

values: .word 8, 80					#defining array
output: .asciiz "Result:\n"	#defining result string
message: .asciiz "Choose one: [1] Addition, [2] Subtraction, [3] Multiplication, [4] Division, [5] [Default], [0] Exit\n Default values are 8, 80\n"		#instruction string
err: .asciiz "Invalid input, please input int between 0 and 5.\n"				#error message
end: .asciiz "End of Program!\n"    	#exit message


.text									    	#alphanumeric identifier
.globl main									#make global for external use

main: 								  		#start of main code body

	li $v0, 4 								#referencing the print_string system call (4)
	la $a0, message						#passing string
	syscall								  	#execute
	j do							    		#jump to do loop

do:										    	#start of do loop

	move $t0, $zero						#loading the increment value (0)
	la $t1, values						#loading address of values into t1

	li $v0, 5							   	# system call code for user input in integer, i.e., read_int
	syscall								  	# excute the read_int system call

	beq $v0, $t0, brk					#if input = 0, jump to brk function
	addi $t0, $t0, 1					#incrementing t0
	
	beq $v0, $t0, addit				#if input = 1, jump to addition function
	addi $t0, $t0, 1		  		#incrementing t0
	
	beq $v0, $t0, subtr				#if input = 2, jump to subtraction function
	addi $t0, $t0, 1					#incrementing t0
	
	beq $v0, $t0, multipl			#if input = 3, jump to multiplication function
	addi $t0, $t0, 1					#incrementing t0

	beq $v0, $t0, divis				#if input = 4, jump to division function
	addi $t0, $t0, 1					#incrementing t0

	beq $v0, $t0, addit				#if input = 5, jump to addition function (DEFAULT)

	li $v0, 4 								#referencing the print_string system call (4)
	la $a0, err								#passing error message - input too high
	syscall								  	#execute
	j do							    		#jump to do loop
  
brk:									    	#defining brk function

	li $v0, 4					  			#referencing the print_string system call (4)
	la $a0, end								#passing exit string
	syscall							  		#execute

	li $v0, 10 								#referencing exit function
	syscall								  	#execute exit
	

addit:									   	#defining addit function

	lw $t0, 0($t1)						#loading first memory location of values
	lw $t2, 4($t1)						#loading second memory location of values

	add $t0, $t0, $t2					#adding values

	li $v0, 4								#referencing the print_string system call (4)
	la $a0, output					#grabbing output string
	syscall									#execute print

	li $v0, 1								#referencing the print_int system call (1)
	move $a0, $t0						#grabbing sum as argument
	syscall									#execute print

	j do							  		#jumo to do loop


subtr:										#defining subtr function

	lw $t0, 0($t1)					#loading first memory location of values
	lw $t2, 4($t1)					#loading second memory location of values

	sub $t0, $t0, $t2				#subtracting values

	li $v0, 4								#referencing the print_string system call (4)
	la $a0, output					#grabbing output string
	syscall									#execute print

	li $v0, 1								#referencing the print_int system call (1)
	move $a0, $t0						#grabbing result as argument
	syscall									#execute print

	j do							  		#jumo to do loop



multipl:									#defining multipl function

	lw $t0, 0($t1)					#loading first memory location of values
	lw $t2, 4($t1)					#loading second memory location of values

	mul $t0, $t0, $t2				#multiplying values

	li $v0, 4								#referencing the print_string system call (4)
	la $a0, output					#grabbing output string
	syscall									#execute print

	li $v0, 1								#referencing the print_int system call (1)
	move $a0, $t0						#grabbing result as argument
	syscall									#execute print

	j do								  	#jumo to do loop

divis:										#defining divis function

	lw $t0, 0($t1)					#loading first memory location of values
	lw $t2, 4($t1)					#loading second memory location of values

	div $t0, $t0, $t2				#dividing values

	li $v0, 4								#referencing the print_string system call (4)
	la $a0, output					#grabbing output string
	syscall									#execute print

	li $v0, 1								#referencing the print_int system call (1)
	move $a0, $t0						#grabbing result as argument
	syscall									#execute print

	j do							  		#jumo to do loop
