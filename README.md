# CE4 PRISM Coding
## Assembly Language

### Program A

Program A was difficult to program simply because we were unfamiliar with the commands and language of PRISM. This program served as an introduction, mostly to the syntax, of the program. I learned that I had to name a RAM port if I wanted to use that port. Once the three RAM ports to be used were named, it was very simple to use LDAI to load the value of the operand, then use STA to store that value to a RAM port that had the same name as the supplied operand.

Documentation: received help from C3C Bodin on naming RAM ports in order to use those ports in the program.

### Program B

This program involved basic math, as well as using the input and output ports. For this, the value of RAM had to be manipulated in order to test the program. In this program I used the LDAD command to load the value at a specific port, then I added that value to itself using ADDD to double it. 

In my original program, I stored that value into another RAM port. Next I loaded the value of 4 and used the NEG command to get -4. Then I used the ADDD command in order to add the -4 value to the previous number (the doubled number stored) in order to achieve the final result, to double the original number and subtract 4.

The original program accomplished the purpose of the program, but used a larger amount of code and RAM than needed. I edited the program after finishing Program C, which will explain the process of reaching the final product of Program B. Essentially, I just replaced the lines that loaded the value of 4 and subsequently negated the value, instead using the add immediate command with the original doubled number in the accumulator. The operand, then, was the equivalent of -4: C. Using this took away the use of the second RAM port and greatly reduced the amount of code needed.

### Program C

This program created a pattern of gradually decreasing numbers in 3 of the 4 output ports. This turned out to be a relatively simple program, but using the precedent mentioned above of storing values unnecessarily in RAM and loading values just to negate those values, my program went through a couple of changes in order to reduce the amount of code.

Originally, I went to load and negate a value of 1, then store that value and use it again. However, upon studying the program as it ran, I noticed that I had overlooked a very simple piece of syntax. I was trying to use literally "-1" as an operand, which wasn't an option, so then I loaded the value of 1 and negated it. I should have been trying to use the 2's compliment version of -1 which is 1111 or "F" (I felt a little dumb overlooking this...). From there, I realized I could use the add immediate command and just add the value of the accumulator to F, or -1, in order to decrease the number. I later took this piece of syntax and used it to make Program B more efficient.

After each value underwent the subtraction, it was outputted to its respective port. Then at the end of the program, I added 1 to the accumulator (which is 1 less than the original value) and looped it to the first output command to make the infinite loop. 
