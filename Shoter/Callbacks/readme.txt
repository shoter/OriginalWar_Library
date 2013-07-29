Author : shoter
Version : 1.0

Uses :
Shoter_Functions

How to use :
1. Init callback library by OWL_Shoter_Callback_init;
2. add your own function to Shoter_Functions in library/shoter/Functions folder
3. Write your own function 
4a. Add your callback in code by OWL_Shoter_Callback_Add( Function_String_Name , Function_Parameters, Function_Frequency, Function_number_of_repeats );
4b. Add your callback in code by OWL_Shoter_Callback_Add_Fetch( Function_String_Name , Function_Parameters, Function_Frequency, Function_number_of_repeats ); //IT's diffrent!

Example : Function that spawns crates and uses parameters to do something like rand.

//Function : 

export function create_Crate( params );
begin
CreateCratesAnywhere(Rand(params[1],params[2]),true);
end;

//Now we will add it to Shoter_Functions

Export function OWL_Shoter_Functions_Execute( {string} function_name, parameters );
begin
     case function_name of
          'create_Crate' :
                        begin pojaw_skrzynke( parameters ); end;
     end;
end;

//Now we will use callback Library

OWL_Shoter_Callback_Add('create_Crate', [3,4], 5, 5 );

As the result shoter callback library will spawn from 3 to 4 crates 5 times with 5 second frequency

------
Example of point 4b :

OWL_Shoter_Callback_Add_Fetch('create_Crate', [2,[True,'rand',[1,3] ], [False, 5] ], 5, 5 );
Script will work same like above but with that diffrence that parameters given to function can change every time. In this example our first parameter can only change.

Parameter [True,'rand',[1,3]] will execute rand from Shoter_Functions and return it's result.
Parameter [False, 5] will return 5.

Result of parameter 1 and parameter 2 will be joined and they will be passed to 'create_Crate' function that is declared inside Shoter_function

Parameters syntax

[ num_of_parameters, param_1, param_2, ... , param_n ]

Syntax of fetched parameters :
	Unfetched ones :
	[False, Value]
	Fetched ones :
	[True, Function_name, params ]