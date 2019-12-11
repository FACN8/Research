**Regular Expressions**

A regular expression is an object that describes a pattern of characters.

**use**
Regular expressions are used to perform pattern-matching and “search-and-replace” functions on text or Test() and Exec(). 


**Modifier/Flags**
flags: (optional) indicate how to search (modifier). 
i
With this flag the search is case-insensitive: no difference between A and a .
g
With this flag the search looks for all matches, without it – only the first match is returned.
m
Multiline mode, searches at the beginning or end of each line in a string.

 **Creating a Regex**
   **Creating**
  var re = new RegExp("pattern","flags"); 
 or
 var re = /pattern/flags;   
 **Testing for matches:**
 /pattern/.test("this-is-a-string"): returns a Boolean telling you whether the string contains a match of the pattern 
**Executes a search:**
/pattern/.exec("this-is-a-string"): returns an array

**Email Regex**
^\w+([.-]?\w+)@\w+(.\w{2,3})$
