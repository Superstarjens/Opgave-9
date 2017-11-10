  #include <stdio.h>
  #include <stdlib.h>
  #include <string.h>
  
  /*the prototype*/
  int is_palindrom_iter(char *pal);
  int is_palindrome_rec(char *str);

  int main(void)
  {
    char pal[20];
    /*find the palindrom*/
    printf("Enter a word which is a palindrom\n");
    scanf("%s", pal);

    /*Show if the word is a palindrom*/
    printf("In the iterative the word %s\n", pal);
    if (is_palindrom_iter(pal) == 0)
    {
      printf("Is not a palindrom\n");
    }
    else
    {
      printf("Is a palindrom\n");
    }

    printf("In the recursive the word %s\n", pal);

    if (is_palindrome_rec(pal) == 0)
    {
        printf("Is not a palindrom\n");
    }
    else
    {
        printf("Is a palindrom\n");
    }
    return 0;
  }

  /*Is the palindrom iterativ*/
  int is_palindrom_iter(char *pal)
  {
    int str;
    str=strlen(pal)-1;
  for (int i=0, j=str; i < j; ++i, --j)
  {
      if (*(pal + i) == *(pal + j))
      {
        continue;
      }
      else
      {
        return 0;
      }
  }
  return 1;
  }

  /*Is the Palindrom recursive*/
  int is_palindrome_rec(char *pal)
  {
    int str;
    int counter = 1;
    str=strlen(pal);
    if ((counter==str / 2) && ((str + counter) == (str + ((str - 1) - counter))))
    {
        return 1;
    }
    else if ((str + (counter - 1)) == (str + ((str - 1) - (counter - 1))))
    {
    counter++;
    return is_palindrome_rec(pal);
    }
    else
    {
        return 0;
    }
  }
