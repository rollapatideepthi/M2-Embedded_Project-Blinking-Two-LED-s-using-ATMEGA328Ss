# TestPlan


At the beginning of the program a pre-processor named “F_CPU” is defined. It is simply your way to tell some of the library code how many CPU cycles per second the processor is executing. Here we defined the F_CPU as 1 MHz. “#include <avr/io.h>” is a header files which provides you with various  i/o operations like DDRx, PINx, PORTx, etc. “#include <util/delay.h>” is a header file which provides you with inbuilt delay functions like _delay_ms(), _delay_us(), etc. “_delay_ms(1000)” provides a delay of 1000 milliseconds (i.e., equivalent to 1 second).

#define F_CPU 1000000UL

#include <avr/io.h>

#include <util/delay.h>




1. DDRx – Data Direction Register configures data direction of the port(Input/Output). The instruction “ DDRB |= (1<<DDB2)”  makes corresponding port pin as output.

DDRB |= (1<<DDB2)|(1<<DDB3);


PORTx – Port register is for assigning appropriate values for the port pins.

PORTB |=(1<<PORTB2);

		PORTB &=~(1<<PORTB3);
    
		_delay_ms(1000);
			
		PORTB &=~(1<<PORTB2);
    
		PORTB |=(1<<PORTB3);
    
		_delay_ms(1000);
    

Writing to PORTx.n will immediately change state of the port pins according to given value. “PORTB |=(1<<PORTB2)” will generate a high signal at PB2. And “PORTB&=~(1<<PORTB3)” is for generating a low signal at PB3.


