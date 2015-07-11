#Levya Org. : LDAP

This is the authentication backend for all services of Levya Org. and is administered by sub-porject [Levya-Indentity](https://github.com/Levya-Org/levya-identity).
This is the SRC folder of the project, for more information see the public Owncloud Folder [here]().

##Folder Organisation :


##File Description :

.\README.md : this file  
.\AUTHORS : list of Authors & Contributors
.\LICENSE : license file for the project  
.\CONTRIBUTING.md : How To contribute

##Setup

Replace all [PASSWORD] in ldif files with a generated password :
```
slappasswd -h {SSHA} -s apassword
```
Then :
```
ldapadd -Y EXTERNAL -H ldapi:/// -f createDB.ldif
ldapadd -x -D cn=root,dc=levya,dc=org -W -f initDB.ldif
ldapadd -x -D cn=root,dc=levya,dc=org -W -f realData.ldif
ldapmodify -Y EXTERNAL -H ldapi:/// -f ACL.ldif
ldapadd -x -D cn=root,dc=levya,dc=org -W -f testData.ldif //For test purpose
```

##Licence :

This file is part of Levya Org. project.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
