# NOSQLi

# TYPES:
### Syntax Injection
### OPerator INjection


##NOSQL SYNTAX NJECTION
'"`{
;$Foo}
$Foo \xYZ  -------> if request is from URL 

for JSON --> '\"`{\r;$Foo}\n$Foo \\xYZ\u0000

the above strings can be used to test fot noslqi if detectable changes or eroor is caused
