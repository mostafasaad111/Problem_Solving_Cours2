# Problem_Solving_Cours2

## 1- Write a program to read how many keys to generate and print them on the screen.

          #include <iostream>
          #include <string>
          #include <cstdlib> // For rand and srand
          #include <ctime>   // For time function
          using namespace std;
          enum enCharType
          {
            SamallLetter = 1,
            CapitalLetter = 2,
            SpecialCharacter = 3,
            Digit = 4
          };
          int RandomNumber(int From, int To)
          {
            int randNum = rand() % (To - From + 1) + From;
            return randNum;
          }
          char GetRandomCharacter(enCharType CharType)
          {
            switch (CharType)
            {
              case enCharType::SamallLetter:
              {
                return char(RandomNumber(97, 122));
                break;
              }
              case enCharType::CapitalLetter:
              {
                return char(RandomNumber(65, 90));
                break;
              }
              case enCharType::SpecialCharacter:
              {
                return char(RandomNumber(33, 47));
                break;
              }
              case enCharType::Digit:
              {
                return char(RandomNumber(48, 57));
                break;
              }
            }
          }
          
          int ReadPositiveNumber(string message)
          {
            int number = 0;
            do
            {
              cout << message << endl;
              cin >> number;
            } while (number <= 0);
            return number;
          }
          string GenerateWord(enCharType charType, short length)
          {
            string word;
            for (int i = 1; i <= length; i++)
            {
              word = word + GetRandomCharacter(charType);
            }
            return word;
          }
          
          string GenerateKey()
          {
            string key = "";
          
            key = GenerateWord(enCharType::CapitalLetter, 4) + "-";
            key = key + GenerateWord(enCharType::CapitalLetter, 4) + "-";
            key = key + GenerateWord(enCharType::CapitalLetter, 4) + "-";
            key = key + GenerateWord(enCharType::CapitalLetter, 4);
          
            return key;
          }
          void GenerateKeys(short NumberOfKeys)
          {
            for (int i = 1; i <= NumberOfKeys; i++)
            {
              cout << "key [" << i << "]: ";
              cout << GenerateKey() << endl;
            }
          }
          int main()
          {

## 2- Write a program to read N elements and store them in array then print all array elements and ask
for a number to check, then print how many number a certain element repeated in that array.



























  srand((unsigned)time(NULL));

  GenerateKeys(ReadPositiveNumber("please enter how many keys to generate? \n"));
  return 0;
}
