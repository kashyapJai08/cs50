#include <cs50.h>
#include <ctype.h>
#include <stdio.h>
#include <string.h>

bool valid_key(string key);
string cipher(string key, string plain);

int main(int argc, string argv[])
{
    // validitiy check for the key
    if (argc != 2 || (int) strlen(argv[1]) != 26 || !(valid_key(argv[1])))
    {
        printf("Usage: ./substitution key\n");
        return 1;
    }

    string plain = get_string("plaintext: "); // input plaintext from user
    // print ciphertext
    printf("ciphertext: %s\n", cipher(argv[1], plain));
    return 0;
}

// checks for the validity of the key
bool valid_key(string key)
{
    // checks for invalid length of the key and repeated characters in the key.
    bool seen[26] = {false};

    for (int i = 0, len = strlen(key); i < len; i++)
    {
        if (!isalpha(key[i]) || seen[tolower(key[i]) - 'a'])
        {
            return false;
        }
        seen[tolower(key[i]) - 'a'] = true;
    }
    return true;
}

// encrypts the plaintext and returns ciphertext
string cipher(string key, string plain)
{
    // encrypting the plaintext
    for (int i = 0, len = strlen(plain); i < len; i++)
    {
        if (islower(plain[i]))
        {
            plain[i] = key[plain[i] - 97];
            plain[i] = tolower(plain[i]);
        }
        else if (isupper(plain[i]))
        {
            plain[i] = key[plain[i] - 65];
            plain[i] = toupper(plain[i]);
        }
    }
    return plain;
}
