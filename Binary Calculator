def bin_addition(a, b) :
 #pad the shorter number with zeros that won't affect the value but will make the two numbers have the same length
 length = len(a) if len(a) >= len(b) else len(b)  # finding he shorter number
 a = a.zfill(length)
 b = b.zfill(length)
 carry = '0'   # initialize carry
 result = ''   # initialize result
 # Loop through the digits of the numbers from right to left
 for i in range(length - 1, -1, -1):
   # Calculate the sum of the current digits and the carry
   sum_digit = int(a[i]) + int(b[i]) + int(carry)
   carry = '1' if sum_digit >= 2 else '0'
   result = str(sum_digit % 2) + result
 # Add the carry to the beginning of the sum if necessary
 if carry == '1':
    result = '1' + result
 return result



def bin_subtraction(a , b) :
 # Pad the shorter number with zeros that won't affect the value but will make the two numbers have the same length
 a = a.zfill(len(a) if len(a) >= len(b) else len(b))  # finding he shorter number
 b = b.zfill(len(a))
 difference = ""   # initialize difference
 carry = 0         # initialize carry
 # Loop through the digits of the numbers from right to left
 for i in range(len(a) - 1, -1, -1):
   digit_difference = int(a[i]) - int(b[i]) - carry   # Subtract the current digits and the carry
   # Handle negative difference and carry
   if digit_difference < 0:
      digit_difference += 2
      carry = 1
   else:
       carry = 0
   difference = str(digit_difference) + difference # Append the difference digit to the result.
 #difference = difference.lstrip("0")  if you want to remove unnecessary zeros on the left of the final answer remove the hash from this line (the same indent as for loop)
 if carry :
     difference = "-" + difference
 return difference



menu1_options = ( "A" , "B" )
# making menu1 choices for user to choose whether to continue or to exit
while True :
# while true loop won't stop until we use break so it's useful in this case as munu1 will automatically appear when an invalid choice entered or when operation finished
    print()
    print("**binary calculator**")
    print("A)Insert new number")
    print("B)Exit")
#print() is to make every choice appear in a seperate line
    print()
    menu1_user_input = input("enter an option: ")
    if menu1_user_input == "A" :
     first_number= input("Please enter a number: ")
     binary_set = {'0' , '1'}
     input_set = set(first_number)
     if binary_set == input_set or input_set == {'0'} or input_set == {'1'}:
#we converted input into a set then using boolean methods and set theory (from discrete mathematics) if any condition from the 3 is true the input is binary and menu2 will appear
         menu2_options = ('A' , 'B' , 'C' , 'D')
         print()
         print("**please select the operation**")
         print("A)Compute one's complement")
         print("B)Compute two's complement")
         print("C)addition")
         print("D)subtraction")
         print()
         menu2_user_input = input("enter an option: ")
         if menu2_user_input == 'A' :
           first_number= str(first_number)
           # chain replace method to replace every 1 with 0 and every 0 with 1
           first_complement= first_number.replace('0','_').replace('1' , '0').replace('_' ,'1').replace('_' ,'1')
           print("one's complement: ", first_complement)
#test by entering 1001  for test and the output will be 0110 as expected



         elif menu2_user_input == 'B' :   #test by entering 110010 the output will be 001101
          first_number= str(first_number)
          first_complement= first_number.replace('0','_').replace('1' , '0').replace('_' , '1').replace('_' , '1')
          second_complement =bin_addition(str(first_complement) , str(1))  # we got the one's complement first like we did in choice A the used the binary addition function we defined previously to add 1 to the one's complement
          # we converted first_number and 1 to str to be able to put them into the function len because it doesn't work on integers
          print("two's complement: " , second_complement)
# test by enetering 100110 the output will be 011010 as expected


         elif menu2_user_input == 'C' :
             second_number = input('Please enter second number: ')
             binary_set = {'0' , '1'}
             input2_set = set(second_number)
             if binary_set == input2_set or input2_set =={'0'} or input2_set =={'1'} : #the same binary test we used in line 59
              # convert variables to str to make the functin able to work
              sum = bin_addition(str(first_number) , str(second_number)) #we used the function bin_addition we defined earlier
              print('sum: ' , sum)
             else :
              print('Please enter a valid binary number')
# test by entering 01101 and 00111 the answer will be 10100 as expected
# test by entering 01101 and 10111 the answer will be 100100 as expected



         elif menu2_user_input == 'D' :
             second_number = input( 'please enter second number: ')
             binary_set = {'0' , '1'}
             input2_set = set(second_number)
             if binary_set == input2_set or input2_set =={'0'} or input2_set =={'1'} :
              #convert variables to str to make the functin able to work
              subtraction = bin_subtraction(str(first_number) , str(second_number))  # we used the function bin_subtraction we defined earlier
              print('subtraction: ' , subtraction)
             else :
              print('Please enter a valid binary number')
# test by entering 01101 first then 00111 the output will be 00110 as expected
# test by entering 01001 first then 00111 the output will be 00010 as expected
# IMPORTANT NOTE if you want to remove the leading unnecessary zeros go back to line 37 and remove the hash as explained if you want to keep the zeros don't do that



         else :
             print('Please enter a valid choice')



     else:
         print("Please enter a valid binary number")
#test by entering (10015100) and an error message will appear because input contains 5 so the condition we used in line as expected



    elif menu1_user_input == "B" :
        exit()
#test by entering B in first menu for test and the program will stop because of exit() as expected



    else :
        print("Please enter a valid choice")
#test by entering anything except for A B C (they should be capital as well) the loop will return user to menu1 to input a valid choice because we didn't break loop
