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

regex pattern - ^.{3}\..{3}\..{3}\..{3}$


You have a test string S. Your task is to match the pattern xxXxxXxxxx
Here x denotes a digit character, and X denotes a non-digit character.

regex pattern - \d{2}\D\d{2}\D\d{4}


You have a test string S. Your task is to match the pattern XXxXXxXX
Here, x denotes whitespace characters, and X denotes non-white space characters.

regex pattern - \S{2}\s\S{2}\s\S{2}


You have a test string A. Your task is to match the pattern Xxxxx.
Here,  x denotes a word character, and X denotes a digit.
S must start with a digit  and end with . symbol.
S should be 6 characters long only.

regex pattern - ^\d\w{4}\.$




You have a test string S.
Your task is to write a regex that will match S with following conditions:

S must be of length: 6
First character: 1, 2 or 3
Second character: 1, 2 or 0
Third character: x, s or 0
Fourth character: 3, 0 , A or a
Fifth character: x, s or u
Sixth character: . or ,

regex pattern - ^[123][120][xs0][30Aa][xsu][.,]$



You have a test string S . Your task is to match the pattern xxxXxxxxxxxxxxXxxx
Here x denotes any word character and X denotes any non-word character.

regex pattern - \w{3}\W\w{10}\W\w{3}




You have a test string S.
Your task is to write a regex that will match S with the following conditions:

 must be of length 6.
First character should not be a digit .
Second character should not be a lowercase vowel.
Third character should not be b, c, D or F.
Fourth character should not be a whitespace character ( \r, \n, \t, \f or <space> ).
Fifth character should not be a uppercase vowel .
Sixth character should not be a . or , symbol.

regex pattern - ^\D[^aeiou][^bcDF]\S[^AEIOU][^.,]$



Write a RegEx that will match a string satisfying the following conditions:

The string's length is >=5.
The first character must be a lowercase English alphabetic character.
The second character must be a positive digit. Note that we consider zero to be neither positive nor negative.
The third character must not be a lowercase English alphabetic character.
The fourth character must not be an uppercase English alphabetic character.
The fifth character must be an uppercase English alphabetic character.

regex pattern - ^[a-z][1-9][^a-z][^A-Z][A-Z]





You have a test string S.
Your task is to write a regex that will match S using the following conditions:

S must be of length equal to 45.
The first 40 characters should consist of letters(both lowercase and uppercase), or of even digits.
The last 5 characters should consist of odd digits or whitespace characters.

regex pattern - ^[a-zA-z024568]{40}[13579\s]{5}$


You have a test string S.
Your task is to write a regex that will match S using the following conditions:

S should begin with 1 or 2 digits.
After that, S should have 3 or more letters (both lowercase and uppercase).
Then S should end with up to 3 . symbol(s). You can end with 0 to 3 . symbol(s), inclusively.


regex pattern - ^\d{1,2}[a-zA-z]{3,}\.{0,3}$



You have a test string S.
Your task is to write a regex that will match  using the following conditions:

S should begin with 2 or more digits.
After that, S should have 0 or more lowercase letters.
S should end with 2 or more uppercase letters

regex pattern - ^\d{2,}[a-z]{0,}[A-Z]{0,}$


You have a test string S.
Your task is to write a regex that will match S using the following conditions:

S should begin with 1 or more digits.
After that, S should have 1 or more uppercase letters.
S should end with 1 or more lowercase letters.

regex pattern - ^\d{1,}[A-Z]{1,}[a-z]{1,}$
