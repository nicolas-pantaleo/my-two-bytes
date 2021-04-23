
# MS Excel Shortcuts & Formulas

<br>

Simply a collection of useful shortcuts and formulas!

<br>

---

<br>


## Shortcuts

|Command | Action |
|:------------:|:-----------:|
|CTRL + Home | Back to the first non-blank cell|
|CTRL + 1 | Format Cells|
|CTRL + A | Select the entire data block |
|CTRL + Y | Re-do last action |
|CTRL + 0 | Hide the column of the active cell |
|CTRL + 9 | Hide the row of the active cell |
|CTRL + PageUp/PageDown | Move to the next/previous sheet |
|CTRL + Shift + L | Hide/Unhide Filters |
|CTRL + ; | TODAY() but it doesn't update over time |
|CTRL + T | Create Table |
|CTRL + Space | Select the entire column (not only the data block section) |
|Shift + Space | Select the entire row (not only the data block section) |
|F4 (+Fn?) | Converts relative reference to absolute reference|
|Alt + Enter | Go to the next line when writing text |
|Shift + Top-Left Corner + Bottom-Right Corner| Select all cells in between
| F3 (+Fn?) | Show active named ranges |

<br>

---

<br>

## Numeric Formulas

|Function | Action |
|:------------:|:-----------:|
| =RANDBETWEEN(\$A\$1;\$B\$1) | Random number sampled from the interval |
| =SUM(Sheet1:Sheet8!A1) | 3D Formula Example |
| =COUNT(SomeNumericColumn) | Counts only numeric cells even if there are alphanums |
| =COUNTA(SomeColumn)| Counts all non-empty cells |
| =COUNTBLANK(SomeColumn)| Counts all empty cells |
| =COUNTIFS(Col; "Value") | Counts all cells that have that "Value" |
| =COUNTIFS(Col; A1) | Counts all cells where the value equals A1 |
| =COUNTIFS(Col; 2021) | Counts all cells where the value equals the number 2021 |
| =COUNTIFS(Col; ">20") | Counts all cells where the value respects the logical condition |
| =SUMIFS(ColToSum; ColToCheck, "SomeValue") | Basic Sum + If |
| =SUMIFS(ColSum; ColCheck_1; "A"; ColCheck_2; "B") | Double filter |
| =SUMPRODUCT(Estimates;Weights)/SUM(Weights) | Basic Pessimistic/Optimistic/Likely Estimation |
| =SUMPRODUCT(1\*(A1:A5>=100)) | How many values are >=100? |
| =SUM(IFNA(H7:H17*I7:I17); 0) | Avoiding N/A in SUM with Arrays |
| =SUM((Col1>Col2)*1) | Trick to count how many rows respect the condition |
| =LARGE(Table[Column]; 2) | Second biggest value of the column |
| =LARGE(Table[Column]; ReportTBL[@[Best Quarters]:[Best Quarters]]) | Absolute reference in a table |
| =SUM(SalesTable[[Italy]:[China]]) | "@" not used! It's the sum of all the columns from Italy to China |

<br>

## Text Formulas

|Function | Action |
|:------------:|:-----------:|
| =PROPER(CONCAT(A1; " "; B1))| Capitalize + Concatenate Strings |
| =LOWER(A1&"."&B1&"@email.com") | Lower + Alternative Concatenation |
| =LEFT(A1; 2) | First and second char |
| =RIGHT(A1; 4) | Last 4 chars |
| =MIDDLE(A1; 3; 4) | From the third char (included), 4 chars in total |
| =FIND(" "; A1; 3) | Position of the first space, starting from the third char |
| =TEXTJOIN("-";TRUE;A1;B1) | Another Concatenation, the TRUE is "ignore blank cells" |
| =TRIM(CLEAN(A1)) | Removing extra spaces and non-printing chars |
| =ISNUMBER(A1) | Is A1 a number? |
| =ISTEXT(A1) | Is A1 text? |
| =LEN(A1) | Length of the content of A1 |
| =CODE(RIGHT(A1;1)) | Convert to ASCII |
| =VALUE(A1) | Convert to Numeric from Text |
| =SUBSTITUTE(TextToChange; ToFindAndReplace; ReplaceWith) | Easy sub |
| =SUBSTITUTE(Text; CHAR(160); "") | Removing bad characters |

