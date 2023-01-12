'''Function converting a roman numeral to a decimal number'''

def roman_to_decimal(roman):
    
    # A map or dictionary of each roman numeral which corresponds to a integer
    
    dec_num_result = 0 # setting initial result to zero
    i = 0 # setting initial index to zero
        
    roman_dict = {
        'I':1,
        'IV': 4,
        'V': 5,
        'IX': 9,
        'X': 10,
        'XL': 40,
        'L': 50,
        'XC': 90,
        'C': 100,
        'CD': 400,
        'D': 500,
        'CM': 900,
        'M': 1000
    }

    '''Converts a roman numeral to an integer'''
    
    ''' As long as the index, i,  is less than the length of the roman numeral, 
    the answer isnt complete. While loop continues to increase index as each number becomes
    added to the string.'''
    
    while i < len(roman): 
        
        if i+1 < len(roman) and roman[i:i+2] in roman_dict: # Checks if the current digit is one of the two digit numerals from the dictionary    
            dec_num_result += roman_dict[roman[i:i+2]] # Adds value of two digit numeral.
            i += 2 # Increments index by two, effectively skipping the numerals it has just added.
        
        else:
            dec_num_result += roman_dict[roman[i]] # Adds value of a single digit numeral
            i += 1 # Skips one numeral by incrementing by one.
    
    return dec_num_result


'''Function converting decimal number to a roman numeral'''

def decimal_to_roman(decimal):
    
    # A map or dictionary of each integer corresponding to a roman numeral
    '''Format; value:numeral '''
    
    roman_dict = {
        1: 'I',
        4: 'IV',
        5: 'V',
        9: 'IX',
        10: 'X',
        40: 'XL',
        50: 'L',
        90: 'XC',
        100: 'C',
        400: 'CD',
        500: 'D',
        900: 'CM',
        1000: 'M'
    }

    roman_num_result = '' # Initial roman numeral is blank 
    
    '''Converts an integer to a roman numeral.
    Uses arguments 'format' and 'value' to lookup fron the dictionary.
    Uses 'sorted' and 'reverse=True' arguments to arrange the numeral in descending order
    to build the roman numeral.
    .items() is used to actually lookup the mapped values.'''
    
    for value, numeral in sorted(roman_dict.items(), reverse=True):
            # Loop runs when the inputted integer, 'decimal', is greater than the integer value in the dictionary.
            while decimal >= value:
                # Adds the part of the numeral to the output
                roman_num_result += numeral
                # Decreases the input by the integer value that it has just appended to the numeral
                decimal -= value
    
    return roman_num_result


'''Calculator function which takes inputs and computes sums'''

def calculator():
    
    print('Welcome, enter the two roman numeral numbers and chosen operator below to use the calculator.')
    print('Enter "exit" to stop the programme at any time.')
    
    while True:
    
        num_1_rom = str(input('Enter the first numeral: '))
        if num_1_rom == 'exit' or num_1_rom == 'Exit':
            break
        else:
            num_1 = roman_to_decimal(num_1_rom)
            
        operator = str(input('Enter an operator (+, -, /, *, **): '))
        if operator == 'exit' or operator == 'Exit':
            break
        
        num_2_rom = str(input('Enter the second numeral: '))
        if num_2_rom == 'exit' or num_2_rom == 'Exit':
            break
        else:
            num_2 = roman_to_decimal(num_2_rom)
        
        '''Performing Calculations'''
        
        if operator == '+':
            answer = num_1 + num_2

        elif operator == '-':
            answer = num_1 - num_2

        elif operator == '*':
            answer = num_1 * num_2

        elif operator == '/':
            answer = num_1 / num_2

        elif operator == '**':
            answer = num_1 ** num_2
                
        # answer needs to be a whole number to be converted back into a roman numeral.
        answer = round(answer)

        answer = decimal_to_roman(answer) # Using decimal_to_roman to convert integer back to a roman numeral.
        
        print('{} {} {} = {} (rounded to the nearest numeral)'.format(num_1_rom, operator, num_2_rom, answer))

calculator() # Initialises Script
