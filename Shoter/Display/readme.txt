Author : Shoter
Version 1.0

Uses :
-

Syntax :
--------------------------------------------------
Shoter_Display_Add( string:string, params:list, time:integer , overwrite:boolean ) : returns unique_id:integer

string - name of text to replace from counters.wri or text to display

params - parameters that will be passed to counter. Example : [1], Example2 : [1,4,0$02]

time - How much second it will be shown on display

overWrite : if true it will rewrite the same string on the table, if true and there isn't any same string on the display then it will just add itself.
if false it will just add itself to display.
--------------------------------------------------
--------------------------------------------------
Shoter_Display_Delete( unique_id:integer ) : return nothing

unique_id - delete string on display with passed id.
--------------------------------------------------
--------------------------------------------------


How to use :
- Init display with Shoter_Display_Init;
- Add your text on display with Shoter_Display_Add;
- we can define our own texts in counters.wri.

Example video in polish language : http://www.youtube.com/watch?v=6J8T3YjhI-A
