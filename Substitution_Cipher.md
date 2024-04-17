## Substitution Cipher

**Project description:** A substitution cipher that encrypts user-entered messages by replacing an alphanumeric character with an alternative element. The substitution is called fixed because the same character will always receive the same replacement.

<img src="images/Cipher_1.png?raw=true"/>
<img src="images/Cipher_2.png?raw=true"/>

### Code Structure

The cipher is constructed by parsing through two global variables: 

```C#
        public Cipher()
        {
            //instantiate vars

            alphabet = "abcdefghijklmnopqrstuvwxyz";
            substitute = "opdefghiqrsxyzabcjklmntuvw";
            
        }
```
The user is prompted for a message, which is encrypted with the Encrypt() method:

```C#
        public string Encrypt(string myMessage) //returns string
        {
            int index;
            char replacement = 'z';
            string result = "";
            int subIndex;

            myMessage = myMessage.Trim().ToLower();

            for (index = 0; index < myMessage.Length; index++)
                for (subIndex = 0; subIndex < 26; subIndex++)
                    if (myMessage[index] == alphabet[subIndex])
                        result += substitute[subIndex];
            return result;

        }
```

The encrypted message is passed through the Decrypt() method and printed for the user:

```C#
        public string Decrypt(string myMessage)
        {
            string result = "";
            int subIndex;

            for (int index = 0; index < myMessage.Length; index++)
                for (subIndex = 0; subIndex < 26; subIndex++)
                    if (myMessage[index] == substitute[subIndex])
                        result += alphabet[subIndex];
            return result;


        }
```
