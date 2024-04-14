# Regular-Expressions
Commonly used regexes

Reference
Characters
Literal Characters
Example - car string. regex - car
global - match multiple times
Metacharacters
Wildcard
“.” - any character except newline
Example - /h.t/ - will match hat
Escaping Metacharacters
“\” - escape any metcharacter
Example - /\./ - escapes wildcard metacharacter “.” and its only matching a period
Other special characters
Spaces - actual space character
Tab - \t
Line returns
\n - new line
\r - return carriage
\r\n
Character sets
Define a character set
“[“- begin character set
“]” - end character set
Example - /[aeiou]/ - match any vowel
Example -/gr[ea]y/ - matches grey and gray
Character Ranges
/[0123456789]/ or /[0-9]/- any number
/[abcdefghijklmnopqrstuvwxyz]/ or /[a-z]// - any alphabet lowercase
/[ABCDEFGHIJKLMNOPQRSTUVWXYZ]/ or /[A-Z]/ - any alphabet uppercase
/[a-z]/ - a to z . The “-” here is applicable only inside [] outsite its just a hyphen
/[A-Za-z]/ - case insensitive alphabets
Negative character sets
^ - Negate character set
/[^aeiou]/ - matches only consonants
Meta characters inside character sets
Meta characters already escaped in a character set
/h[.e]t/ - matches het and h.t
Exceptions - ], -, ^, \
Shorthand character sets
\d - any 1 digit same as [0-9]
\w - word character same as [a-zA-Z0-9_]
\s - whitespace same as [\t\r\n]
\D - not digit same as [^0-9] same as /[^\d]/
\W - not word same as [^a-zA-Z0-9_] 
\S - no whitespace same as [^ \t\r\n]

Repetition
Repetition Meta Characters
“*” - Preceding items 0 or more times
“+” - Preceding items, one or more times
“?” - Preceding items, one or more times
Examples
/.+/ - any character other than except line return
/apples*/ - matches apple, apples and applessssss
/\d\d\d\d*/ - matches number 3 or more digits
/\d\d\d*/ - matches numbers 3 digits or more
/colou?r/ - matches color or colour
Quantified Repetition
“{“ - start of quantified repetition of preceding item
“}” - end of quantified repetition of preceding item
Examples-
\d{4,8} - matches number 4 to 8 digits
\d{4} - matches only 4 digits
\d{4,}- matches number 4 or more digits
\d{0,}- is same as \d*
\d{1,} is same as \d+
Greedy Expressions - match the longest possible string
Example
/.+\.jpg/ - matches filename.jpg
Lazy Expressions - match the shortest possible string
Grouping and Alternation
Grouping Metacharacters
“(“ - start of a grouped expression
“)” - end of a grouped expression
Examples
/(abc)+/ - matches abc or abcabcabc
/(in)?dependant/ - matches independent and dependant
/run(s)?/ is same as /runs?/
Alternation Metacharacters
“|” - match previous or next expression
Examples
/apple|orange/- matches apple and orange
/apple(juice|sauce)/ not same as /applejuice|sauce/
/(AA|BB|CC){4}/ - matches AABBCCAA or AAAABBBB
Efficiency in alternations
Put simplest most efficient expression first
Anchors
Start and end Anchors
“^” - start of the string/line
$ - end of the string/line
\A - Start of string, never end of line
\Z - end of string, never end of line
Examples
/^apple/ same as /\Aapple/
/apple$/ same as /apple\Z
/^apple$/ same as /\Aapple\Z/ 
Line breaks and multiline mode
Single line mode
^ and $ do not match at line breaks
\A and \Z do not match at line breaks
Multiline mode
^ and $ will match at the start and end of lines
\A and \Z do not match at start and end of lines

Word boundaries
\b - word boundary (start/end of word)
\B - not a word boundary
Examples
/\b\w+\b/ - finds four matches in “This is a test”
/\b\w+\b/ - matches all of abc_123 but only part of top-notch
/\bNew\b \bYork\b/ - matches “New York”
/\B\w+\B/ - matches hi and es from  “This is a test”

Capturing Grouping and Backreferences
Captures and Backreferences
\1 - backreference to first capture
\2 - backreference to second capture
\3 - backreference to third capture
Examples
/(ab):(cd):(ef):\3:\2:\1/ matches ab:cd:ef:ef:cd:ab
/<(i|em)>.+?<\/\1>/ - matches <i>regex</i> and <em>regex</em> but not <i>regex</em>
Backreferences to optional expressions
Examples
/(a?)typical & \1political/ matches atypical & apolitical or typical & political 
/(a)?typical & \1politcial/ does not match typical & political
Find and replace using backreferences
Non-capturing group expressions
“?:” - disable capturing for this group
Examples
/I (love|like) (.+)\./ for the text “I like pizza.” captures “like” and “pizza.”
/I (?:love|like) (.+)\./ for the same text only captures “pizza.”
Lookaround Assertions
Positive lookahead assertions
“?=” - group is a positive lookahead assertion
Examples
/sea/ matches sea in seashore and seaside
/(?=seashore)sea/ matches sea in seashore only
Negative lookahead assertion
“?!” = group is a negative lookahead assertion
Examples
/?!(seashore)sea/ matches sea in seaside but not seashore
Lookbehind assertions
“?<=” - group is a positive lookbehind assertion
“?<!” - group is a negative lookbehind assertion
Examples
/(?<=base)ball/ matches “ball” in “baseball” but not in “football”
/(?<!base)ball/ matches ball in football but not in baseball
Multiple lookaround assertions

 
 











Match hackerrank
regex pattern - hackerannk

You have a test string S.
Your task is to write a regular expression that matches only and exactly strings of form:abc.def.ghi.jkx , where each variable  a,b,c,d,e,f,g,h,i,j,k,x can be any single character except the newline.
regex pattern - 
