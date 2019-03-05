# INDEX-OF---TOOL-CALL-MACRO
Macro to call tools with a number (name) instead of position


Abstract:
Tool organization can be a very dificult task in a workshop, keeping the tool names in a ISO format program is impossible, we can only call for a tool number that exists in the machine tool magazine.
There are some third part software to deal with this, the solutions can be various. For this case I use the concept of IndexOf, an ideia used in most of the programming languages.

So, to do this we must use this rules:

- Maximum of 99 tools, can be more if necessary, but this program must be changed;
- Tool numbers must be unique, you can't repeat the tool number;
- Tool position must be defined with variables #101 to #199, #101 is pocket 1, #102 is poket 2, #199 is pocket 99;
- Tool can only be called with a macro like "G65 P9001 T12344321";
- The H and D offsets are setted with the tool call, not in the middle of the program.

Implementation:
The macro is just a Index Of function. Instead of asking the value of a variable, you ask the variable that contains a value.

(POCKET=TOOL)
#101=12340001

#102=12340024

#103=12340030

#104=12340022

#105=12340054

#106=12340125

#107=12340555

#108=12340656

#109=12340655

#110=12343252

#111=12342455

#112=12345456

#113=12341457

#114=12345412

#115=12341257


If you ask for the variable that contains 12340125, you will get the #106. In this macro, The tool T6 will be called and the offsets H6 and D6 will be setted.