<br>

## Lookup Formulas

|Function | Action |
|:------------:|:-----------:|
| =CHOOSE([@Column];$K$1;$K$2;$K$3) | Basic CHOOSE Lookup; don't use ranges in values |
| =VLOOKUP(D3;$G$3:$H$7;2) | Basic Range VLOOKUP; sort the lookup in ascending order first |
| =VLOOKUP([@SomeColumn];SomeTable;3;FALSE) | VLOOKUP with a table in another sheet |
| =INDEX(A:A; ROWS(SomeTable) + 3) | Trick to point at last row, 4 is for the heading rows |

<br>

## Date Formulas

|Function | Action |
|:------------:|:-----------:|
| =NOW() | 31/12/2021 18.00 |
| =TODAY() | 31/12/2021 |
| =YEARFRAC(01/01/2021; 31/06/2021) | Close to 0.5 |
| =TODAY()-WEEKDAY(TODAY();3) | First day of the week |
| =A1 + 365 | If A1 is a date, it's a year from A1 |
| =MIN/MAX(A1:A10) | Oldest/Latest Date if A1:A10 are dates |
| =YEAR(A1) | Fetch the Year from a date cell |
| =MONTH(A1) | Fetch the Month from a date cell |
| =DAY(A1) | Fetch the Day from a date cell |
| =EOMONTH(A1;-12) + 1 | Go back 12 months, get the last day and add one |
| =EDATE(A1; 1) | Add one month to that date |
| =WORKDAY.INTL(EOMONTH(C5;0);10;1;$K$5:$K$7) | Ten working days after the end of the month of the date in C5; K5:K7 are holiday dates |
| =DATE(LEFT(A1;4);MID(A1;6;2);RIGHT(A1;2)) | String to Date |
| =TEXT(A1;"mmmm") | Extracting the full month name from a date |

<br>

## Miscellaneous Formulas

|Function | Action |
|:------------:|:-----------:|
| ='[filename.xlsx]Sheet1'!\$A\$1 | Retrieve data from another workbook |
| =[@[Annual Salary]]+[@Bonus] | Working with named ranges in tables |
| =ROUND(A1;2) | Round up to two decimal cells, using 0.5 as threshold |
| =ROUNDUP(A1;2) | Round up to two decimal cells, but always away from zero |
| =ROWS(Table) | Number of rows, headers not included |
| =Table[[#Headers];[ThatNamedRange]] | Returns that column name properly |
| {=TRANSPOSE(A4:A14)} | Column to Row |

<br>

## Logical Formulas

|Function | Action |
|:------------:|:-----------:|
| =IF(EXACT(A1, "John"); B1\*5%; 0) | Using Exact to match string case |
| =IF(AND(B4>0;C4<>"Y"), B4\*10%;0) | IF + AND |
| =IF(OR(B4>=C4;J4;250;0)) | IF + OR |
| =IF(A1=0;"Category A";IF(A1>0; "Category B"; "Category C")) | Nested IFs |
| =IF(A1=1; 0; IF(A1=2; E1\*5%; E1\*10%) | Another Nested IF |
| =IFERROR(AVERAGE(A2:A10);"") | Basic IFERROR |
| =IFNA(VLOOKUP(...); 0) | Managing NAs from VLOOKUP |
| =IF(AND(A3=TRUE;B3=FALSE);"Call";"Do Not Call") | T/F checking with IFs |
| =IF(NOT(A3="Value");"Ok";"Not Ok") | IF + NOT |
| =IF(ISBLANK(A2);A1;A2) | Checking for blanks |


<br>

---
