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

## 2- Write a program to read N elements and store them in the array then print all array elements and ask for a number to check, then print how many numbers a certain element repeated in that array.

                    #include <iostream>
                    #include <string>
                    using namespace std;
                    
                    int ReadNumber(string message)
                    {
                        int number = 0;
                        do
                        {
                            cout << message << endl;
                            cin >> number;
                        } while (number <= 0);
                        return number;
                    }
                    
                    void LoopFunction(int number, int array[])
                    {
                        for (int i = 0; i < number; i++) // Changed i <= number to i < number
                        {
                            cout << "Element [" << i + 1 << "]: ";
                            cin >> array[i]; // Assign value to array[i]
                        }
                    }
                    
                    void printArray(int array[], int number)
                    {
                        cout << "Original array: ";
                        for (int i = 0; i < number; i++) // Changed i <= number to i < number
                        {
                            cout << array[i] << " ";
                        }
                        cout << endl;
                    }
                    
                    void CheckNumber(int array[], int number)
                    {
                        int number2;
                        cout << "Enter the number you want to check: " << endl;
                        cin >> number2;
                        int counter = 0;
                        for (int i = 0; i < number; i++) // Changed i <= number to i < number
                        {
                            if (number2 == array[i])
                            {
                                counter++;
                            }
                        }
                        if (counter > 0)
                        {
                            cout << number2 << " is repeated " << counter << " times." << endl;
                        }
                        else
                        {
                            cout << number2 << " is not found in the array." << endl;
                        }
                    }
                    
                    int main()
                    {
                        int number = ReadNumber("Please enter the number of elements in the array: ");
                        int array[number];
                        LoopFunction(number, array);
                    
                        printArray(array, number);
                        CheckNumber(array, number);
                        return 0;
                    }
                    
## 3 -  Write a program to fill the array with a max size of 100 with random numbers from 1 to 100.
 
                    #include <iostream>
                    #include <string>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    
                    int ReadNumber(string message)
                    {
                      int number = 0;
                      do
                      {
                        cout << message << endl;
                        cin >> number;
                      } while (number <= 0);
                      return number;
                    }
                    
                    int randNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    
                    void printArray(int array[], int number)
                    {
                      cout << "Original array: ";
                      for (int i = 0; i < number; i++)
                      {
                        cout << array[i] << " ";
                      }
                      cout << endl;
                    }
                    
                    void FillArray(int array[], int number, int from, int to)
                    {
                      for (int i = 0; i < number; i++)
                      {
                        array[i] = randNumber(from, to);
                      }
                    }
                    
                    int main()
                    {
                      srand((unsigned)time(NULL));
                    
                      int number = ReadNumber("Please enter the number of elements in the array: ");
                      int array[100];
                    
                      FillArray(array, number, 10, 100); // Fill the array with random numbers
                      printArray(array, number); // Print the filled array
                    
                      return 0;
                    }

## 4-   Write a program to fill the array with a max size of 100 with random numbers from 1 to 100, Then print the max number.


                              #include <iostream>
                              #include <string>
                              #include <cstdlib> // For rand and srand
                              #include <ctime>   // For time function
                              using namespace std;
                              
                              int ReadNumber(string message)
                              {
                                int number = 0;
                                do
                                {
                                  cout << message << endl;
                                  cin >> number;
                                } while (number <= 0);
                                return number;
                              }
                              
                              int randNumber(int from, int to)
                              {
                                int randNum = rand() % (to - from + 1) + from;
                                return randNum;
                              }
                              
                              void FillArray(int array[], int number, int from, int to)
                              {
                                for (int i = 0; i < number; i++)
                                {
                                  array[i] = randNumber(from, to);
                                }
                              }
                              void printArray(int array[], int number)
                              {
                                cout << "Original array: ";
                                for (int i = 0; i < number; i++)
                                {
                                  cout << array[i] << " ";
                                }
                                cout << endl;
                              }
                              void checkFunction(int array[], int number)
                              {
                                int MaxNumber = array[0];
                                for (int i = 0; i < number; i++)
                                {
                                  if (array[i] > MaxNumber)
                                  {
                                    MaxNumber = array[i];
                                  }
                                }
                                  cout << "Max number is :" << MaxNumber << endl;
                              }
                              int main()
                              {
                                srand((unsigned)time(NULL));
                              
                                int number = ReadNumber("Please enter the number of elements in the array: ");
                                int array[100];
                              
                                FillArray(array, number, 10, 100); // Fill the array with random numbers
                                printArray(array, number);         // Print the filled array
                              
                                checkFunction(array , number); 
                                return 0;
                              }
## 5- Write a program to fill the array with a max size of 100 with random numbers from 1 to 100, Then print the min number.

                    #include <iostream>
                    #include <string>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    
                    int ReadNumber(string message)
                    {
                      int number = 0;
                      do
                      {
                        cout << message << endl;
                        cin >> number;
                      } while (number <= 0);
                      return number;
                    }
                    
                    int randNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    
                    void FillArray(int array[], int number, int from, int to)
                    {
                      for (int i = 0; i < number; i++)
                      {
                        array[i] = randNumber(from, to);
                      }
                    }
                    void printArray(int array[], int number)
                    {
                      cout << "Original array: ";
                      for (int i = 0; i < number; i++)
                      {
                        cout << array[i] << " ";
                      }
                      cout << endl;
                    }
                    void checkFunction(int array[], int number)
                    {
                      int MinNumber = array[0];
                      for (int i = 0; i < number; i++)
                      {
                        if (array[i] < MinNumber)
                        {
                          MinNumber = array[i];
                        }
                      }
                        cout << "Min number is :" << MinNumber << endl;
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                    
                      int number = ReadNumber("Please enter the number of elements in the array: ");
                      int array[100];
                    
                      FillArray(array, number, 10, 100); // Fill the array with random numbers
                      printArray(array, number);         // Print the filled array
                    
                      checkFunction(array , number); 
                      return 0;
                    }
## 6- Write a program to fill the array with a max size of 100 with random numbers from 1 to 100, Then print the sum of all numbers.


                    #include <iostream>
                    #include <string>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    
                    int ReadNumber(string message)
                    {
                      int number = 0;
                      do
                      {
                        cout << message << endl;
                        cin >> number;
                      } while (number <= 0);
                      return number;
                    }
                    
                    int randNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    
                    void FillArray(int array[], int number, int from, int to)
                    {
                      for (int i = 0; i < number; i++)
                      {
                        array[i] = randNumber(from, to);
                      }
                    }
                    void printArray(int array[], int number)
                    {
                      cout << "Original array: ";
                      for (int i = 0; i < number; i++)
                      {
                        cout << array[i] << " ";
                      }
                      cout << endl;
                    }
                    void CalculateNumbers(int array[], int number)
                    {
                      int counter = 0;
                      for (int i = 0; i < number; i++)
                      {
                        counter += array[i];
                      }
                        cout << "sum =  " << counter << endl;
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                    
                      int number = ReadNumber("Please enter the number of elements in the array: ");
                      int array[100];
                    
                      FillArray(array, number, 10, 100); // Fill the array with random numbers
                      printArray(array, number);         // Print the filled array
                    
                      CalculateNumbers(array , number); 
                      return 0;
                    }
## 7- Write a program to fill the array with a max size of 100 with random numbers from 1 to 100, Then calculate the sum of all numbers and print the average of all numbers.

 
                              #include <iostream>
                              #include <string>
                              #include <cstdlib> // For rand and srand
                              #include <ctime>   // For time function
                              using namespace std;
                              
                              int ReadNumber(string message)
                              {
                                int number = 0;
                                do
                                {
                                  cout << message << endl;
                                  cin >> number;
                                } while (number <= 0);
                                return number;
                              }
                              
                              int randNumber(int from, int to)
                              {
                                int randNum = rand() % (to - from + 1) + from;
                                return randNum;
                              }
                              
                              void FillArray(int array[], int number, int from, int to)
                              {
                                for (int i = 0; i < number; i++)
                                {
                                  array[i] = randNumber(from, to);
                                }
                              }
                              void printArray(int array[], int number)
                              {
                                cout << "Original array: ";
                                for (int i = 0; i < number; i++)
                                {
                                  cout << array[i] << " ";
                                }
                                cout << endl;
                              }
                              void CalculateAverageNumber(int array[], int number)
                              {
                                int counter = 0;
                                for (int i = 0; i < number; i++)
                                {
                                  counter += array[i];
                                }
                                int average = counter / number;
                                  cout << "average =  " << average << endl;
                              }
                              int main()
                              {
                                srand((unsigned)time(NULL));
                              
                                int number = ReadNumber("Please enter the number of elements in the array: ");
                                int array[100];
                              
                                FillArray(array, number, 10, 100); // Fill the array with random numbers
                                printArray(array, number);         // Print the filled array
                              
                                CalculateAverageNumber(array , number); 
                                return 0;
                              }
## 8- Write a program to fill the array with a max size of 100 with random numbers from 1 to 100, and copy it to anther and print 2 array .

                    #include <iostream>
                    #include <string>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    
                    int ReadNumber(string message)
                    {
                      int number = 0;
                      do
                      {
                        cout << message << endl;
                        cin >> number;
                      } while (number <= 0);
                      return number;
                    }
                    
                    int randNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    
                    void FillArray(int array[], int number, int from, int to)
                    {
                      for (int i = 0; i < number; i++)
                      {
                        array[i] = randNumber(from, to);
                      }
                    }
                    void printArray(int array[], int number)
                    {
                      cout << "Original array: ";
                      for (int i = 0; i < number; i++)
                      {
                        cout << array[i] << " ";
                      }
                      cout << endl;
                    }
                    void NumberArray2(int array[], int array2[], int number)
                    {
                      cout << " copy array : ";
                      for (int i = 0; i < number; i++)
                      {
                        array2[i] = array[i];
                      }
                      for (int i = 0; i < number; i++)
                      {
                        cout << array2[i] << " ";
                      }
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                    
                      int number = ReadNumber("Please enter the number of elements in the array: ");
                      int array[100];
                      int array2[100];
                    
                      FillArray(array, number, 10, 100); // Fill the array with random numbers
                      printArray(array, number);         // Print the filled array
                    
                      NumberArray2(array, array2, number);
                      return 0;
                    }

## 9-  Write a program to fill the array with a max size of 100 with random numbers from 1 to 100, copy only prime numbers to another array and print it.


                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    enum enPrimNotPrime
                    {
                      Prime = 1,
                      NotPrime = 2
                    };
                    enPrimNotPrime CheckPrime(int Number)
                    {
                      int M = round(Number / 2);
                      for (int Counter = 2; Counter <= M; Counter++)
                      {
                        if (Number % Counter == 0)
                          return enPrimNotPrime::NotPrime;
                      }
                      return enPrimNotPrime::Prime;
                    }
                    int RandomNumber(int From, int To)
                    {
                      int randNum = rand() % (To - From + 1) + From;
                      return randNum;
                    }
                    void FillArrayWithRandomNumbers(int arr[100], int &arrLength)
                    {
                      cout << "\nEnter number of elements:\n";
                      cin >> arrLength;
                      for (int i = 0; i < arrLength; i++)
                        arr[i] = RandomNumber(1, 100);
                    }
                    void CopyOnlyPrimeNumbers(int arrSource[100], int arrDestination[100], int arrLength, int 
                              &arr2Length)
                    {
                      int Counter = 0;
                      for (int i = 0; i < arrLength; i++)
                      {
                        if (CheckPrime(arrSource[i]) == enPrimNotPrime::Prime)
                        {
                          arrDestination[Counter] = arrSource[i];
                          Counter++;
                        }
                      }
                      arr2Length = Counter; // Update arr2Length to the correct value
                    }
                    
                    void PrintArray(int arr[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                        cout << arr[i] << " ";
                      cout << "\n";
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int arr[100], arrLength;
                      FillArrayWithRandomNumbers(arr, arrLength);
                      int arr2[100], arr2Length = 0;
                      CopyOnlyPrimeNumbers(arr, arr2, arrLength, arr2Length);
                      cout << "\nArray 1 elements:\n";
                      PrintArray(arr, arrLength);
                      cout << "\nPrime Numbers in Array2:\n";
                      PrintArray(arr2, arr2Length);
                      return 0;
                    }

## 10 - Write a program to fill array two arrays with max size 100 with random numbers from 1 to 100 , sum their elements in a third array and print the results.

     

                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
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
                    int RandomNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    void ArrayOne(int array[], int number)
                    {
                      for (int i = 0; i < number; i++)
                      {
                        array[i] = RandomNumber(10, 100);
                      }
                    }
                    void ArrayTwo(int array2[], int number)
                    {
                      for (int i = 0; i < number; i++)
                      {
                        array2[i] = RandomNumber(10, 100);
                      }
                    }
                    void printArrayOne(int array[], int number)
                    {
                      cout << "Array One :";
                      for (int i = 0; i < number; i++)
                      {
                        cout << array[i] << " ";
                      }
                      cout << endl;
                    }
                    void printArrayTwo(int array2[], int number)
                    {
                      cout << "Array Two :";
                      for (int i = 0; i < number; i++)
                      {
                        cout << array2[i] << " ";
                      }
                      cout <<endl;
                    }
                    int SumArrayOneAndArrayTwo(int number, int array[], int array2[], int array3[])
                    {
                      cout << "total sum array one and array 2 : ";
                      for (int i = 0; i < number; i++)
                      {
                        array3[i] = array[i] + array2[i];
                        cout << array3[i] << " ";
                      }
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int number = ReadPositiveNumber("Please enter total number in array");
                      int array[100];
                      int array2[100];
                      int array3[100];
                    
                      ArrayOne(array, number);
                      printArrayOne(array, number);
                    
                      ArrayTwo(array2, number);
                      printArrayTwo(array2, number);
                    
                      SumArrayOneAndArrayTwo(number, array, array2, array3);
                    
                      return 0;
                    }


## 11- Write a program to fill array with ordered numbers from 1 to N, then print it, after that shuffle this array and print it after shuffle.

                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
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
                    int RandomNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    void ArrayOne(int array[], int number)
                    {
                      for (int i = 0; i < number; i++)
                      {
                        array[i] = i + 1;
                      }
                    }
                    void ArrayTwo(int array2[], int number)
                    {
                      for (int i = 0; i < number; i++)
                      {
                        array2[i] = RandomNumber(1 , number);
                      }
                    }
                    void printArrayOne(int array[], int number)
                    {
                      cout << "Array One :";
                      for (int i = 0; i < number; i++)
                      {
                        cout << array[i] << " ";
                      }
                      cout << endl;
                    }
                    void printArrayTwo(int array2[], int number)
                    {
                      cout << "Array Two :";
                      for (int i = 0; i < number; i++)
                      {
                        cout << array2[i] << " ";
                      }
                      cout << endl;
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int number = ReadPositiveNumber("Please enter total number in array");
                      int array[100];
                      int array2[100];
                    
                      ArrayOne(array, number);
                      printArrayOne(array, number);
                    
                      ArrayTwo(array2, number);
                      printArrayTwo(array2, number);
                    
                      return 0;
                    }

## 12- Write a program to fill array with max size 100 with random numbers from 1 to 100 , copy it to another array in reverse order and print it.



                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    int ReadPositiveNumber(string message)
                    {
                      int Length = 0;
                      do
                      {
                        cout << message << endl;
                        cin >> Length;
                      } while (Length <= 0);
                      return Length;
                    }
                    int RandomNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    void ArrayOne(int array[], int Length)
                    {
                      for (int i = 0; i < Length; i++)
                      {
                        array[i] = RandomNumber(1, 100);
                      }
                    }
                    void ArrayTwo(int array[], int array2[], int Length)
                    {
                      for (int i = 0; i < Length; i++)
                      {
                        array2[i] = array[Length - i - 1];
                      }
                    }
                    void printArrayOne(int array[], int Length)
                    {
                      cout << "Array One :";
                      for (int i = 0; i < Length; i++)
                      {
                        cout << array[i] << " ";
                      }
                      cout << endl;
                    }
                    void printArrayTwo(int array2[], int Length)
                    {
                      cout << "Array Two :";
                      for (int i = 0; i < Length; i++)
                      {
                        cout << array2[i] << " ";
                      }
                      cout << endl;
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int Length = ReadPositiveNumber("Please enter total number in array");
                      int array[100];
                      int array2[100];
                    
                      ArrayOne(array, Length);
                      printArrayOne(array, Length);
                    
                      ArrayTwo(array,array2, Length);
                      printArrayTwo(array2, Length);
                    
                      return 0;
                    }
                    
## 13- Write a program to read how many keys to generate, fill them in the array, and then print them on the screen.


                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    int ReadPositiveNumber(string message)
                    {
                      int Length = 0;
                      do
                      {
                        cout << message << endl;
                        cin >> Length;
                      } while (Length <= 0);
                      return Length;
                    }
                    int RandomNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    void ArrayOne(string array[], int Length)
                    {
                      for (int x = 0; x < Length; x++)
                      {
                        string key = "";
                        for (int y = 0; y < 4; y++)
                        {
                          for (int i = 0; i < 4; i++)
                          {
                            key += char(RandomNumber(65, 90));
                          }
                          if (y != 3)
                          {
                            key += '-';
                          }
                        }
                        array[x] = key;
                      }
                    }
                    void printArrayOne(string array[], int Length)
                    {
                      cout << "keys :-" <<endl;
                      for (int i = 0; i < Length; i++)
                      {
                          cout << "Key [" << i <<"]"<< array[i] << endl;
                      }
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int Length = ReadPositiveNumber("Please enter total number in array");
                      string array[100];
                    
                      ArrayOne(array, Length);
                      printArrayOne(array, Length);
                    
                      return 0;
                    }
          
## 14- Write a program to fill the array with max size 100 with random numbers from 1 to 100, read the number, and return its index in the array if found otherwise ## 
## return-1.

                            
                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    int ReadPositiveNumber(string message)
                    {
                      int Length = 0;
                      do
                      {
                        cout << message << endl;
                        cin >> Length;
                      } while (Length <= 0);
                      return Length;
                    }
                    int RandomNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    void ArrayOne(int array[], int Length)
                    {
                      for (int i = 0; i < Length; i++)
                      {
                        array[i] = RandomNumber(1, 100);
                      }
                    }
                    void printArrayOne(int array[], int Length)
                    {
                      cout << "Numbers in array: " << endl;
                      for (int i = 0; i < Length; i++)
                      {
                        cout << array[i] << " ";
                      }
                      cout << endl;
                    }
                    void ChooseNumber(int &number)
                    {
                      cout << "Please enter a number" << endl;
                      cin >> number;
                    }
                    void CheckNumber(int array[], int Length, int number)
                    {
                      for (int i = 0; i < Length; i++)
                      {
                        if (array[i] == number)
                        {
                          cout << "the number found at position " << i << endl;
                          cout << "the number found its orders " << i + 1 << endl;
                        }
                        else
                        {
                          cout << "number your are looking or is " << number << "the number is not found :-)" << endl;
                          break;
                        }
                      }
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int Length = ReadPositiveNumber("Please enter total number in array");
                      int array[100];
                      int number;
                    
                      ArrayOne(array, Length);
                      printArrayOne(array, Length);
                      ChooseNumber(number);
                      CheckNumber(array, Length, number);
                      return 0;
                    }

## 15- Write a program to fill the array with max size 100 with random numbers from 1 to 100, read the number, and print if it's found or not (reuse code in the problem).



                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    int ReadPositiveNumber(string message)
                    {
                      int Length = 0;
                      do
                      {
                        cout << message << endl;
                        cin >> Length;
                      } while (Length <= 0);
                      return Length;
                    }
                    int RandomNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    void ArrayOne(int array[], int Length)
                    {
                      for (int i = 0; i < Length; i++)
                      {
                        array[i] = RandomNumber(1, 100);
                      }
                    }
                    void printArrayOne(int array[], int Length)
                    {
                      cout << "Numbers in array: " << endl;
                      for (int i = 0; i < Length; i++)
                      {
                        cout << array[i] << " ";
                      }
                      cout << endl;
                    }
                    void ChooseNumber(int &number)
                    {
                      cout << "Please enter a number" << endl;
                      cin >> number;
                    }
                    void CheckNumber(int array[], int Length, int number)
                    {
                      for (int i = 0; i < Length; i++)
                      {
                        if (array[i] == number)
                        {
                          cout << "Number you are looking for is: " << number << endl;
                          cout << " Yes, The number is found :-) " << endl;
                          break;
                        }
                        else
                        {
                          cout << " Number you are looking for is: " << number << " No, The number is found :-(" << endl;
                          break;
                        }
                      }
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int Length = ReadPositiveNumber("Please enter total number in array");
                      int array[100];
                      int number;
                    
                      ArrayOne(array, Length);
                      printArrayOne(array, Length);
                      ChooseNumber(number);
                      CheckNumber(array, Length, number);
                      return 0;
                    }

## 16 - Write a program to dynamically read numbers and save them in an array max size of the array is 100, and allocate a simi-dynamic array length.


                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    
                    // Function to read a number into the array
                    void ReadNumber(int array[], int index)
                    {
                        cout << "Please enter a number: ";
                        cin >> array[index];
                    }
                    
                    // Function to check numbers in the array
                    void CheckNumber(int array[], int& length)
                    {
                        int Check;
                    
                        cout << "Do you want to add more numbers? (1 for Yes, 0 for No): ";
                        cin >> Check;
                        if (Check == 0)
                        {
                            cout << "Array elements: " << endl;
                            for (int i = 0; i < length; i++)
                            {
                                cout << array[i] << " ";
                            }
                            cout << "\nArray Length: " << length << endl;
                        }
                        else
                        {
                            length++;
                            ReadNumber(array, length);
                            CheckNumber(array, length);
                        }
                    }
                    
                    int main()
                    {
                        int array[100];
                        int length = 0;
                    
                        ReadNumber(array, length);
                        CheckNumber(array, length);
                    
                        return 0;
                    }

## Another solution :
                    
                   #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    
                    int ReadNumber()
                    {
                      int Number;
                      cout << "\nPlease enter a number? ";
                      cin >> Number;
                      return Number;
                    }
                    void AddElements(int Number, int arr[100], int &arrLength)
                    {
                      arrLength++;
                      arr[arrLength - 1] = Number;
                    }
                    void InputUserNumberInArray(int arr[100], int &arrLength)
                    {
                      bool AddMore = true;
                      do
                      {
                        AddElements(ReadNumber(), arr, arrLength);
                        cout << "\n Do you add " << endl;
                        cin >> AddMore;
                      } while (AddMore);
                    }
                    void PrintArray(int arr[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                      {
                        cout << arr[i] << " ";
                      }
                    }
                    int main()
                    {
                      int arr[100], arrLength = 0;
                    
                      InputUserNumberInArray(arr, arrLength);
                      cout << "\n Array Length : " << arrLength << endl;
                      cout << "\n Array elements : " << endl;
                      PrintArray(arr, arrLength);
                      return 0;
                    }


## 17 - Write a program to fill the array with max size 100 with random numbers from 1 to 100, copy it to another array using AddArrayElement, and print it.


                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    
                    int ReadNumber()
                    {
                      int Number;
                      cout << "\nPlease enter a number? ";
                      cin >> Number;
                      return Number;
                    }
                    int NumberInArray(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    
                    void AddElements(int arr[100], int &arrLength, int Number)
                    {
                      for (int i = 0; i < Number; i++)
                      {
                    
                        arr[arrLength++] = NumberInArray(1, 100);
                      }
                    }
                    void CopyArray(int arr[100], int arr2[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                      {
                        arr2[i] = arr[i];
                      }
                    }
                    void PrintArray(int arr[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                      {
                        cout << arr[i] << " ";
                      }
                    }
                    void PrintArray2(int arr2[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                      {
                        cout << arr2[i] << " ";
                      }
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int arr[100], arrLength = 0 , arr2[100];
                    
                      int Number = ReadNumber();
                    
                      AddElements(arr, arrLength, Number);
                      cout << "\n Array Length : " << arrLength << endl;
                    
                      CopyArray(arr , arr2 , arrLength);
                    
                      cout << "\n Array 1 elements : " << endl;
                      PrintArray(arr, arrLength);
                    
                      cout << "\nArray 2 elements : " << endl;
                      PrintArray(arr2, arrLength);
                    
                      return 0;
                    }
## Another solution:-
                     
                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    
                    int RandomNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    
                    void FillArrayWithRandomNumbers(int arr[100], int &arrLength)
                    {
                      cout << "\nEnter number of elements \n";
                      cin >> arrLength;
                    
                      for (int i = 0; i < arrLength; i++)
                      {
                        arr[i] = RandomNumber(1, 100);
                      }
                    }
                    
                    void PrintArray(int arr[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                      {
                        cout << arr[i] << " ";
                      }
                    }
                    
                    void CopyArray(int arrSource[100], int arrDestination[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                      {
                        arrDestination[i] = arrSource[i];
                      }
                    }
                    
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int arr[100], arrLength = 0, arr2[100], arr2Length = 0;
                    
                      FillArrayWithRandomNumbers(arr, arrLength);
                    
                      cout << "\nArray Length : " << arrLength << endl;
                    
                      CopyArray(arr, arr2, arrLength);
                    
                      cout << "\nArray 1 elements : " << endl;
                      PrintArray(arr, arrLength);
                    
                      cout << "\nArray 2 elements : " << endl;
                      PrintArray(arr2, arrLength); // Use arrLength instead of arr2Length
                    
                      return 0;
                    }

## 18- Write a program to fill the array with max size 100 with random numbers from 1 to 100, copy only odd numbers to another array using AddArrayElement, and print it.



                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    
                    int RandomNumber(int from, int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    
                    void FillArrayWithRandomNumbers(int arr[100], int &arrLength)
                    {
                      cout << "\nEnter number of elements \n";
                      cin >> arrLength;
                    
                      for (int i = 0; i < arrLength; i++)
                      {
                        arr[i] = RandomNumber(1, 100);
                      }
                    }
                    
                    void PrintArray1(int arr[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                      {
                        cout << arr[i] << " ";
                      }
                    }
                    
                    void CopyArray(int arrSource[100], int arrDestination[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                      {
                        arrDestination[i] = arrSource[i];
                      }
                    }
                    void PrintArray2(int arr[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                      {
                        if(arr[i] % 2 != 0)
                          cout << arr[i] <<" ";
                      }
                    }
                    
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int arr[100], arrLength = 0, arr2[100], arr2Length = 0;
                    
                      FillArrayWithRandomNumbers(arr, arrLength);
                    
                      cout << "\nArray Length : " << arrLength << endl;
                    
                      CopyArray(arr, arr2, arrLength);
                    
                      cout << "\nArray 1 elements : " << endl;
                      PrintArray1(arr, arrLength);
                    
                      cout << "\nArray 2 elements : " << endl;
                      PrintArray2(arr2, arrLength); // Use arrLength instead of arr2Length
                    
                      return 0;
                    }

## 19-  Write a program to fill the array with numbers, then print distinct numbers to another array. 
 
                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    void FillArray(int arr[100], int &arrLength)
                    {
                      arrLength = 10;
                      arr[0] = 10;
                      arr[1] = 10;
                      arr[2] = 10;
                      arr[3] = 50;
                      arr[4] = 50;
                      arr[5] = 70;
                      arr[6] = 70;
                      arr[7] = 70;
                      arr[8] = 70;
                      arr[9] = 70;
                      arr[10] = 90;
                    }
                    
                    void PrintArray(int arr[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                      {
                        cout << arr[i] << " "
                             << "\n";
                      }
                    }
                    short FindNumberPositionInArray(int number, int arr[100], int arrLength)
                    {
                      for (int i = 0; i < arrLength; i++)
                      {
                        if (arr[i] == number)
                          return i;
                      }
                      return -1;
                    }
                    bool IsNumbersInArray(int number, int arr[100], int arrLength)
                    {
                      return FindNumberPositionInArray(number, arr, arrLength) != -1;
                    }
                    void AddArrayElement(int Number, int arr[100], int &arrLength)
                    {
                      arrLength++;
                      arr[arrLength - 1] = Number;
                    }
                    void CopyDistinctNumbersToArray(int arrSource[100], int arrDestination[100], int SourceLength, int &DestinationLength)
                    {
                      for (int i = 0; i < SourceLength; i++)
                      {
                        if (!IsNumbersInArray(arrSource[i], arrDestination, DestinationLength))
                        {
                          AddArrayElement(arrSource[i], arrDestination, DestinationLength);
                        }
                      };
                    }
                    int main()
                    {
                      int arrSource[100], SourceLength = 0, arrDestination[100], DestinationLength = 0;
                      FillArray(arrSource, SourceLength);
                      cout << "\nArray 1 elements:\n";
                      PrintArray(arrSource, SourceLength);
                      CopyDistinctNumbersToArray(arrSource, arrDestination, SourceLength, DestinationLength);
                      cout << "\nArray 2 distinct elements:\n";
                      PrintArray(arrDestination, DestinationLength);
                      return 0;
                    }
## 20 - Write a program to fill the array with numbers, then check if it is a Palindrome array or not, Note: Palindrome array can be read the same from right to left and from left to right.

                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    int ReadNumberOfArrayLength(int &Length)
                    {
                      cout << "Please enter a length of array : ";
                      cin >> Length;
                    }
                    void FillArray(int Length, int arr[])
                    {
                      cout << "Please enter" << Length << "numbers for the array: " << endl;
                      for (int i = 0; i < Length; i++)
                      {
                        cin >> arr[i];
                      }
                    }
                    void PrintArray(int Length, int arr[])
                    {
                      cout << "Array 1 Element" << endl;
                      for (int i = 0; i < Length; i++)
                      {
                        cout << arr[i] << " ";
                      }
                    }
                    void CopyArray(int Length, int arr[], int arr2[])
                    {
                      for (int i = 0; i < Length; i++)
                      {
                        arr2[i] = arr[Length - 1 - i];
                      }
                    }
                    void PrintArray2(int Length, int arr2[])
                    {
                      cout << "\n Array 2 Element" << endl;
                    
                      for (int i = 0; i < Length; i++)
                      {
                        cout << arr2[i] << " ";
                      }
                    }
                    int CheckArray(int Length, int arr[], int arr2[])
                    {
                      for (int i = 0; i < Length; i++)
                      {
                        if (arr[i] == arr2[i])
                        {
                          return true;
                        }
                      }
                    }
                    void check(int Length, int arr[], int arr2[])
                    {
                      if (CheckArray(Length, arr, arr2) == true)
                      {
                        cout << " \n Palindrome" << endl;
                      }
                    }
                    int main()
                    {
                      int arr[100], Length = 0, arr2[100];
                    
                      ReadNumberOfArrayLength(Length);
                    
                      FillArray(Length, arr);
                      PrintArray(Length, arr);
                    
                      CopyArray(Length, arr, arr2);
                      PrintArray2(Length, arr2);
                    
                      check(Length, arr, arr2);
                      return 0;
                    }
## another solution  :-
                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    int ReadNumberOfArrayLength(int &Length)
                    {
                      cout << "Please enter a length of array : ";
                      cin >> Length;
                    }
                    void FillArray(int Length, int arr[])
                    {
                      cout << "Please enter" << Length << "numbers for the array: " << endl;
                      for (int i = 0; i < Length; i++)
                      {
                        cin >> arr[i];
                      }
                    }
                    void PrintArray(int Length, int arr[])
                    {
                      cout << "Array 1 Element" << endl;
                      for (int i = 0; i < Length; i++)
                      {
                        cout << arr[i] << " ";
                      }
                    }
                    bool IsPalindromeArray(int Length, int arr[])
                    {
                      for (int i = 0; i < Length; i++)
                      {
                        if (arr[i] = arr[Length - 1 - i])
                        {
                          return false;
                        }
                      }
                        return true;
                    }
                    int main()
                    {
                      int arr[100], Length = 0;
                    
                      ReadNumberOfArrayLength(Length);
                    
                      FillArray(Length, arr);
                      PrintArray(Length, arr);
                    
                      if(IsPalindromeArray(Length , arr))
                        cout<<"\n Yes array is Palindrome \n" ;
                      else
                        cout<<"\n Yes array is Palindrome \n";
                        
                      return 0;
                    }

## 21 - Writ a program to fill array with max size 100 with random numbers from 1 to 100, then print the count of Odd numbers.

                              #include <iostream>
                              #include <string>
                              #include <cmath>
                              #include <cstdlib> // For rand and srand
                              #include <ctime>   // For time function
                              using namespace std;
                              int ReadNumberOfArrayLength(int &Length)
                              {
                                cout << "Please enter a length of array : ";
                                cin >> Length;
                              }
                              int RandomNumber(int from , int to)
                              {
                                int randNum = rand() % (to - from + 1) + from;
                                return randNum;
                              }
                              void FillArray(int Length, int arr[])
                              {
                                for (int i = 0; i < Length; i++)
                                {
                                  arr[i] = RandomNumber(1, 100);
                                }
                              }
                              void PrintArray(int Length, int arr[])
                              {
                                cout << "Array 1 Element" << endl;
                                for (int i = 0; i < Length; i++)
                                {
                                  cout << arr[i] << " ";
                                }
                              }
                              void CalcOddNumber(int Length, int arr[])
                              {
                                int counter = 0;
                                for (int i = 0; i < Length; i++)
                                {
                                  if (arr[i] % 2 != 0)
                                    counter++;
                                }
                                cout << "\n Odd Numbers count is: " << counter << endl;
                              }
                              int main()
                              {
                                srand((unsigned)time(NULL));
                                int arr[100], Length = 0;
                              
                                ReadNumberOfArrayLength(Length);
                              
                                FillArray(Length, arr);
                                PrintArray(Length, arr);
                              
                                CalcOddNumber(Length, arr);
                                return 0;
                              }

## 22-  Writ a program to fill array with max size 100 with random numbers from 1 to 100, then print the count Of Even numbers.

                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    int ReadNumberOfArrayLength(int &Length)
                    {
                      cout << "Please enter a length of array : ";
                      cin >> Length;
                    }
                    int RandomNumber(int from , int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    void FillArray(int Length, int arr[])
                    {
                      for (int i = 0; i < Length; i++)
                      {
                        arr[i] = RandomNumber(1, 100);
                      }
                    }
                    void PrintArray(int Length, int arr[])
                    {
                      cout << "Array 1 Element" << endl;
                      for (int i = 0; i < Length; i++)
                      {
                        cout << arr[i] << " ";
                      }
                    }
                    void CalcEvenNumber(int Length, int arr[])
                    {
                      int counter = 0;
                      for (int i = 0; i < Length; i++)
                      {
                        if (arr[i] % 2 == 0)
                          counter++;
                      }
                      cout << "\n Odd Numbers count is: " << counter << endl;
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int arr[100], Length = 0;
                    
                      ReadNumberOfArrayLength(Length);
                    
                      FillArray(Length, arr);
                      PrintArray(Length, arr);
                    
                      CalcEvenNumber(Length, arr);
                      return 0;
                    }
  ## 23 - Writ a program to fill array with max size 100 with random numbers from -100 to 100, then print the count Of Negative numbers.                  
                    

                              #include <iostream>
                              #include <string>
                              #include <cmath>
                              #include <cstdlib> // For rand and srand
                              #include <ctime>   // For time function
                              using namespace std;
                              int ReadNumberOfArrayLength(int &Length)
                              {
                                cout << "Please enter a length of array : ";
                                cin >> Length;
                              }
                              int RandomNumber(int from , int to)
                              {
                                int randNum = rand() % (to - from + 1) + from;
                                return randNum;
                              }
                              void FillArray(int Length, int arr[])
                              {
                                for (int i = 0; i < Length; i++)
                                {
                                  arr[i] = RandomNumber(-100, 100);
                                }
                              }
                              void PrintArray(int Length, int arr[])
                              {
                                cout << "Array 1 Element" << endl;
                                for (int i = 0; i < Length; i++)
                                {
                                  cout << arr[i] << " ";
                                }
                              }
                              void CalcNegativeNumber(int Length, int arr[])
                              {
                                int counter = 0;
                                for (int i = 0; i < Length; i++)
                                {
                                  if (arr[i] > 0)
                                    counter++;
                                }
                                cout << "\n Negative Numbers count is: " << counter << endl;
                              }
                              int main()
                              {
                                srand((unsigned)time(NULL));
                                int arr[100], Length = 0;
                              
                                ReadNumberOfArrayLength(Length);
                              
                                FillArray(Length, arr);
                                PrintArray(Length, arr);
                              
                                CalcNegativeNumber(Length, arr);
                                return 0;
                              }

## 23 - Writ a program to fill array with max size 100 with random numbers from -100 to 100, then print the count Of positive numbers.   

                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    int ReadNumberOfArrayLength(int &Length)
                    {
                      cout << "Please enter a length of array : ";
                      cin >> Length;
                    }
                    int RandomNumber(int from , int to)
                    {
                      int randNum = rand() % (to - from + 1) + from;
                      return randNum;
                    }
                    void FillArray(int Length, int arr[])
                    {
                      for (int i = 0; i < Length; i++)
                      {
                        arr[i] = RandomNumber(-100, 100);
                      }
                    }
                    void PrintArray(int Length, int arr[])
                    {
                      cout << "Array 1 Element" << endl;
                      for (int i = 0; i < Length; i++)
                      {
                        cout << arr[i] << " ";
                      }
                    }
                    void CalcPositiveNumber(int Length, int arr[])
                    {
                      int counter = 0;
                      for (int i = 0; i < Length; i++)
                      {
                        if (arr[i] > 0)
                          counter++;
                      }
                      cout << "\n positive Numbers count is: " << counter << endl;
                    }
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int arr[100], Length = 0;
                    
                      ReadNumberOfArrayLength(Length);
                    
                      FillArray(Length, arr);
                      PrintArray(Length, arr);
                    
                      CalcPositiveNumber(Length, arr);
                      return 0;
                    }
## 24- Write a program to print abs of numbers, don't use the built-in abs function.

                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    float ReadNumber(float &Number)
                    {
                      cout << "Please enter Number : ";
                      cin >> Number;
                    }
                    float MyABS(float Number)
                    {
                      if (Number > 0)
                        return Number;
                      else
                        return Number * -1;
                    }
                    int main()
                    {
                      float Number = 0;
                      ReadNumber(Number);
                    
                      cout << "My abs result : " << MyABS(Number);
                      cout << "C++ abs result : " << abs(Number);
                      return 0;
                    }

## 25 - Write a program to print a round of numbers, don't use the built-in round function.


                              #include <iostream>
                              #include <string>
                              #include <cmath>
                              #include <cstdlib> // For rand and srand
                              #include <ctime>   // For time function
                              using namespace std;
                              float ReadNumber(float &Number)
                              {
                                cout << "Please enter Number : ";
                                cin >> Number;
                              }
                              float FractionFunction(float Number, float Fraction)
                              {
                                Fraction = Number - int(Number);
                                return Fraction;
                              }
                              float RoundFunction(float Number, float Fraction)
                              {
                                int Input = int(Number);
                                if (abs(Fraction) >= 0.5)
                                {
                                  if (Number > 0)
                                  {
                                    return Input++;
                                  }
                                  else
                                  {
                                    return --Input;
                                  }
                                }
                                else
                                {
                                  return Input;
                                }
                              }
                              int main()
                              {
                                float Number = 0, Fraction;
                                ReadNumber(Number);
                              
                                FractionFunction(Number, Fraction);
                              
                                cout << "My abs result : " << RoundFunction(Number, Fraction) <<endl;
                                cout << "C++ abs result : " << round(Number) <<endl;
                                return 0;
                              }

## 26 - Write a program to print the floor of Numbers, don't use the built-in floor function.

                              #include <iostream>
                              #include <string>
                              #include <cmath>
                              #include <cstdlib> // For rand and srand
                              #include <ctime>   // For time function
                              using namespace std;
                              float ReadNumber(float &Number)
                              {
                                cout << "Please enter Number : ";
                                cin >> Number;
                              }
                              float FractionFunction(float Number, float Fraction)
                              {
                                Fraction = Number - int(Number);
                                return Fraction;
                              }
                              float FloorFunction(float Number, float Fraction)
                              {
                                int Input = int(Number);
                                if (abs(Fraction) >= 0.5)
                                {
                                  if (Number > 0)
                                  {
                                    return --Input;
                                  }
                                  else
                                  {
                                    return --Input;
                                  }
                                }
                                else
                                {
                                  return Input;
                                }
                              }
                              int main()
                              {
                                float Number = 0, Fraction;
                                ReadNumber(Number);
                              
                                FractionFunction(Number, Fraction);
                              
                                cout << "My abs result : " << FloorFunction(Number, Fraction) <<endl;
                                cout << "C++ abs result : " << floor(Number) <<endl;
                                return 0;
                              }

## 27- Write a program to print Ceil of numbers, don't use built in Ceil function. 

                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    float ReadNumber(float &Number)
                    {
                      cout << "Please enter Number : ";
                      cin >> Number;
                    }
                    float FractionFunction(float Number, float &Fraction)
                    {
                      Fraction = Number - int(Number);
                      return Fraction;
                    }
                    float CeilFunction(float Number, float Fraction)
                    {
                      if (abs(Fraction) > 0)
                        if (Number > 0)
                          return int(Number) + 1;
                        else
                          return int(Number);
                      else
                        return Number;
                    }
                    int main()
                    {
                      float Number = 0, Fraction = 0;
                      ReadNumber(Number);
                    
                      FractionFunction(Number, Fraction);
                    
                      cout << "My abs result : " << CeilFunction(Number, Fraction) << endl;
                      cout << "C++ abs result : " << ceil(Number) << endl;
                      return 0;
                    }

## 28- Write a program to print Sqrt of numbers, don't use built in sqrt function.

                    #include <iostream>
                    #include <string>
                    #include <cmath>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    int ReadNumber(int &Number)
                    {
                      cout << "Please enter Number : ";
                      cin >> Number;
                    }
                    int SqrtFunction(int Number)
                    {
                      return pow(Number , .5);
                    }
                    int main()
                    {
                      int Number = 0;
                      ReadNumber(Number);
                    
                    
                      cout << "My abs result : " << SqrtFunction(Number) << endl;
                      cout << "C++ abs result : " << sqrt(Number) << endl;
                      return 0;
                    }

## 29- Math Game 
                    #include <iostream>
                    #include <string>
                    #include <cstdlib> // For rand and srand
                    #include <ctime>   // For time function
                    using namespace std;
                    
                    int ReadNumberOfIteration(int &Counter1)
                    {
                      do
                      {
                        cout << "How many questions do you want to answer? ";
                        cin >> Counter1;
                      } while (Counter1 <= 0);
                      return Counter1;
                    }
                    
                    int ReadLevel(int &Number)
                    {
                      do
                      {
                        cout << "Enter Question Level [1] Easy, [2] Medium, [3] Hard, [4] Mix: ";
                        cin >> Number;
                      } while (Number > 4 || Number < 1);
                      return Number;
                    }
                    
                    int ReadOperation(int &Number3)
                    {
                      do
                      {
                        cout << "Enter Question Type [1] Add, [2] Sub, [3] Mul, [4] Div, [5] Mix: ";
                        cin >> Number3;
                      } while (Number3 > 5 || Number3 < 1);
                      return Number3;
                    }
                    
                    int RandomNumber(int from, int to)
                    {
                      return rand() % (to - from + 1) + from;
                    }
                    
                    int RandomArray(int f, int t)
                    {
                      return rand() % (t - f + 1) + f;
                    }
                    double MixLevels(int arr[3], int Counter1)
                    {
                        arr[0] = RandomNumber(1, 10);
                        arr[1] = RandomNumber(1, 50);
                        arr[2] = RandomNumber(1, 100);
                    
                        for (int i = 0; i < Counter1; i++)
                        {
                            arr[RandomArray(0, 2)];
                        }
                        return arr[RandomArray(0, 2)]; 
                    }
                    
                    void GenerateNumbers(int arr[3], int Counter1, int &Value1, int &Value2, int Number)
                    {
                      Value1 = 0, Value2 = 0;
                      switch (Number)
                      {
                      case 1:
                        Value1 = RandomNumber(1, 10);
                        Value2 = RandomNumber(1, 10);
                        break;
                      case 2:
                        Value1 = RandomNumber(1, 50);
                        Value2 = RandomNumber(1, 50);
                        break;
                      case 3:
                        Value1 = RandomNumber(1, 100);
                        Value2 = RandomNumber(1, 100);
                        break;
                      case 4:
                        Value1 =  arr[RandomArray(0, 2)];
                        Value2 =  arr[RandomArray(0, 2)];
                        break;
                      default:
                        break;
                      }
                    }
                    
                    void CheckFunction(int Number2, int Value3)
                    {
                      if (Number2 == Value3)
                      {
                        system("color 2f");
                      }
                      else
                      {
                        cout << "Correct Answer = " << Value3 << endl;
                        system("color 4f");
                      }
                    }
                    
                    int AddFunction(int arr[3], int Counter1, int Number, int &Number2, int &Value3)
                    {
                      int Value1, Value2;
                    
                      GenerateNumbers(arr, Counter1, Value1, Value2, Number);
                      Value3 = Value1 + Value2;
                    
                      cout << Value1 << " + " << Value2 << " = ";
                      cin >> Number2;
                      CheckFunction(Number2, Value3);
                    }
                    
                    int SubFunction(int arr[3], int Counter1, int Number, int &Number2, int &Value3)
                    {
                      int Value1, Value2;
                    
                      GenerateNumbers(arr, Counter1, Value1, Value2, Number);
                      Value3 = Value1 - Value2;
                    
                      cout << Value1 << " - " << Value2 << " = ";
                      cin >> Number2;
                      CheckFunction(Number2, Value3);
                    }
                    
                    int MultiFunction(int arr[3], int Counter1, int Number, int &Number2, int &Value3)
                    {
                      int Value1, Value2;
                    
                      GenerateNumbers(arr, Counter1, Value1, Value2, Number);
                      Value3 = Value1 * Value2;
                    
                      cout << Value1 << " * " << Value2 << " = ";
                      cin >> Number2;
                      CheckFunction(Number2, Value3);
                    }
                    
                    int DivFunction(int arr[3], int Counter1, int Number, int &Number2, int &Value3)
                    {
                      int Value1, Value2;
                    
                      GenerateNumbers(arr, Counter1, Value1, Value2, Number);
                      Value3 = Value1 / Value2;
                    
                      cout << Value1 << " / " << Value2 << " = ";
                      cin >> Number2;
                      CheckFunction(Number2, Value3);
                    }
                    int MixFunction(int arr2[4], int arr[3], int Number, int Number2, int Value3, int Counter1)
                    {
                      arr2[0] = AddFunction(arr, Counter1, Number, Number2, Value3);
                      arr2[1] = SubFunction(arr, Counter1, Number, Number2, Value3);
                      arr2[2] = DivFunction(arr, Counter1, Number, Number2, Value3);
                      arr2[3] = MultiFunction(arr, Counter1, Number, Number2, Value3);
                    
                      for (int i = 0; i < Counter1; i++)
                      {
                        arr2[RandomArray(0, 3)];
                      }
                    }
                    double Easy(int arr2[4], int arr[3], int Number, int Number2, int Counter1, int Number3, int Value3)
                    {
                      if (Number == 1 && Number3 == 1)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          AddFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 1 && Number3 == 2)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          SubFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 1 && Number3 == 3)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          MultiFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 1 && Number3 == 4)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          DivFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 1 && Number3 == 5)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          MixFunction(arr2, arr, Number, Number2, Value3, Counter1);
                        }
                      }
                    }
                    
                    double Medium(int arr2[4] ,int arr[3], int Number, int Number2, int Counter1, int Number3, int Value3)
                    {
                      if (Number == 2 && Number3 == 1)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          AddFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 2 && Number3 == 2)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          SubFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 2 && Number3 == 3)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          MultiFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 2 && Number3 == 4)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          DivFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                        else if (Number == 2 && Number3 == 5)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          MixFunction(arr2, arr, Number, Number2, Value3, Counter1);
                        }
                      }
                    }
                    
                    double Hard(int arr2[4] ,int arr[3], int Number, int Number2, int Counter1, int Number3, int Value3)
                    {
                      if (Number == 3 && Number3 == 1)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          AddFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 3 && Number3 == 2)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          SubFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 3 && Number3 == 3)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          MultiFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 3 && Number3 == 4)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          DivFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                        else if (Number == 3 && Number3 == 5)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          MixFunction(arr2, arr, Number, Number2, Value3, Counter1);
                        }
                      }
                    }
                    int Mix(int arr2[4],int arr[3] , int Number, int Number2, int Counter1, int Number3, int Value3)
                    {
                      if (Number == 4 && Number2 == 1)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          AddFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 4 && Number3 == 2)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          SubFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 4 && Number3 == 3)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          MultiFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 4 && Number3 == 4)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          DivFunction(arr, Counter1, Number, Number2, Value3);
                        }
                      }
                      else if (Number == 4 && Number3 == 5)
                      {
                        for (int i = 0; i < Counter1; i++)
                        {
                          MixFunction(arr2, arr, Number, Number2, Value3, Counter1);
                        }
                      }
                    }
                    
                    int main()
                    {
                      srand((unsigned)time(NULL));
                      int Counter1 = 0, Number = 0, Number3 = 0, arr2[4], arr[3], Value3 = 0, Number2 = 0;
                      ReadNumberOfIteration(Counter1);
                      ReadLevel(Number);
                      ReadOperation(Number3);
                    
                      Easy(arr2,arr, Number, Number2, Counter1, Number3, Value3);
                      Medium(arr2,arr, Number, Number2, Counter1, Number3, Value3);
                      Hard(arr2,arr, Number, Number2, Counter1, Number3, Value3);
                      Mix(arr, arr2, Number, Number2, Counter1, Number3, Value3);
                    
                      return 0;
                    }


## 30 - Write a program to do the following Using the ternary Operator, a Program to check if the Number is Positive or Negative.

                    #include <iostream>
                    using namespace std;
                    
                    int main()
                    {
                      int Number = 0;
                      cout << "Please enter a number:";
                      cin >> Number;
                    
                      (Number == 0) ? cout << "0" : (Number >= 0) ? cout << "Positive"
                                                                  : cout << "Negative";
                      ;
                    
                      return 0;
                    }

## 31 - Ranged Loop:-


                              #include <iostream>
                              using namespace std;
                              
                              int main()
                              {
                              
                                int arr[] = {
                                    1,
                                    2,
                                    3,
                                    4,
                                    5,
                                    6,
                                    6,
                                    6,
                                    6,
                                };
                              
                                for (int n : arr)
                                {
                                  cout << n;
                                }
                                return 0;
                              }

## 32 - Validation Number:-

                    #include <iostream>
                    #include <limits> // Include for std::numeric_limits
                    using namespace std;
                    
                    int ReadNumber() {
                        int Number = 0;
                        cout << "Please enter a number: ";
                        cin >> Number;
                    
                        while (cin.fail()) {
                            cin.clear(); // Clear the error state of cin
                            cin.ignore(numeric_limits<streamsize>::max(), '\n'); // Ignore any invalid input in the buffer
                            cout << "Invalid input. Please enter a valid number: ";
                            cin >> Number; // Try reading input again
                        }
                    
                        return Number;
                    }
                    
                    int main() {
                        cout << "Your Number is: " << ReadNumber() << endl;
                        return 0;
                    }
## 33 - BitWise AND Operatin (&):-
                    #include <iostream>
                    #include <limits> 
                    using namespace std;
                    
                    int main() {
                        cout << "Result:"<<(12 & 25) << endl;
                        return 0;
                    }

## 34 -  BitWise OR Operatin (|) :-

                    #include <iostream>
                    using namespace std;
                    
                    int main() {
                        cout << "Result:"<<(12 | 25) << endl;
                        return 0;
                    }
## 35 - Decleraion and Definiation :-

                    #include <iostream>
                    using namespace std;
                    void add(int , int ); // Declaration
                    
                    int main() {
                        add(20 ,20);
                        return 0;
                    }
                      // definition
                    void add(int a , int b){
                      cout << a + b << endl;
                    }

## 36 - Default Parametter :-

                    #include <iostream>
                    using namespace std;
                    int add(int a, int b, int c, int d = 0)
                    {
                      return (a + b + c + d);
                    }
                    
                    int main()
                    {
                      cout << add(1, 2, 3);
                      cout << add(1, 2, 3, 4);
                    }

## 37 - Recursion Print Numbers From 1 to 4:-

          #include <iostream>
          using namespace std;
          
          void PrintNumber(int N, int M)
          {
          	if (N <= M)
          	{
          		cout << N << endl;
          		PrintNumber(N + 1, M);
          	}
          }
          int main()
          {
          	PrintNumber(1, 4);
          	return 0;
          }
          
## 38 - Recursion Print Numbers From 4 to 1:-        

                    #include <iostream>
                    using namespace std;
                    
                    void PrintNumber(int N, int M)
                    {
                    	if (N <= M)
                    	{
                    		cout << M << endl;
                    		PrintNumber(N, M -1 );
                    	}
                    }
                    int main()
                    {
                    	PrintNumber(1, 4);
                    	return 0;
                    }
 
## 39 - using Recursion write program to calculate power N^m:-   



                    #include <iostream>
                    using namespace std;
                    
                    int MyPower(int Base, int Power) {
                    	if (Power == 0) {
                    		return 1;
                    	}
                    	else {
                    		return(Base * MyPower(Base, Power - 1));
                    	}
                    }
                    int main() {
                    
                    	cout << MyPower(2, 4);
                    
                    	return 0;
                    
                    }

## 40 - Static Variable:-


                    #include <iostream>
                    using namespace std;
                    
                    void MyFunction() {
                    	static	 int Number = 1;
                    
                    	cout << "Result = " << Number << endl;
                    	Number++;
                    }
                    int main() {
                    
                    	MyFunction();
                    	MyFunction();
                    	MyFunction();
                    
                    	return 0;
                    }
## 41 - auto Variables:-

                    #include <iostream>
                    using namespace std;
                    
                    int main() {
                    	auto x = 5;
                    	auto y = 11.3;
                    	auto z = "Mustafa Saad";
                    
                    	cout << x << endl;
                    	cout << y << endl;
                    	cout << z << endl;
                    
                    	return 0;
                    
                    }

## 42 - Integer Formatting:-


                    #include <iostream>
                    using namespace std;
                    
                    int main() {
                    	int Page = 1, TotalPage = 10;
                    
                    	printf("The page number =  %d \n", Page);
                    	printf("You are in Page %d of % d \n", Page, TotalPage);
                    
                    
                    	printf("The page number = %0*d \n", 2, Page);
                    	printf("The page number = %0*d \n", 3, Page);
                    	printf("The page number = %0*d \n", 4, Page);
                    	printf("The page number = %0*d \n", 5, Page);
                    
                    	int Number1 = 20, Number2 = 30;
                    	printf("The Result of %d + %d = %d \n", Number1, Number1, Number1 + Number2);
                    
                    	return 0;
                    
                              }

## 43 - float format (print)


#include <iostream>
using namespace std;

int main() {

                    	// float format (printf) ;
                    
                    	float Pi = 3.14232423;
                    
                    	printf("Percison specification of %.*f \n", 1, Pi);
                    	printf("Percison specification of %.*f \n", 2, Pi);
                    	printf("Percison specification of %.*f  \n", 3, Pi);
                    	printf("Percison specification of %.*f  \n", 4, Pi);
                    
                    
                    	float x = 7.0, y = 9.0;
                    
                    	printf("\n The Float division is : %.3f / %.3f = %.3f \n", x, y, x / y);
                    
                    	double d = 23.34;
                    	printf("The double value is : %.3f \n", d);
                    	printf("The double value is : %.4f \n", d);
                    
                    	return 0;
                    
                            }

## 44 - String and Char Formatting (printf)
   
                              #include <iostream>
                              using namespace std;
                              
                              int main() {
                              
                              	// String and Char formatting 
                              
                              	char Name[] = "Mustafa saad";
                              	char School[] = "Mansoura  unviersity ";
                              
                              	printf("Welcome %s \n", Name);
                              	printf("your school is  %s \n", School);
                              
                              	char c = 'b';
                              
                              	printf("the char is %*c \n", 1, c);
                              	printf("the char is %*c \n", 2, c);
                              	printf("the char is %*c \n", 3, c);
                              	printf("the char is %*c \n", 4, c);
                              
                              
                              	return 0;
                              
                              }
## 45 - Two Dimensional Array 


#include <iostream>
                   
                    using namespace std;
                    int main() {
                    	
                    	// Two Dimensional Array
                    
                    	int x[3][4] = { {1,2,3,4},{5,6,7,8},{9,10,11,12} };
                    
                    	for (int i = 0; i < 3; i++) {
                    		for (int j = 0; j < 4; j++) {
                    			cout << x[i][j] ;
                    		}
                    		cout << endl;
                    	}
                    	return 0;
                    
                    }

## 46 -  Write a program to store the multiplication table results in 10 * 10 and print the result.

                    #include <iostream>
                    #include <iomanip>
                    using namespace std;
                    
                    int main() {
                    
                    	// Two Dimensional Array
                    
                    	int x[10][10] = { {1,2,3,4,5,6,7,8,9,10},{1,2,3,4,5,6,7,8,9,10},{1,2,3,4,5,6,7,8,9,10},
                    		{1,2,3,4,5,6,7,8,9,10},{1,2,3,4,5,6,7,8,9,10},{1,2,3,4,5,6,7,8,9,10},{1,2,3,4,5,6,7,8,9,10},
                    		{1,2,3,4,5,6,7,8,9,10},{1,2,3,4,5,6,7,8,9,10},{1,2,3,4,5,6,7,8,9,10} };
                    
                    	for (int i = 0; i < 10; i++) {
                    		for (int j = 0; j < 10; j++) {
                    			cout << setw(4) <<(x[i][j] * (i + 1)) ;
                    		}
                    		cout << endl;
                    	}
                    
                    	return 0;
                    
## 47 - Another Solution

                    #include <iostream>
                    #include <iomanip>
                    using namespace std;
                    
                    int main() {
                    
                    	// Two Dimensional Array
                    
                    	int x[10][10];
                    
                    	for (int i = 0; i < 10; i++) {
                    		for (int j = 0; j < 10; j++) {
                    			x[i][j] = (i + 1) * (j + 1);
                    		}
                    	}
                    	for (int i = 0; i < 10; i++) {
                    		for (int j = 0; j < 10; j++) {
                    			printf(" %0*d ", 2, x[i][j]);
                    		}
                    		cout << endl;
                    	}
                    
                    	return 0;
                    
                    }


## 48 - pointer and array 

                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    int main() {
                        int arr[4] = { 10, 20, 30, 40 };
                        int* ptr;
                        ptr = arr;
                    
                        cout << "Addresses are : \n" << endl;
                        for (int i = 0; i < 4; i++) {
                            cout << ptr + i << endl;
                        }
                    
                        cout << "\nValues are : \n" << endl;
                    
                        for (int i = 0; i < 4; i++) {
                            cout << *(ptr + i) << endl;
                        }
                    
                        return 0;
                    }

## 49 - pointer and array


                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    int main() {
                        int arr[4] = { 10, 20, 30, 40 };
                        int* ptr;
                        ptr = arr;
                    
                        cout << "Addresses are : \n" << endl;
                        for (int i = 0; i < 4; i++) {
                            cout << ptr + i << endl;
                        }
                    
                        cout << "\nValues are : \n" << endl;
                    
                        for (int i = 0; i < 4; i++) {
                            cout << *(ptr + i) << endl;
                        }
                    
                        return 0;
                    }


## 50 - pointer and structure

                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    struct stElemet {
                    	string name;
                    	float salary;
                    };
                    int main() {
                    	stElemet Element1, * ptr;
                    
                    	Element1.name = "Mustafa sad";
                    	Element1.salary = 5000;
                        
                    	cout << Element1.name << endl;
                    	cout << Element1.salary << endl;
                    
                    	ptr = &Element1;
                    
                    	cout << ptr->name << endl;
                    	cout << ptr->salary << endl;
                    
                    	return 0;
                    
                    }


## 51 - pointer and void 

                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    int main() {
                    
                    	void* ptr;
                    	int x = 50;
                    	float f1 = 10.5;
                    
                    	ptr = &f1;
                    	cout << *(static_cast<float*>(ptr))<< endl;
                    	cout << ptr << endl;
                    
                    	ptr = &x;
                    
                    	cout << ptr << endl;
                    	cout << *(static_cast<int*>(ptr));
                    
                    	return 0;
                    
                    }

## 52 - Dynamic memory allocation new and delete 

                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    int main() {
                    
                    	int* ptrx;
                    	float* ptry;
                    
                    	ptrx = new int;
                    	ptry = new float;
                    
                    	*ptrx = 1213;
                    	*ptry = 10.343;
                    
                    	cout << *ptrx << endl;
                    	cout << *ptry << endl;
                    	
                    	delete ptry;
                    	delete ptrx;
                    
                    	return 0;
                    
                    }
                    
## 53 - Dynamic array > new and delete

                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    int main() {
                    
                    	int num;
                    	cout << "Enter grades of student \n";
                    	cin >> num;
                    	
                    	float *ptr = new float[num]; 
                        
                    	for (int i = 0; i < num; i++) {
                    		cout << "student" << i + 1 << endl;
                    		cin >> *(ptr + i);
                    	}
                    
                    	cout << "\n Displaying grades of students " << endl;
                    
                    	for (int i = 0; i < num; i++) {
                    		cout << "student" << i + 1 << endl<<*(ptr + i) << endl;
                    	}
                    
                    	delete[] ptr;
                    
                    	return 0;
                    
                    }
                              
## 54 - access element in vector

                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    int main() {
                    
                    	vector <int> num{ 1,2,3,45 };
                    	
                    	cout << num.at(0) << endl;
                    	cout << num.at(1) << endl;
                    
                    	cout << num[0] << endl;
                    	cout << num[1] << endl;
                    
                    	return 0;
                    }

## 55 - change element in vector
                    
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    int main() {
                    
                    	vector <int> num{ 1,2,3,45 ,5 };
                    
                    	cout << "values : \n";
                    	for (const int& i : num) {
                    		cout << i << " ";
                    	}
                    
                    	cout << "\nup date values : \n";
                    	for (int& i : num) {
                    		i = 20;
                    		cout << i << " ";
                    	}
                    	cout << "\nup date values : \n";
                    
                    	num[1] = 40;
                    	num.at(2) = 50;
                    	num.at(4) = 60;
                    
                    	for (const int& i : num) {
                    		cout << i << " ";
                    	}
                    	return 0;
                    }
## 56 - vector iterations

                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    int main() {
                    
                    	vector <int> num{ 1,2,3,45,56,5 };
                    
                    	vector <int>::iterator iter;
                    
                    	for (iter = num.begin(); iter != num.end(); iter++) {
                    		cout << *iter << " ";
                    	}
                    
                    	return 0;
                    }
                    
## 57 - string object 

                    
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    int main() {
                       
                        string s1 = "Mustafa saad mohammed mohammed elgabear";
                    
                        cout << s1.length()<< endl;
                    
                        cout << s1.at(5) << endl;
                    
                        s1.append("@ali mohammed");
                        cout << s1 << endl;
                    
                        s1.insert(7, "ali");
                        cout << s1 << endl;
                    
                        cout << s1.substr(12, 3) << endl;
                        
                        s1.push_back('x');
                        cout << s1 << endl;
                    
                        s1.pop_back();
                        cout << s1 << endl;
                    
                        cout << s1.find("Ali") << endl;
                    
                        if (s1.find("ali") == s1.npos) {
                            cout << "not found"<<endl;
                        }
                    
                    
                        s1.clear();
                        return 0;
                    }

## 58 - cctype function


                    #include <iostream>
                    #include <vector>
                    #include <cctype>
                    using namespace std;
                    
                    int main() {
                        
                        char x, w;
                    
                        x = toupper('a');
                        w = tolower('A');
                    
                        cout << "is upper : " << x << endl;
                        cout << "is lower : " << w << endl;
                    
                        cout << islower('a') << endl;
                        cout << isupper('A') << endl;
                    
                        cout << isdigit('9') << endl;
                        cout << ispunct(';') << endl;
                        
                    
                        return 0;
                    }
                    
##  59 - write mod wirte data to file

                    #include<iostream>
                    #include<fstream>
                    using namespace std;
                    int main() {
                    	fstream MyFile;
                    	MyFile.open("MyFile.txt", ios::out);//Write Mode
                    	if (MyFile.is_open())  
                    	{
                    		MyFile << "Mustafa\n";
                    		MyFile << "Hi, this is the second line\n";
                    		MyFile << "Hi, this is the third line\n";
                    		MyFile << "Hi, this is the third line\n";
                    		MyFile.close();
                    	}
                    	return 0;
                    }
  ## 60 - Read data from the file 

  
                    #include <iostream>
                    #include <fstream> 
                    #include <string>
                    using namespace std;
                    
                    void PrintFileContent(string FileName) {
                    	fstream Myfile;
                    
                    	Myfile.open(FileName, ios::in); // read mode 
                    
                    	if (Myfile.is_open()) {
                    
                    		string Line;
                    
                    		while (getline(Myfile, Line)) {
                    			cout << Line << endl;
                    		}
                    		Myfile.close();
                    	}
                    }
                    int main()
                    {
                    	PrintFileContent("file.txt");
                    	return 0;
                    }

## 61 - load data from file to vector 


                    #include <iostream>
                    #include <fstream> 
                    #include <string>
                    #include <vector>
                    using namespace std;
                    
                    void LoadDataFileToVector(string FileName, vector <string> & vFileContent) {
                    
                    	fstream Myfile;
                    	Myfile.open(FileName, ios::in); // read mode
                    	
                    	if (Myfile.is_open()) {
                    		string Line;
                    
                    		while (getline(Myfile, Line)) {
                    			vFileContent.push_back(Line);
                    		}
                    		Myfile.close();
                    	}
                    }
                    int main()
                    {
                    	vector <string> vFileContenet;
                    
                    	LoadDataFileToVector("Myfile.txt", vFileContenet);
                    
                    	for (string Line: vFileContenet) {
                    		cout << Line << endl;
                    	}
                    	
                    	return 0;
                    }

## 62 - save data from vector in file 

                    #include <iostream>
                    #include <fstream> 
                    #include <string>
                    #include <vector>
                    using namespace std;
                    
                    void SaveVectorToFile(string FileName, vector <string> & vFileContent) {
                    
                    	fstream Myfile;
                    	Myfile.open(FileName, ios::out); // read mode
                    	
                    	if (Myfile.is_open()) {
                    		
                    
                    		for (string &Line : vFileContent) {
                    			if (Line != "") {
                    				Myfile << Line << endl;
                    			}
                    		}
                    		Myfile.close();
                    	}
                    }
                    int main()
                    {
                    	vector <string> vFileContenet{ "ali" , "Shadi","Maher" , "Fadi" , "Lama" };
                    
                    	SaveVectorToFile("Myfile.txt", vFileContenet);
                    	
                    	return 0;
                    }
                    
## 63 - append values in file:-

                    #include <iostream>
                    #include <fstream> 
                    using namespace std;
                    int main() {
                    	fstream Myfile;
                    
                    	Myfile.open("file.txt", ios::app | ios::out);
                    
                    	if (Myfile.is_open()) {
                    		Myfile << "Hello World\n";
                    		Myfile << "Hello World\n";
                    		Myfile << "Hello World\n";
                    
                    		Myfile.close();
                    	}
                    	return 0;
                    }

## 64 - print values from file:-

                    #include <iostream>
                    #include <string>
                    #include <vector>
                    #include <fstream> 
                    using namespace std;
                    
                    void print(string FileName) {
                    	fstream MyFile;
                    
                    	MyFile.open(FileName, ios::in);
                    	string line;
                    
                    	if (MyFile.is_open()) {
                    
                    		while (getline(MyFile, line)) {
                    
                    			cout << line << endl;
                    		}
                    		MyFile.close();
                    	}
                    }
                    
                    int main() {
                    	print("file.txt");
                    	return 0;
                    }

## 65 - load data from the file and print it in vector:-

                    #include <iostream>
                    #include <string>
                    #include <vector>
                    #include <fstream> 
                    using namespace std;
                    
                    void loadDataFromFileToVector(string FileName, vector <string>& VfileData) {
                    
                    	fstream MyFile;
                    	MyFile.open(FileName, ios::in);
                    
                    	if (MyFile.is_open()) {
                    		string line;
                    
                    		while (getline(MyFile, line)) {
                    			VfileData.push_back(line);
                    		}
                    		MyFile.close();
                    	}
                    }
                    
                    int main() {
                    	vector <string> VfileData;
                    
                    	loadDataFromFileToVector("file.txt", VfileData);
                    
                    	for (string sLine : VfileData) {
                    		cout << sLine << endl;
                    	}
                    	return 0;
                    }
## 66 - save vector data to file:-

                    #include <iostream>
                    #include <string>
                    #include <vector>
                    #include <fstream> 
                    using namespace std;
                    
                    void SaveVectorDataToFile(string FileName ,vector <string>& VfileData) {
                    
                    	fstream MyFile;
                    	MyFile.open("file.txt", ios::out);
                    
                    	if (MyFile.is_open()) {
                    		string line;
                    
                    		for (string& line : VfileData) {
                    			MyFile << line << endl;
                    		}
                    		MyFile.close();
                    	}
                    }
                    
                    int main() {
                    
                    	vector <string> VfileData{ "Mustafa", "Saad", "Mohammed"};
                    	SaveVectorDataToFile("file.txt", VfileData);
                    
                    	return 0;
                    }

## 67 - program to delete the value from the file and save the file:-


                              #include <iostream>
                              #include <string>
                              #include <vector>
                              #include <fstream> 
                              using namespace std;
                              
                              void loadDataFromFileToVector(string FileName, vector <string>& VfileData) {
                              
                              	fstream MyFile;
                              	MyFile.open("file.txt", ios::in);
                              
                              	if (MyFile.is_open()) {
                              		string line;
                              
                              		while (getline(MyFile, line)) {
                              			VfileData.push_back(line);
                              		}
                              		MyFile.close();
                              	}
                              }
                              void SaveVectorDataToFile(string FileName, vector <string>& VfileData) {
                              
                              	fstream MyFile;
                              	MyFile.open("file.txt", ios::out);
                              
                              	if (MyFile.is_open()) {
                              
                              		for (string& line : VfileData) {
                              			MyFile << line << endl;
                              		}
                              		MyFile.close();
                              	}
                              }
                              void DeleteRecordFromFile(string FileNmae, string Record) {
                              
                              
                              	vector <string> VfileData;
                              
                              	loadDataFromFileToVector(FileNmae, VfileData);
                              
                              	for (string& line : VfileData) {
                              		if (line == Record) {
                              			line = " ";
                              		}
                              	}
                              	SaveVectorDataToFile(FileNmae, VfileData);
                              }
                              
                              void PrintContent(string FileName) {
                              
                              	fstream MyFile;
                              	MyFile.open(FileName, ios::in);
                              
                              	if (MyFile.is_open()) {
                              		string line;
                              		while (getline(MyFile , line)) {
                              			cout << line << endl;
                              		}
                              		MyFile.close();
                              	}
                              
                              }
                              
                              int main() {
                              
                              
                              	cout << "file content before delete. \n";
                              	PrintContent("file.txt");
                              
                              	DeleteRecordFromFile("file.txt", "Mustafa");
                              
                              	cout << "\n\n file content After Delete.\n";
                              	PrintContent("file.txt");
                              
                              	return 0;
                              }
## 68 - Update data in the file:-

                    #include <iostream>
                    #include <string>
                    #include <vector>
                    #include <fstream> 
                    using namespace std;
                    
                    void loadDataFromFileToVector(string FileName, vector <string>& VfileData) {
                    
                    	fstream MyFile;
                    	MyFile.open("file.txt", ios::in);
                    
                    	if (MyFile.is_open()) {
                    		string line;
                    
                    		while (getline(MyFile, line)) {
                    			VfileData.push_back(line);
                    		}
                    		MyFile.close();
                    	}
                    }
                    void SaveVectorDataToFile(string FileName, vector <string>& VfileData) {
                    
                    	fstream MyFile;
                    	MyFile.open("file.txt", ios::out);
                    
                    	if (MyFile.is_open()) {
                    
                    		for (string& line : VfileData) {
                    			MyFile << line << endl;
                    		}
                    		MyFile.close();
                    	}
                    }
                    void UpdateRecordInFile(string FileNmae, string Record , string updateTo) {
                    
                    
                    	vector <string> VfileData;
                    
                    	loadDataFromFileToVector(FileNmae, VfileData);
                    
                    	for (string& line : VfileData) {
                    		if (line == Record) {
                    			line = updateTo;
                    		}
                    	}
                    	SaveVectorDataToFile(FileNmae, VfileData);
                    }
                    
                    void PrintContent(string FileName) {
                    
                    	fstream MyFile;
                    	MyFile.open(FileName, ios::in);
                    
                    	if (MyFile.is_open()) {
                    		string line;
                    		while (getline(MyFile , line)) {
                    			cout << line << endl;
                    		}
                    		MyFile.close();
                    	}
                    
                    }
                    
                    int main() {
                    
                    
                    	cout << "file content before delete. \n";
                    	PrintContent("file.txt");
                    
                    	UpdateRecordInFile("file.txt", "Mustafa" , "Ali");
                    
                    	cout << "\n\n file content After Delete.\n";
                    	PrintContent("file.txt");
                    
                    	return 0;
                    }




# Problem Solving Level3

## 1 - Write a program to fill a 3*3 matrix with random numbers.


            #include <ctime>
            #include <iostream>
            #include <string>
            #include <cstdlib> // For rand and srand
            #include <ctime>   // For time function
            using namespace std;
            
            int RandomNumber(int from, int to) {
            	int RandNum = rand() % (to - from + 1) + from;
            	return RandNum;
            }
            void FillMetrix(int x[][3], int from, int to) {
            
            	for (int i = 0; i < 3; i++) {
            		for (int j = 0; j < 3; j++) {
            			x[i][j] = RandomNumber(from, to);
            		}
            	}
            }
            void PrintMetrix(int x[][3]) {
            
            	for (int i = 0; i < 3; i++) {
            		for (int j = 0; j < 3; j++) {
            			cout << x[i][j] << "    ";
            		}
            		cout << endl;
            	}
            }
            int main() {
            	int x[3][3];
            
            	srand((unsigned)time(NULL));
            
            	FillMetrix(x, 1, 100);
            
            
            	PrintMetrix(x);
            
            	return 0;
            
            }

## 2 - Write a program to fill a 3*3 matrix with random numbers, then print each row sum:--

        #include <ctime>
        #include <iostream>
        #include <string>
        #include <cstdlib> // For rand and srand
        #include <ctime>   // For time function
        using namespace std;
        
        int RandomNumber(int from, int to) {
        	int RandNum = rand() % (to - from + 1) + from;
        	return RandNum;
        }
        void FillMetrix(int x[][3]) {
        
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			x[i][j] = RandomNumber(1, 100);
        		}
        	}
        }
        void CalcRows(int x[][3]) {
        
        	int counter = 0;
        
        	cout << "Result of Rows Sum :" << endl;
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			counter += x[i][j];
        		}
        		cout << "Row(" << i << ") : " << counter << endl;
        		counter = 0;
        	}
        }
        void PrintMetrix(int x[][3]) {
        
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			cout << x[i][j] << "    ";
        		}
        		cout << endl;
        	}
        }
        int main() {
        	int x[3][3];
        
        	srand((unsigned)time(NULL));
        
        	FillMetrix(x);
        	PrintMetrix(x);
        
        	CalcRows(x);
        
        	return 0;
        
        }
## 3 - another solution:-

        #include <ctime>
        #include <iostream>
        #include <string>
        #include <cstdlib> // For rand and srand
        #include <ctime>   // For time function
        using namespace std;
        
        int RandomNumber(int from, int to) {
        	int RandNum = rand() % (to - from + 1) + from;
        	return RandNum;
        }
        void FillMetrix(int x[][3]) {
        
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			x[i][j] = RandomNumber(1, 100);
        		}
        	}
        }
        int CalcRows(int x[][3]) {
        
        	int counter = 0;
        
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			counter += x[i][j];
        		}
        		return counter;
        	}
        }
        void PrintMetrix(int x[][3]) {
        
        	for (int i = 0; i < 3; i++) {
        		for (int j = 0; j < 3; j++) {
        			cout << x[i][j] << "    ";
        		}
        		cout << endl;
        	}
        }
        void PrintEachRow(int x[][3] ) {
        	cout << " \n Result of Rows Sum :\n" << endl;
        	for (int i = 0; i < 3; i++) {
        		cout << "Row(" << i+1 << ") sum : " << CalcRows(x)<< endl;
        	}
        }
        int main() {
        	int x[3][3];
        
        	srand((unsigned)time(NULL));
        
        	FillMetrix(x);
        	PrintMetrix(x);
        
        	CalcRows(x);
        	PrintEachRow(x);
        	return 0;
        
        }

## 4 -Write a program to fill a 3*3 matrix with random numbers, then sum each row in a separate array and print the result:-


          #include <ctime>
          #include <iostream>
          #include <string>
          #include <cstdlib> // For rand and srand
          #include <ctime>   // For time function
          using namespace std;
          
          int RandomNumber(int from, int to) {
          	int RandNum = rand() % (to - from + 1) + from;
          	return RandNum;
          }
          void FillMetrix(int x[][3]) {
          
          	for (int i = 0; i < 3; i++) {
          		for (int j = 0; j < 3; j++) {
          			x[i][j] = RandomNumber(1, 100);
          		}
          	}
          }
          int CalcRows(int x[][3], int arr[]) {
          
          	for (int i = 0; i < 3; i++) {
          		  arr[i] = 0; // Initialize the sum for each row
          		for (int j = 0; j < 3; j++) {
          			arr[i] += x[i][j];
          		}
          	}
          }
          void PrintMetrix(int x[][3]) {
          
          	for (int i = 0; i < 3; i++) {
          		for (int j = 0; j < 3; j++) {
          			cout << x[i][j] << "    ";
          		}
          		cout << endl;
          	}
          }
          void PrintEachRow(int arr[]) {
          	cout << " \n Result of Rows Sum :\n" << endl;
          	for (int i = 0; i < 3; i++) {
          		cout << "Row" << i + 1 << " sum : " << arr[i] << endl;
          	}
          }
          int main() {
          	int x[3][3];
          	int arr[3];
          	srand((unsigned)time(NULL));
          
          	FillMetrix(x);
          	PrintMetrix(x);
          
          	CalcRows(x, arr);
          	PrintEachRow(arr);
          
          	return 0;
          
          }

## 5 - Write a program to fill a 3*3 matrix with random numbers, then sum each col in another array and print them:-


      #include <ctime>
      #include <iostream>
      #include <string>
      #include <cstdlib> // For rand and srand
      #include <ctime>   // For time function
      using namespace std;
      
      int RandomNumber(int from, int to) {
      	int RandNum = rand() % (to - from + 1) + from;
      	return RandNum;
      }
      void FillMetrix(int arr[3][3] , short Rows , short Cols) {
      
      	for (short i = 0; i < Rows; i++) {
      		for (short j = 0; j < Cols; j++) {
      			arr[i][j] = RandomNumber(1, 100);
      		}
      	}
      }
      void PrintMetrix(int arr[3][3] , short Rows , short Cols) {
      
      	for (short i = 0; i < Rows; i++) {
      		for (short j = 0; j < Cols; j++) {
      			cout << arr[i][j] << "    ";
      		}
      		cout << endl;
      	}
      }
      int ColSum(int arr[3][3], short Rows , short colNum) {
      
      	int sum = 0;
      	for (int i = 0; i < Rows - 1; i++)
      	{
      		sum += arr[i][colNum];
      	}
      	return sum;
      }
      void SumMaterix(int arr[3][3] ,int arr2[] , short Rows, short Cols ) {
      	for (short x = 0; x < Cols; x++)
      	{
      		arr2[x] = ColSum(arr, Rows, x);
      	}
      }
      void PrintEachColSum( int arr2[3] , short Length ) {
      	cout << " \n Result of Rows Sum :\n" << endl;
      	for (short j = 0; j < Length; j++) {
      		cout << "Row" << j + 1 << " sum : " << arr2[j] << endl;
      	}
      }
      int main() {
      
      	srand((unsigned)time(NULL));
      
      	int arr[3][3];
      	int arr2[3];
      
      
      	FillMetrix(arr ,3,3);
      	PrintMetrix(arr,3,3);
      
      	SumMaterix(arr, arr2,3,3);
      	PrintEachColSum(arr2,3);
      
      	return 0;
      
      }


## 6 - Write a program to fill a 3*3 matrix with ordered numbers.
            
            #include <iostream>
            #include <string>
            using namespace std;
            
            void FillMatrix(int arr[3][3], short Rows, short Cols) {
            
                short counter = 0;
                for (short i = 0; i < Rows; i++) {
                    for (short j = 0; j < Cols; j++) {
                        counter++;
                        arr[i][j] = counter; // Increment num after assigning it
                    }
                }
            }
            
            void PrshortMatrix(int arr[3][3], short Rows, short Cols) {
                for (short i = 0; i < Rows; i++) {
                    for (short j = 0; j < Cols; j++) {
                        cout << arr[i][j] << " ";
                    }
                    cout << endl;
                }
            }
            
            int main() {
                int arr[3][3];
            
                FillMatrix(arr, 3, 3);
                PrshortMatrix(arr, 3, 3);
            
                return 0;
            }

## 7 - Write a program to fill a 3*3 matrix with ordered numbers and print it, then transpose the matrix and print it.


            #include <iostream>
            #include <string>
            using namespace std;
            
            void FillMatrix(int arr[3][3], short Rows, short Cols) {
                int counter = 1; // Start from 1 instead of 0
                for (short i = 0; i < Rows; i++) {
                    for (short j = 0; j < Cols; j++) {
                        arr[i][j] = counter++; // Increment counter after assigning it
                    }
                }
            }
            
            void PrintMatrix(int arr[3][3], short Rows, short Cols) {
                cout << "The real matrix:" << endl;
                for (short i = 0; i < Rows; i++) {
                    for (short j = 0; j < Cols; j++) {
                        cout << arr[i][j] << " ";
                    }
                    cout << endl;
                }
            }
            
            void TransposeMatrix(int arr2[3][3], int arr[3][3], short Rows, short Cols) {
                for (int i = 0; i < Rows; i++) {
                    for (int j = 0; j < Cols; j++) {
                        arr2[j][i] = arr[i][j];
                    }
                }
            }
            
            void PrintTransposeMatrix(int arr2[3][3], short Rows, short Cols) {
                cout << "The transpose matrix:" << endl;
                for (short i = 0; i < Rows; i++) {
                    for (short j = 0; j < Cols; j++) {
                        cout << arr2[i][j] << " ";
                    }
                    cout << endl;
                }
            }
            int main() {
                int arr[3][3], arr2[3][3];
            
                FillMatrix(arr, 3, 3);
                PrintMatrix(arr, 3, 3);
            
                TransposeMatrix(arr2, arr, 3, 3);
                PrintTransposeMatrix(arr2, 3, 3);
            
                return 0;
            }
## 8 - Write a program to fill two 3*3 matrices with random numbers and them, then multiply them into a 3rd matrix and print it.


          #include <iostream>
          #include <string>
          #include <ctime>  // for time function
          #include <cstdlib> // for rand and srand
          
          using namespace std;
          
          int RandomNumber(int from, int to) {
          	int RandNumber = rand() % (to - from + 1) + from;
          	return RandNumber;
          }
          void FillMatrix1(int arr[3][3], short Rows, short Cols) {
          
          	for (short i = 0; i < Rows; i++) {
          		for (short j = 0; j < Cols; j++) {
          			arr[i][j] = RandomNumber(1, 10);
          		}
          		cout << endl;
          	}
          }
          void PrintlMatrix1(int arr[3][3], short Rows, short Cols)
          {
          	cout << "Matrix 1 values \n " << endl;
          	for (short i = 0; i < Rows; i++) {
          		for (short j = 0; j < Cols; j++) {
          			cout << arr[i][j] << " ";
          		}
          		cout << "\n";
          	}
          }
          void FillMatrix2(int arr2[3][3], short Rows, short Cols) {
          
          	for (short i = 0; i < Rows; i++) {
          		for (short j = 0; j < Cols; j++) {
          			arr2[i][j] = RandomNumber(1, 10);
          		}
          		cout << endl;
          	}
          }
          void PrintlMatrix2(int arr2[3][3], short Rows, short Cols)
          {
          	cout << "Matrix 2 values \n " << endl;
          	for (short i = 0; i < Rows; i++) {
          		for (short j = 0; j < Cols; j++) {
          			cout << arr2[i][j] << " ";
          		}
          		cout << "\n";
          	}
          }
          void MultipleMatrix(int arr[3][3], int arr2[3][3], int arr3[3][3], short Rows, short Cols) {
          
          	for (short i = 0; i < Rows; i++) {
          		for (short j = 0; j < Cols; j++) {
          			arr3[i][j] = arr[i][j] * arr2[i][j];
          		}
          	}
          }
          void PrintMatrix(int arr[3][3], int arr2[3][3], int arr3[3][3], short Rows, short Cols) {
          
          	cout << "Multipe_Matrix values :  " << endl;
          	for (short i = 0; i < Rows; i++) {
          		for (short j = 0; j < Cols; j++) {
          			cout << arr3[i][j] << " ";
          		}
          		cout << endl;
          	}
          }
          int main() {
          
          	srand((unsigned)time(NULL));
          
          	int arr[3][3], arr2[3][3], arr3[3][3];
          
          	FillMatrix1(arr, 3, 3);
          	FillMatrix2(arr2, 3, 3);
          
          	MultipleMatrix(arr, arr2, arr3, 3, 3);
          
          	PrintlMatrix1(arr, 3, 3);
          	PrintlMatrix2(arr2, 3, 3);
          
          	PrintMatrix(arr, arr2, arr3, 3, 3);
          
          	return 0;
          }
          
## 9 - Write a program to fill a 3*3 matrix with random numbers, print it, then print the middle row and middle col.

                    #include <iostream>
                    #include <string>
                    #include <ctime>  // for time function
                    #include <cstdlib> // for rand and srand
                    
                    using namespace std;
                    
                    int RandomNumber(int from, int to) {
                    	int RandNumber = rand() % (to - from + 1) + from;
                    	return RandNumber;
                    }
                    void FillMatrix1(int arr[3][3], short Rows, short Cols) {
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			arr[i][j] = RandomNumber(1, 10);
                    		}
                    		cout << endl;
                    	}
                    }
                    void PrintMatrix1(int arr[3][3], short Rows, short Cols) {
                    	FillMatrix1(arr, Rows, Cols);
                    
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			cout << arr[i][j] << " ";
                    		}
                    		cout << endl;
                    	}
                    	cout << endl;
                    }
                    
                    void PrintFillMiddleRow(int arr[3][3], short Rows, short Cols) {
                    
                    	short MiddleRow = Rows / 2;
                    
                    	cout << " Middle Cols: ";
                    	for (short i = 0; i < Rows; i++) {
                    		printf("  %0*d  ", 2, arr[MiddleRow][i]);
                    	}
                    		cout << "\n";
                    }
                    
                    void PrintFillMiddleCols(int arr[3][3], short Rows, short Cols) {
                    	short MiddleCol = Cols / 2;
                    
                    	cout << " Middle Cols: ";
                    	for (short j = 0; j < Cols; j++) {
                    		printf("  %0*d  ", 2, arr[j][MiddleCol]);
                    	}
                    		cout << "\n";
                    }
                    int main() {
                    
                    	srand((unsigned)time(NULL));
                    
                    	int arr[3][3];
                    
                    	PrintMatrix1(arr, 3, 3);
                    
                    	PrintFillMiddleRow(arr, 3, 3);
                    
                    	PrintFillMiddleCols(arr, 3, 3);
                    
                    	return 0;
                    }



## 10 -  Write a program to fill two 3*3 matrices with random numbers and them, then write a function to sum all numbers in this matrix and print it.

                    #include <iostream>
                    #include <string>
                    #include <ctime>  // for time function
                    #include <cstdlib> // for rand and srand
                    
                    using namespace std;
                    
                    int RandomNumber(int from, int to) {
                    	int RandNumber = rand() % (to - from + 1) + from;
                    	return RandNumber;
                    }
                    void FillMatrix1(int arr[3][3], short Rows, short Cols) {
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			arr[i][j] = RandomNumber(1, 10);
                    		}
                    		cout << endl;
                    	}
                    }
                    void PrintMatrix1(int arr[3][3], short Rows, short Cols) {
                    	FillMatrix1(arr, Rows, Cols);
                    
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			cout << arr[i][j] << " ";
                    		}
                    		cout << endl;
                    	}
                    	cout << endl;
                    }
                    int  CaclNumbersOfMatrix(int arr[3][3], short Rows, short Cols){
                    
                    	int sum = 0;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			sum +=  arr[i][j];
                    		}
                    	}
                    	return sum;
                    }
                    int main() {
                    
                    	srand((unsigned)time(NULL));
                    
                    	int arr[3][3]  ;
                    
                    	PrintMatrix1(arr, 3, 3);
                    
                    	CaclNumbersOfMatrix(arr, 3, 3);
                    
                    	cout << "sum fo matrix1 is :  " << CaclNumbersOfMatrix(arr,3,3) << endl;
                    
                    
                    	return 0;
                    }


                    
## 11 - Write a program to compare two matrices and check if they are equal or not.

                    #include <iostream>
                    #include <string>
                    #include <ctime>  // for time function
                    #include <cstdlib> // for rand and srand
                    
                    using namespace std;
                    
                    int RandomNumber(int from, int to) {
                    	int RandNumber = rand() % (to - from + 1) + from;
                    	return RandNumber;
                    }
                    void FillMatrix1(int arr[3][3], short Rows, short Cols) {
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			arr[i][j] = RandomNumber(1, 10);
                    		}
                    		cout << endl;
                    	}
                    }
                    void PrintMatrix1(int arr[3][3], short Rows, short Cols) {
                    	FillMatrix1(arr, Rows, Cols);
                    
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			cout << arr[i][j] << " ";
                    		}
                    		cout << endl;
                    	}
                    }
                    void FillMatrix2(int arr2[3][3], short Rows, short Cols) {
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			arr2[i][j] = RandomNumber(1, 10);
                    		}
                    		cout << endl;
                    	}
                    }
                    void PrintMatrix2(int arr2[3][3], short Rows, short Cols) {
                    	FillMatrix2(arr2, Rows, Cols);
                    
                    	cout << "Matrix 2 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			cout << arr2[i][j] << " ";
                    		}
                    		cout << endl;
                    	}
                    }
                    int  CaclNumbersOfMatrix1(int arr[3][3], short Rows, short Cols){
                    
                    	int sum = 0;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			sum +=  arr[i][j];
                    		}
                    	}
                    	return sum;
                    }
                    int  CaclNumbersOfMatrix2(int arr2[3][3], short Rows, short Cols) {
                    
                    	int sum2 = 0;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			sum2 += arr2[i][j];
                    		}
                    	}
                    	return sum2;
                    }
                    void CompareMatrixs(int arr[3][3], int arr2[3][3], short Rows, short Cols) {
                    	
                    	int sum = CaclNumbersOfMatrix1(arr, Rows, Cols);
                    	int sum2 = CaclNumbersOfMatrix2(arr2, Rows, Cols);
                    
                    	if (sum == sum2) 
                    		cout << sum <<" = " << sum2<< "\n matrices are equal" << endl;
                    	else 
                    		cout << sum << " != " << sum2 << "\n matrices not are equal" << endl;
                    
                    }
                    int main() {
                    
                    	srand((unsigned)time(NULL));
                    
                    	int arr[3][3] , arr2[3][3];
                    
                    	PrintMatrix1(arr, 3, 3);
                    
                    	PrintMatrix2(arr2, 3, 3);
                    
                    	CompareMatrixs(arr, arr2, 3, 3);
                    
                    	return 0;
                    }

## 12 - anoter soluthion .

                    #include <iostream>
                    #include <string>
                    #include <ctime>  // for time function
                    #include <cstdlib> // for rand and srand
                    
                    using namespace std;
                    
                    int RandomNumber(int from, int to) {
                    	int RandNumber = rand() % (to - from + 1) + from;
                    	return RandNumber;
                    }
                    void FillMatrix1(int Matrix1[3][3], short Rows, short Cols) {
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			Matrix1[i][j] = RandomNumber(1, 10);
                    		}
                    		cout << endl;
                    	}
                    }
                    void PrintMatrix1(int Matrix1[3][3], short Rows, short Cols) {
                    	FillMatrix1(Matrix1, Rows, Cols);
                    
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			cout << Matrix1[i][j] << " ";
                    		}
                    		cout << endl;
                    	}
                    }
                    void FillMatrix2(int Matrix2[3][3], short Rows, short Cols) {
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			Matrix2[i][j] = RandomNumber(1, 10);
                    		}
                    		cout << endl;
                    	}
                    }
                    void PrintMatrix2(int Matrix2[3][3], short Rows, short Cols) {
                    	FillMatrix2(Matrix2, Rows, Cols);
                    
                    	cout << "Matrix 2 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			cout << Matrix2[i][j] << " ";
                    		}
                    		cout << endl;
                    	}
                    }
                    
                    int  SumOfMatrix(int Matrix1[3][3], short Rows, short Cols) {
                    
                    	int sum = 0;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			sum += Matrix1[i][j];
                    		}
                    	}
                    	return sum;
                    }
                    bool AreEqual(int Matrix1[3][3], int Matrix2[3][3] , short Rows, short Cols) {
                    	return (SumOfMatrix(Matrix1,Rows, Cols) == SumOfMatrix(Matrix2, Rows, Cols));
                    }
                    int main() {
                    
                    	srand((unsigned)time(NULL));
                    
                    	int Matrix1[3][3] , Matrix2[3][3];
                    
                    	PrintMatrix1(Matrix1, 3, 3);
                    
                    	PrintMatrix2(Matrix2, 3, 3);
                    
                    	if(AreEqual(Matrix1, Matrix2, 3, 3))
                    		cout << "The sum of the elements of the two matrices is equal" << endl;
                    	else
                    		cout << "The sum of the elements of the two matrices is not equal" << endl;
                    
                    	return 0;
                    }
                    
## 13 - Write a program to compare two matrices and check if they are typical or not.

                    #include <iostream>
                    #include <string>
                    #include <ctime>  // for time function
                    #include <cstdlib> // for rand and srand
                    
                    using namespace std;
                    
                    int RandomNumber(int from, int to) {
                    	int RandNumber = rand() % (to - from + 1) + from;
                    	return RandNumber;
                    }
                    void FillMatrix1(int Matrix1[3][3], short Rows, short Cols) {
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			Matrix1[i][j] = RandomNumber(1, 2);
                    		}
                    		cout << endl;
                    	}
                    }
                    void PrintMatrix1(int Matrix1[3][3], short Rows, short Cols) {
                    	FillMatrix1(Matrix1, Rows, Cols);
                    
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			printf(" %0*d ", 2, Matrix1[i][j]);
                    		}
                    		cout << endl;
                    	}
                    }
                    void FillMatrix2(int Matrix2[3][3], short Rows, short Cols) {
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			Matrix2[i][j] = RandomNumber(1, 2);
                    		}
                    		cout << endl;
                    	}
                    }
                    void PrintMatrix2(int Matrix2[3][3], short Rows, short Cols) {
                    	FillMatrix2(Matrix2, Rows, Cols);
                    
                    	cout << "Matrix 2 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			printf(" %0*d ", 2, Matrix2[i][j]);
                    		}
                    		cout << endl;
                    	}
                    }
                    bool CheckTypical(int Matrix1[3][3], int Matrix2[3][3], short Rows, short Cols) {
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			if (Matrix1[i][j] != Matrix2[i][j]) {
                    				return false;
                    			}
                    		}
                    		cout << endl;
                    	}
                    }
                    int main() {
                    
                    	srand((unsigned)time(NULL));
                    
                    	int Matrix1[3][3], Matrix2[3][3];
                    
                    	PrintMatrix1(Matrix1, 3, 3);
                    
                    	PrintMatrix2(Matrix2, 3, 3);
                    
                    	if (CheckTypical(Matrix1, Matrix2, 3, 3))
                    	    cout << "Matrix 1 and Matrix 2 are typical" << endl;
                    	else
                    		cout << "Matrix 1 and Matrix 2 are not typical" << endl;
                    	return 0;
                    }

## 14 - Write a program to check if the matrix is identity or not.

                    #include <iostream>
                    #include <string>
                    
                    
                    using namespace std;
                    
                    
                    void PrintMatrix1(int Matrix1[3][3], short Rows, short Cols) {
                    
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			printf(" %0*d ", 2, Matrix1[i][j]);
                    		}
                    		cout << endl;
                    	}
                    }
                    bool CheckIdentityMatrix(int Matrix1[3][3], short Rows, short Cols) {
                    	
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			if(i == j && Matrix1[i][j] != 1 )
                    				return false;
                    			else if (i != j && Matrix1[i][j] != 0)
                    				return false;
                    		}
                    		cout << endl;
                    	}
                    	return true;
                    }	
                    int main() {
                    
                    	int Matrix1[3][3] = { {1,0,0} ,{0,1,0},{0,0,1} };
                    
                    	PrintMatrix1(Matrix1, 3, 3);
                    
                    	if(CheckIdentityMatrix(Matrix1, 3, 3))
                    		cout << "Matrix is Identity Matrix" << endl;
                    	else
                    		cout << "Matrix is not Identity Matrix" << endl;
                    }

 ## 15 -  Write a program to check if the matrix is scalar or not.

 
                    #include <iostream>
                    #include <string>
                    
                    
                    using namespace std;
                    
                    
                    void PrintMatrix1(int Matrix1[3][3], short Rows, short Cols) {
                    
                    	
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			printf(" %0*d ", 2, Matrix1[i][j]);
                    		}
                    		cout << endl;
                    	}
                    }
                    bool CheckScalarMatrix(int Matrix1[3][3], short Rows, short Cols) {
                    	
                    	int firstDeigit = Matrix1[0][0] ;
                    	
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			if(i == j && Matrix1[i][j] != firstDeigit)
                    				return false;
                    			else if (i != j && Matrix1[i][j] != 0)
                    				return false;
                    		}
                    		cout << endl;
                    	}
                    	return true;
                    }
                    int main() {
                    
                    	int Matrix1[3][3] = { {4,0,0} ,{0,4,0},{0,0,4} };
                    
                    	PrintMatrix1(Matrix1, 3, 3);
                    
                    	if(CheckScalarMatrix(Matrix1, 3, 3))
                    		cout << "Matrix is Scalar Matrix" << endl;
                    	else
                    		cout << "Matrix is not Scalar Matrix" << endl;
                    }

## 16 - Write a program to count given number in matrix:-


                    #include <iostream>
                    #include <string>
                    
                    
                    using namespace std;
                    
                    int ReadNumber(string message) {
                    
                    	int Number;
                    	cout<< message;
                    	cin >> Number;
                    	return Number;
                    }
                    void PrintMatrix1(int Matrix1[3][3], short Rows, short Cols) {
                    
                    	
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			printf(" %0*d ", 2, Matrix1[i][j]);
                    		}
                    		cout << endl;
                    	}
                    }
                    void CheckNumber(int Matrix1[3][3], short Rows, short Cols) {
                    	int Number = ReadNumber("Enter number: ");
                    	int counter = 0;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			if (Number == Matrix1[i][j])
                    				counter++;
                    		}
                    	}
                    	cout << "Number of iteration numbers: " << counter << endl;
                    }
                    int main() {
                    
                    	int Matrix1[3][3] = { {4,0,0} ,{0,4,0},{0,0,4} };
                    
                    	PrintMatrix1(Matrix1, 3, 3);
                    
                    	CheckNumber(Matrix1, 3, 3);
                    
                    	return 0;
                    }


## 17 - Write a program to check if the matrix is Sparce or not.


                    #include <iostream>
                    #include <string>
                    
                    
                    using namespace std;
                    
                    
                    void PrintMatrix1(int Matrix1[3][3], short Rows, short Cols) {
                    
                    
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			printf(" %0*d ", 2, Matrix1[i][j]);
                    		}
                    		cout << endl;
                    	}
                    }
                    short CountNumberInMatrix(int Matrix1[3][3], int Number , short Rows, short Cols) {
                    
                    	int counterZero = 0;
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    
                    			if (Matrix1[i][j] == Number )
                    				counterZero++;
                    		}
                    	}
                    	return counterZero;
                    }
                    bool IsSparseMatrix(int Matrix1[3][3], short Rows, short Cols) {
                    
                    	short MatrixSize = Rows * Cols;
                        
                    	return CountNumberInMatrix(Matrix1, 0, 3, 3) > ceil((float)MatrixSize / 2);
                    }
                    int main() {
                    
                    	int Matrix1[3][3] = { {0,5,0} ,{30,0,0},{0,7,0} };
                    
                    	PrintMatrix1(Matrix1, 3, 3);
                    
                    	if (IsSparseMatrix(Matrix1, 3, 3))
                    		cout << "Yes: It's Sparce" << endl;
                    	else
                    		cout << "No: It's Not Sparce" << endl;
                    	return 0;
                    }


## 18 - Write a program to check if a given number exists im matrix or not.


                    #include <iostream>
                    #include <string>
                    
                    
                    using namespace std;
                    
                    int ReadNumber(string message) {
                    
                    	int number;
                    	cout << message;
                    	cin >> number;
                    	return number;
                    }
                    void PrintMatrix1(int Matrix1[3][3], short Rows, short Cols) {
                    
                    
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			printf(" %0*d ", 2, Matrix1[i][j]);
                    		}
                    		cout << endl;
                    	}
                    }
                    bool CheckNumber(int Matrix1[3][3], short Rows, short Cols) {
                    
                    	int number = ReadNumber("Enter Number to check: ");
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    
                    			if (Matrix1[i][j] == number)
                    				return true;
                    			else
                    				return false;
                    		}
                    	}
                    }
                    
                    int main() {
                    
                    	int Matrix1[3][3] = { {0,5,0} ,{3,0,0},{0,7,0} };
                    
                    	PrintMatrix1(Matrix1, 3, 3);
                    
                    	if (CheckNumber(Matrix1, 3, 3))
                    		cout << "Yes: It's there" << endl;
                    	else
                    		cout << "No: It's Not there" << endl;
                    	return 0;
                    }
## 19 - Write a program to print the intersected Numners in two given matrices.


                    #include <iostream>
                    #include <string>
                    using namespace std;
                    
                    
                    void PrintMatrix1(int Matrix1[3][3], short Rows, short Cols) {
                    
                    
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			printf(" %0*d ", 2, Matrix1[i][j]);
                    		}
                    		cout << endl;
                    	}
                    }
                    void PrintMatrix2(int Matrix2[3][3], short Rows, short Cols) {
                    
                    
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			printf(" %0*d ", 2, Matrix2[i][j]);
                    		}
                    		cout << endl;
                    	}
                    }
                    void  CheckIntersectedNumber(int Matrix1[3][3], int Matrix2[3][3], short Rows, short Cols) {
                    
                    	cout << "the intersected numbers is:";
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    
                    			if (Matrix1[i][j] == Matrix2[i][j])
                    				cout << Matrix1[i][j] << " ";
                    		}
                    	}
                    }
                    
                    int main() {
                    
                    	int Matrix1[3][3] = { {0,5,0} ,{3,23,1},{0,7,4} };
                    	int Matrix2[3][3] = { {4,5,0} ,{3,23,2},{12,7,0} } , Matrix3[3][3] ;
                    
                    	PrintMatrix1(Matrix1, 3, 3);
                    	PrintMatrix2(Matrix2, 3, 3);
                    
                    	CheckIntersectedNumber(Matrix1, Matrix2, 3, 3);
                    
                    
                    }

## 20 - Write a program to print the minimum and maximum numbers in matrix.

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    
                    void PrintMatrix1(int Matrix1[3][3], short Rows, short Cols) {
                    
                    
                    	cout << "Matrix 1 " << endl;
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			printf(" %0*d ", 2, Matrix1[i][j]);
                    		}
                    		cout << endl;
                    	}
                    }
                    void MinNumberInArray(int Matrix1[3][3], short Rows, short Cols) {
                    	
                    	int min = Matrix1[0][0];
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			if(Matrix1[i][j] < min)
                    				min = Matrix1[i][j];	
                    		}
                    	}
                    		cout << "the min Number is:"<< min<< endl;
                    }
                    void MaxNumberInArray(int Matrix1[3][3], short Rows, short Cols) {
                    
                    	int Max = Matrix1[0][0];
                    
                    	for (short i = 0; i < Rows; i++) {
                    		for (short j = 0; j < Cols; j++) {
                    			if (Matrix1[i][j] > Max)
                    				Max = Matrix1[i][j];
                    		}
                    	}
                    		cout << "the min Number is:" << Max << endl;
                    }
                    
                    
                    int main() {
                    
                    	int Matrix1[3][3] = { {235,5,0} ,{3,23,1},{34,7,4} };
                    
                    	PrintMatrix1(Matrix1, 3, 3);
                    
                    	MinNumberInArray(Matrix1, 3, 3);
                    
                    	MaxNumberInArray(Matrix1, 3, 3);
                    
                    
                    
                    }


## 21 - Write a program to check palindrom Matrix.

          #include <iostream>
          #include <string>
          #include <iomanip>
          using namespace std;
          
          
          void PrintMatrix1(int Matrix1[3][3], short Rows, short Cols) {
          
          
          	cout << "Matrix 1 " << endl;
          	for (short i = 0; i < Rows; i++) {
          		for (short j = 0; j < Cols; j++) {
          			printf(" %0*d ", 2, Matrix1[i][j]);
          		}
          		cout << endl;
          	}
          }
          bool IsPalindromMatrix(int Matrix1[3][3], short Rows, short Cols) {
          	for (int i = 0; i < Rows; i++) {
          		for (int j = 0; j < Cols/2; j++) {
          			if (Matrix1[i][j] == Matrix1[i][Cols - 1 - j]) {
          				return true;
          			}
          		}
          	}
          	return false;
          }
          
          int main() {
          
          	int Matrix1[3][3] = { {1,2,1} ,{5,5,5},{7,3,7} };
          
          	PrintMatrix1(Matrix1, 3, 3);
          
          	if(IsPalindromMatrix(Matrix1, 3, 3))
          		cout << "Matrix is palindrom" << endl;
          	else
          		cout << "Matrix is not palindrom" << endl;
          
          }


## 22 - Wriet a program to print Fibonacci Series of 10.

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    void FibonacciSeries() {
                    	
                    	int First = 1;
                    	int Second = 1;
                    	int Next = 0;
                    	for (int i = 2; i < 10; i++) {
                    		
                    		Next  = First + Second;
                    		cout << Next << " ";
                    		First = Second;
                    		Second = Next;
                    	}
                    }
                    
                    
                    int main() {
                    
                    	cout << "Fibonacci Series:" << endl;
                    	FibonacciSeries();
                    
                    	return 0;
                    
                    }

## 23 -  Wriet a program to print Fibonacci Series with Recursion of 10.

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    void FibonacciSeries(short Number, int First, int Second) {
                    
                    	int Next = 0;
                    
                    	if (Number > 0) {
                    
                    		Next = First + Second;
                    		cout << Next << " ";
                    		First = Second;
                    		Second = Next;
                    
                    		FibonacciSeries(Number - 1, First, Second);
                    	}
                    
                    }
                    
                    
                    int main() {
                    
                    	cout << "Fibonacci Series:" << endl;
                    	FibonacciSeries(10, 0, 1);
                    
                    	return 0;
                    
                    }

## 24 - Write a program to read a string then print the first letter of each word in that string.


                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    string ReadString() {
                    
                    	string name;
                    	cout << "Please enter your name: ";
                    	getline(cin, name);
                    
                    	return name;
                    }
                    void PrintFistLetter() {
                    
                    	string name = ReadString();
                    
                    	cout << "first letter is :" << endl;
                    
                    	for (short i = 0; i < name.length(); i++) {
                    
                    		if (i == 0)
                    			cout << name[i] << endl;
                    
                    		else if (name[i] == ' ')
                    			cout << name[i + 1] << endl;
                    	}
                    }
                    
                    
                    int main() {
                    
                    	PrintFistLetter();
                    
                    	system("pause > 0");
                    
                    }


## 25 - another solution 

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    string ReadString() {
                    
                    	string S;
                    	cout << "Please enter your S: ";
                    	getline(cin, S);
                    
                    	return S;
                    }
                    void PrintFistLetter() {
                    
                    	string S = ReadString();
                    	cout << "first letter is :" << endl;
                    
                    	bool isFirstLetter = true;
                    
                    	for (short i = 0; i < S.length(); i++) {
                    		if (S[i] != ' ' && isFirstLetter) {
                    
                    			cout << S[i] << endl;
                    		}
                    		isFirstLetter = (S[i] == ' ' ? true : false);
                    	}
                    }
                    
                    
                    int main() {
                    
                    	PrintFistLetter();
                    
                    	system("pause > 0");
                    
                    }

## 26 - Write a program to read a string then Uppercase the first letter of each word in that string.


                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    string ReadString() {
                    
                    	string S;
                    	cout << "Please enter your S: ";
                    	getline(cin, S);
                    
                    	return S;
                    }
                    string UpperFirstLetterOfEachWord(string s) {
                    
                    
                    	bool IsFirstLetter = true;
                    	for (short i = 0; i < s.length(); i++) {
                    
                    		if (s[i] != ' ' && IsFirstLetter) {
                    			  s[i] = toupper(s[i]);
                    		}
                    		IsFirstLetter = (s[i] == ' ' ?true: false);
                    	}
                    	return s;
                    }
                    
                    
                    int main() {
                    
                    	string s = ReadString();
                    
                    	cout << "\n string after conversion \n";
                    
                    	s = UpperFirstLetterOfEachWord(s);
                    
                    	cout << s << endl;
                    	
                    	system("pause > 0");
                    
                    }

## 27 - Write a program to read a string then lowercase the first letter of each word in that string.

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    string ReadString() {
                    
                    	string S;
                    	cout << "Please enter your S: ";
                    	getline(cin, S);
                    
                    	return S;
                    }
                    string LowerFirstLetterOfEachWord(string s) {
                    
                    
                    	bool IsFirstLetter = true;
                    	for (short i = 0; i < s.length(); i++) {
                    
                    		if (s[i] != ' ' && IsFirstLetter) {
                    			  s[i] = tolower(s[i]);
                    		}
                    		IsFirstLetter = (s[i] == ' ' ?true: false);
                    	}
                    	return s;
                    }
                    
                    
                    int main() {
                    
                    	string s = ReadString();
                    
                    	cout << "\n string after conversion \n";
                    
                    	s = LowerFirstLetterOfEachWord(s);
                    
                    	cout << s << endl;
                    	
                    	system("pause > 0");
                    
                    }

## 28 -  Write a program to read a string then lowercase the all letter of each word in that string.

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    string ReadString() {
                    
                    	string S;
                    	cout << "Please enter your S: ";
                    	getline(cin, S);
                    
                    	return S;
                    }
                    string LowerLetterOfEachWord(string s) {
                    
                    
                    	for (short i = 0; i < s.length(); i++) {
                    		
                    		s[i] = tolower(s[i]);
                    	}
                    	return s;
                    }
                    
                    
                    int main() {
                    
                    	string s = ReadString();
                    
                    	cout << "\n string after conversion \n";
                    
                    	s = LowerLetterOfEachWord(s);
                    
                    	cout << s << endl;
                    	
                    	system("pause > 0");
                    
                    }

## 29 - Write a program to read a character then invert it's case and print it.

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    char ReadChar() {
                    	
                    	char c;
                    	cout << "Enter a character: ";
                    	cin >> c;
                    	return c;
                    }
                    void ConvertingChar() {
                    	char c = ReadChar();
                    
                    	if (c == tolower(c)) {
                    		cout << char(toupper(c)) << endl;
                    	}
                    	else {
                    		cout << char(tolower(c)) << endl;
                    	}
                    	
                    }
                    int main() {
                    
                    	ConvertingChar();
                    
                    	return 0;
                    }

## 30 - another solution.


                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    char ReadChar() {
                    	
                    	char c;
                    	cout << "Enter a character: ";
                    	cin >> c;
                    	return c;
                    }
                    char InvertingChar(char char1) {
                    
                    	return isupper(char1) ? tolower(char1) : toupper(char1);
                    }
                    
                    int main() {
                    
                    	char char1 = ReadChar();
                    	char1 = InvertingChar(char1);
                    
                    	cout << char1<< endl;
                    
                    	return 0;
                    }

## 31 -  Write a program to read a string then invert its letter's case and print it.

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    string ReadString() {
                    	
                    	string s;
                    	cout << "Enter a string : ";
                    	getline(cin, s);
                    	return s;
                    }
                    string ConvertingString () {
                    	string s = ReadString();
                    
                    	for (int i = 0; i < s.length(); i++) {
                    
                    		if (islower(s[i])) // إذا كان الحرف صغيرًا
                    			s[i] = toupper(s[i]); // تحويله إلى حرف كبير
                    
                    		else if (isupper(s[i]))  // إذا كان الحرف كبيرًا
                    			s[i] = tolower(s[i]); // تحويله إلى حرف صغير
                    	}
                    	return s;
                    }
                    
                    int main() {
                    
                    	string s = ConvertingString();
                    	cout << "The converted string is : " << s << endl;
                    
                        return 0;
                    }

## 32 - another solution 

                              #include <iostream>
                              #include <string>
                              #include <iomanip>
                              #include <cctype>
                              
                              using namespace std;
                              
                              string ReadString() {
                              	
                              	string s;
                              	cout << "Enter a string : ";
                              	getline(cin, s);
                              	return s;
                              }
                              char InverAllLetter(char char1) {
                              
                              	return isupper(char1) ? tolower(char1) : toupper(char1);
                              }
                              string ConvertingString () {
                              	string s = ReadString();
                              
                              	for (int i = 0; i < s.length(); i++) {
                              
                              	   s[i] = InverAllLetter(s[i]);
                              	}
                              	return s;
                              }
                              
                              int main() {
                              
                              	string s = ConvertingString();
                              	cout << "The converted string is : " << s << endl;
                              
                                  return 0;
                              }

## 33 - another solution by enum.

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    string ReadString() {
                    
                    	string s;
                    	cout << "Enter a string : ";
                    	getline(cin, s);
                    	return s;
                    }
                    enum enWhatToCount { CapitalLetter = 0, SmallLetter = 1, All= 3 };
                    
                    short CountLetter(string s , enWhatToCount WhatToCount = enWhatToCount::All) {
                    
                    
                    	if(WhatToCount == enWhatToCount::All)
                    		return s.length();
                    
                    
                    	short counter = 0;
                    
                    	for (short i = 0; i < s.length(); i++) {
                    		if(isupper(s[i]) && WhatToCount == CapitalLetter)
                    			counter++;
                    		if(islower(s[i]) && WhatToCount == SmallLetter)
                    			counter++;
                    	}
                    }
                    int main() {
                    
                    	string s = ReadString();
                    
                    	cout << "the length of the string is : " << s.length() << endl;
                    	cout << "The number of uppercase letters in the string is : " << CountLetter(s , enWhatToCount::CapitalLetter) << endl;
                    	cout << "The number of lowercase letters in the string is : " << CountLetter(s , enWhatToCount::SmallLetter) << endl;
                    	return 0;
                    }
                     
## 34 - Write a program to read a string and read a character then count the character in that string.

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    string ReadString() {
                    
                    	string s;
                    	cout << "Enter a string : ";
                    	getline(cin, s);
                    	return s;
                    }
                    enum enWhatToCount { CapitalLetter = 0, SmallLetter = 1, All= 3 };
                    
                    short CountLetter(string s , enWhatToCount WhatToCount = enWhatToCount::All) {
                    
                    
                    	if(WhatToCount == enWhatToCount::All)
                    		return s.length();
                    
                    
                    	short counter = 0;
                    
                    	for (short i = 0; i < s.length(); i++) {
                    		if(isupper(s[i]) && WhatToCount == CapitalLetter)
                    			counter++;
                    		if(islower(s[i]) && WhatToCount == SmallLetter)
                    			counter++;
                    	}
                    }
                    int main() {
                    
                    	string s = ReadString();
                    
                    	cout << "the length of the string is : " << s.length() << endl;
                    	cout << "The number of uppercase letters in the string is : " << CountLetter(s , enWhatToCount::CapitalLetter) << endl;
                    	cout << "The number of lowercase letters in the string is : " << CountLetter(s , enWhatToCount::SmallLetter) << endl;
                    	return 0;
                    }
                     
## 35 -  Write a program to read a string and read a character then count the character in that string(Match case or Not) using enum .


                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    string ReadString() {
                    
                    	string s;
                    	cout << "Enter a string : ";
                    	getline(cin, s);
                    	return s;
                    }
                    char ReadChar() {
                    
                    	char c;
                    	cout << "Enter a char : ";
                    	cin >> c;
                    	return c;
                    }
                    enum enChar{Small = 0, SmallAndCapital = 1};
                    
                    short CalcChar(string s , char c , enChar Letter = SmallAndCapital ) {
                    	short counter = 0;
                    
                    	for (short i = 0; i < s.length(); i++) {
                    		if (s[i] == c && Letter == Small) {
                    			counter++;
                    		}
                    
                    		if ((isupper(s[i]) || islower(s[i])) && Letter == SmallAndCapital) {
                    			counter++;
                    		}
                    
                    	}
                    	return counter;
                    }
                    int main() {
                    	string s  = ReadString();
                    	char c = ReadChar();
                    	cout << "Length of string = " << s.length() << endl;
                    	cout << "letter " << c << " count = " << CalcChar(s, c,enChar::Small) << endl;
                    	cout << "letter   " << c << " Small or Capital count  = " << CalcChar(s, c, enChar::SmallAndCapital) << endl;
                    }
 ##  36 - Another Solution BY Using Bool.

                     #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    string ReadString() {
                    
                    	string s;
                    	cout << "Enter a string : ";
                    	getline(cin, s);
                    	return s;
                    }
                    char ReadChar() {
                    
                    	char c;
                    	cout << "Enter a char : ";
                    	cin >> c;
                    	return c;
                    }
                    
                    short CalcChar(string s , char c , bool MatchCase = true ) {
                    	short counter = 0;
                    
                    	for (short i = 0; i < s.length(); i++) {
                    		if (MatchCase) {
                    			if (s[i] == c ) {
                    				counter++;
                    			}
                    		}
                    		else {
                    			if (tolower(s[i]) == tolower(c)) {
                    				counter++;
                    			}
                    		}
                    		
                    
                    	}
                    	return counter;
                    }
                    int main() {
                    	string s  = ReadString();
                    	char c = ReadChar();
                    	cout << "Length of string = " << s.length() << endl;
                    	cout << "letter " << c << " count = " << CalcChar(s, c) << endl;
                    	cout << "letter   " << c << " Small or Capital count  = " << CalcChar(s, c,false) << endl;
                    }
## 37 - write a program to read a character the check if it is a vowel or not (vowels are: a,e,I,o,u).


                     #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    char ReadChar() {
                    
                    	char c;
                    	cout << "Enter a char : ";
                    	cin >> c;
                    	return c;
                    }
                    short CheckChar(char c) {
                    	if (c == 'a' || c == 'e' || c == 'i' || c == 'o' || c == 'u' || c == 'A' || c == 'E' || c == 'I' || c == 'O' || c == 'U') {
                    		return 1;
                    	}
                    	else {
                    		return 0;
                    	}
                    }
                    int main() {
                    	char c = ReadChar();
                    
                    	if (CheckChar(c) == 1) {
                    		cout << "The char is a vowel" << endl;
                    	}
                    	else
                    	{
                    		cout << "The char is a consonant" << endl;
                    	}
                    }
                    
 ## 38 -   write a program to read a string  then count all  vowels in that string  (vowels are: a,e, i,o,u). 

 
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    string ReadString() {
                    	string s;
                    	cout << "Enter a string : ";
                    	getline(cin, s);
                        return s;
                    }
                    
                    char IsVowel(char c) {
                    	c = tolower(c);
                    	return ((c == 'a') || (c == 'e') || (c == 'i') || (c == 'o') || (c == 'u'));
                    }
                    short CheckIsVowel( string s) {
                    	
                    	short counter = 0;
                    
                    	for(short i= 0; i< s.length(); i++) {
                    		if ( IsVowel(s[i]))
                    			counter++;
                    	}
                    	return counter;
                    }
                    int main() {
                    	string s = ReadString();
                    
                    	cout << "Number of vowels in the string : " << CheckIsVowel(s) << endl;
                    }

## 39 -   write a program to read a string  then count all  vowels in that string  (vowels are: a,e, i,o,u). 

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <cctype>
                    
                    using namespace std;
                    
                    string ReadString() {
                    	string s;
                    	cout << "Enter a string : ";
                    	getline(cin, s);
                        return s;
                    }
                    
                    bool IsVowel(char c) {
                    	c = tolower(c);
                    	return ((c == 'a') || (c == 'e') || (c == 'i') || (c == 'o') || (c == 'u'));
                    }
                    void PrintIsVowel( string s) {
                    	
                    	short counter = 0;
                    
                    	for (short i = 0; i < s.length(); i++) {
                    		if (IsVowel(s[i]))
                    			cout << s[i] << " ";
                    	}
                        cout << endl;
                    
                    }
                    int main() {
                    	string s = ReadString();
                    
                    	cout << "Number of vowels in the string: ";
                    	PrintIsVowel(s);
                    }

 
## 40 - Write a program to read a string then print each word in that string.


                     #include <iostream>
                    #include <string>
                    
                    using namespace std;
                    
                    string ReadString() {
                    	string s  ;
                    	cout << "Enter a string: ";
                    	getline(cin, s);
                    	return s;
                    }
                    void PrintEachString(string s) {
                    
                    	for (int i = 0; i < s.length(); i++) {
                    		if (s[i] != ' ')
                    			cout << s[i] ;
                    		else
                    			cout << endl;
                    	}
                    }
                    int main() {
                    	string s = ReadString();
                    	cout << "Each character in the string is: " << endl;
                    	PrintEachString(s);
                    	return 0;
                    }
  ## 41 - Write a program to read a string then  count each word in that string.

                   #include <string>
                    #include <iostream>
                    
                    using namespace std;
                    
                    string ReadString() {
                    	string s;
                    	cout << "Enter a string: ";
                    	getline(cin, s);
                    	return s;
                    }
                    int PrintEachWordInString(string s) {
                    	string delim = " "; // delimiter     
                    	cout << "\nThe number of words in your string is: \n\n";
                    	int pos = 0;
                    	string sWord;
                    	
                    	short counter = 0;
                    	while ((pos = s.find(delim)) != std::string::npos)
                    	{
                    		sWord = s.substr(0, pos); // store the word  
                    		if (sWord != "")
                    		{
                    			counter++;
                    		}
                    		s.erase(0, pos + delim.length());  /* erase() until positon and move to next word. */
                    	}
                    	return counter;
                    }
                    
                    int main() {
                    
                    	cout << PrintEachWordInString(ReadString());
                    	return 0;
                    }
                    
## 42 - Write a program to read string then make a function to split each word in vector.

                    #include <string>
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    string ReadString() {
                        string s;
                        cout << "Enter a string: ";
                        getline( cin, s);
                        return s;
                    }
                    int FullVectorEachString(string s, vector<string>& v) {
                        
                                            string delim = " ";
                        short pos = 0;
                        string token;
                    
                        short counter = 0;
                        cout << "the number of token : " ;
                        while ((pos = s.find(delim)) != std::string::npos) {
                            token = s.substr(0, pos);
                            if (token != "") {
                                v.push_back(token);
                                counter++;
                            }
                            s.erase(0,pos+delim.length());
                    
                        }
                        if (s != "") {
                            v.push_back(s);
                            counter++;
                         }
                        return  counter;
                    }
                    void PrintVector(vector <string> v) {
                        cout << "\n-----the vector-----\n";
                        for (string j : v) {
                            cout << j << endl;
                        }
                    }
                    int main()
                    {
                        vector <string> v;
                        
                        cout << FullVectorEachString(ReadString(), v);
                        PrintVector(v);
                    
                    }
## 43 - Write a program to read a string then trim left, right , all.


                     #include <string>
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    string TrimLeft(string s) {
                        for (short i = 0; i < s.length() - 1; i++) {
                            if (s[i] != ' ') {
                                return s.substr(i, s.length() - i);
                            }
                        }
                        return "";
                    }
                    
                    string TrimRight(string s) {
                        for (short i = s.length() - 1; i >= 0; i--) {
                            if (s[i] != ' ') {
                                return s.substr(0, i + 1);
                            }
                        }
                        return "";
                    }
                    
                    string Trim(string s) {
                        return TrimLeft(TrimRight(s));
                    }
                    
                    int main() {
                        string s = "   moustafa sad   ";
                    
                        cout << "Trimmed left:" << TrimLeft(s) << endl;
                        cout << "Trimmed right:" << TrimRight(s) << endl;
                        cout << "Trimmed:" << Trim(s) << endl;
                    
                        return 0;
                    }
 ## 44 - wriet a program to join vector of sttring into a one stringg with separators.

                     #include <string>
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    string join(vector <string> v) {
                        for (string i : v) {
                            cout << i << " ";
                        }
                        return "";
                    }
                    int main() {
                    
                        vector <string> v = {"Mustafa" ,"Sad", "Mohammed","Mohammed"};
                        join(v);
                    
                        return 0;
                    }

## 45- Another Solution.

                    #include <string>
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    string join(vector <string> v , string delim) {
                    
                        string s1;
                        for (string i : v) {
                            s1 = s1 + i + delim;
                        }
                        return s1.substr(0 , s1.length()-delim.length());
                    }
                    int main() {
                    
                        vector <string> v = {"Mustafa" ,"Sad", "Mohammed","Mohammed"};
                         cout <<  join(v ,"##");
                    
                        return 0;
                    }

## 46 - overloading example 

                    #include <string>
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    string JoinString(vector <string> v, string delim) {
                    
                    	string s1;
                    	for (string i : v) {
                    		s1 = s1 + i + delim;
                    	}
                    	return s1.substr(0, s1.length() - delim.length());
                    }
                    string JoinString(string arr[], short length, string delim) {
                    
                    	string s1;
                    	for (int i = 0; i < length; i++) {
                    		s1 = s1 + arr[i] + delim;
                    	}
                    	return s1.substr(0, s1.length() - delim.length());
                    }
                    int main() {
                    
                    	vector <string> v = { "Mustafa" ,"Sad", "Mohammed","Mohammed" };
                    	string arr[] = { "Mustafa" ,"Sad", "Mohammed","Mohammed" };
                    
                    	cout << "\nvector after join :" << endl;
                    	cout << JoinString(v, "##");
                    
                    	cout << "\narray after join :" << endl;
                    	cout << JoinString(arr, 4,"##");
                    
                    	return 0;
                    }

## 47 - Reverse string .


                    #include <string>
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    string ReverseString(string arr[]) {
                    	for (short i = arr->length(); i >= 0; i--) {
                    		cout << arr[i] << " ";
                    	}	
                    	return "";
                    }
                    int main() {
                    
                    	string arr[100] = {"Mustafa" ,"Sad", "Mohammed","Mohammed"};
                    
                    	ReverseString(arr);
                    	return 0;
                    }

## 48 - Reverse and split .

                    #include <string>
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    string ReadString() {
                        string s;
                        cout << "Please enter string: ";
                        getline(cin, s);
                        return s;
                    }
                    
                    vector<string> SplitString(string s, string delim) {
                        short pos = 0;
                        string word;
                        vector<string> v1;
                    
                        while ((pos = s.find(delim)) != std::string::npos) {
                            word = s.substr(0, pos);
                            if (word != " ") {
                                v1.push_back(word);
                            }
                            s.erase(0, pos + delim.length());
                        }
                        if (s != "") {
                            v1.push_back(s);
                        }
                        return v1;
                    }
                    string ReverseString(string s) {
                        vector <string> vString = SplitString(s, " ");
                        string s2 = "";
                    
                        vector <string>::iterator iter = vString.end();
                        while (iter != vString.begin()) {
                            --iter;
                            s2 += *iter + " ";
                        }
                        s2 = s2.substr(0, s2.length() - 1); // remove last space 
                        return s2;
                    }
                    
                    int main() {
                        string s = ReadString();
                        cout << ReverseString(s);
                        return 0;
                    }

## 49 - Replace string .

                    #include <string>
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    string ReadString() {
                        string s;
                        cout << "Please enter string: ";
                        getline(cin, s);
                        return s;
                    }
                    
                    vector<string> SplitString(string s, string delim) {
                        short pos = 0;
                        string word;
                        vector<string> v1;
                    
                        while ((pos = s.find(delim)) != std::string::npos) {
                            word = s.substr(0, pos);
                            if (word != " ") {
                                v1.push_back(word);
                            }
                            s.erase(0, pos + delim.length());
                        }
                        if (s != "") {
                            v1.push_back(s);
                        }
                        return v1;
                    }
                    string ReverseString(string s) {
                    
                        vector <string> vString = SplitString(s, " ");
                    
                        string s2 = "";
                        for (string i : vString) {
                            if (i == "jordan")
                                i = "USA";
                            s2 += i + " ";
                        }
                        return s2;
                    }
                    
                    int main() {
                        string s = ReadString();
                        cout << ReverseString(s);
                        return 0;
                    }

## 50 - Replace string 

                    #include <string>
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    string Replace(string s1, string s2R, string SR) {
                    
                        short pos =  s1.find(s2R);
                    
                        while ( pos != std::string::npos) {
                            s1 = s1.replace(pos, s2R.length(), SR);
                            pos = s1.find(s2R);
                        }
                        return s1;
                    }
                    
                    
                    int main() {
                        string s1 = "Mustafa from Egypt , and welcom Egypt";
                        string s2R = "Egypt";
                        string SR = "USA";
                    
                        cout << Replace(s1, s2R, SR);
                    }
                    
## 51 -  Write a program to remove punctuation.


                    #include <string>
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    
                    string RemovePunctuations(string &word) {
                    	string s2 = "";
                    	for (short i = 0; i < word.length(); i++) {
                    		if (!ispunct(word[i]))
                    			s2 += word[i];
                    	}
                    	return s2;
                    
                    }
                    int main() {
                    	string s = "Welcmoe to jordan, Jordan is a nice country; it's amazing.";
                    
                    	 cout << "example before Remove " << s << endl;
                    
                    	 cout << "example after Remove " << RemovePunctuations(s) << endl;
                    
                    	return 0;
                    }

## 53 - write a program to read bank client data record and convert it to one line.


                    #include <string>
                    #include <iostream>
                    #include <vector>
                    using namespace std;
                    
                    
                    struct stClient {
                    	string AccountNumber;
                    	string PinCode;
                    	string Name;
                    	string Phone;
                    	double AccountBlance;
                    
                    };
                    stClient Read() {
                    
                    	stClient client;
                    
                    
                    	cout << "Enter Account Number?";
                    	getline(cin, client.AccountNumber);
                    
                    	cout << "Enter PinCode ? ";
                    	getline(cin, client.PinCode);
                    
                    	cout << "Enter Name?";
                    	getline(cin, client.Name);
                    
                    	cout << "Enter Phone?";
                    	getline(cin, client.Phone);
                    
                    
                    	cout << "Enter AccountBalance ?";
                    	cin >> client.AccountBlance;
                    
                    	return client;
                    }
                    string converClintData(stClient client, string sperator = "#//#") {
                    
                    	string Record = "";
                    
                    	Record += client.AccountNumber + sperator;
                    	Record += to_string(client.AccountBlance) + sperator;
                    	Record += client.Name + sperator;
                    	Record += client.Phone + sperator;
                    	Record += client.PinCode + sperator;
                    
                    	return Record;
                    }
                    
                    int main() {
                    
                    	cout << "\nPlease enter client Data: \n";
                    	stClient Client;
                    
                    	Client = Read();
                    
                    	cout << converClintData(Client);
                    
                    	return 0;
                    }

## 54 - Write a program to convert line data to record and print it(split ):


                              #include <string>
                              #include <iostream>
                              #include <vector>
                              using namespace std;
                              
                              struct stClient {
                                  string AccountNumber;
                                  string PinCode;
                                  string Name;
                                  string Phone;
                                  double AccountBlance; // Typo: AccountBalance
                              };
                              
                              vector<string> SplitString(const string& s, const string& Delim) {
                                  size_t pos = 0;
                                  string word;
                                  vector<string> v1;
                              
                                  string tempString = s; // Create a temporary string to avoid modifying the original
                                  while ((pos = tempString.find(Delim)) != std::string::npos) {
                                      word = tempString.substr(0, pos);
                                      if (word != Delim) { // Avoid adding the delimiter itself
                                          v1.push_back(word);
                                      }
                                      tempString.erase(0, pos + Delim.length());
                                  }
                                  if (!tempString.empty()) {
                                      v1.push_back(tempString); // Add the remaining substring
                                  }
                                  return v1;
                              }
                              
                              stClient converClintData(const string& s, const string& separator) {
                                  vector<string> v1 = SplitString(s, separator);
                                  stClient client;
                              
                                  if (v1.size() >= 5) { // Check if there are enough elements
                                      client.AccountNumber = v1[0];
                                      client.AccountBlance = stod(v1[1]); // Convert string to double
                                      client.Name = v1[2];
                                      client.Phone = v1[3];
                                      client.PinCode = v1[4];
                                  }
                                  else {
                                      cerr << "Invalid input format!" << endl;
                                  }
                              
                                  return client;
                              }
                              
                              void PrintValues(const stClient& client) {
                                  cout << "AccountNumber: " << client.AccountNumber << endl;
                                  cout << "AccountBalance: " << client.AccountBlance << endl;
                                  cout << "Name: " << client.Name << endl;
                                  cout << "Phone: " << client.Phone << endl;
                                  cout << "PinCode: " << client.PinCode << endl;
                              }
                              
                              int main() {
                                  cout << "\nPlease enter client Data: \n";
                              
                                  string s = "A150#//#1234#//#Mohammed Abu-Hadhoud#//#079999#//#5270.000000";
                              
                                  cout << "\nLine Record is: \n";
                                  cout << s << endl;
                              
                                  stClient client = converClintData(s, "#//#");
                              
                                  PrintValues(client);
                              
                                  return 0;
                              }


## 55 - Write a program to ask you to enter clients and save them to a file.



                              #include<iostream>
                              #include<fstream>
                              #include<string>
                              #include<vector>
                              using namespace std;
                              
                              const string ClientsFileName = "Clients.txt";
                              
                              struct stClient {
                              	string AccountNumber;
                              	string PinCode;
                              	string Name;
                              	string Phone;
                              	double AccountBalance;
                              };
                              stClient ReadNewClient() {
                              	stClient Client;
                              	cout << "Enter Account Number? ";
                              
                              	getline(cin >> ws, Client.AccountNumber);
                              	cout << "Enter PinCode? ";
                              	getline(cin, Client.PinCode);
                              	cout << "Enter Name? ";
                              	getline(cin, Client.Name);
                              	cout << "Enter Phone? ";
                              	getline(cin, Client.Phone);
                              	cout << "Enter AccountBalance? ";
                              	cin >> Client.AccountBalance;
                              	return Client;
                              }
                              string ConvertRecordToLine(stClient Client, string Seperator = "#//#")
                              {
                              	string stClientRecord = "";
                              	stClientRecord += Client.AccountNumber + Seperator;
                              	stClientRecord += Client.PinCode + Seperator;
                              	stClientRecord += Client.Name + Seperator;
                              	stClientRecord += Client.Phone + Seperator;
                              	stClientRecord += to_string(Client.AccountBalance);
                              	return stClientRecord;
                              }
                              void AddDataLineToFile(string FileName, string stDataLine)
                              {
                              	fstream MyFile;
                              	MyFile.open(FileName, ios::out | ios::app);
                              	if (MyFile.is_open()) {
                              		MyFile << stDataLine << endl;
                              		MyFile.close();
                              	}
                              }
                              void AddNewClient() {
                              	stClient Client;
                              	Client = ReadNewClient();
                              	AddDataLineToFile(ClientsFileName, ConvertRecordToLine(Client));
                              }
                              
                              void AddClients() {
                              	char AddMore = 'Y';
                              	do {
                              		system("cls");
                              		cout << "Adding New Client:\n\n";
                              		AddNewClient();
                              		cout << "\nClient Added Successfully, do you want to add more clients? Y/N? ";
                              		cin >> AddMore;
                              	} while (toupper(AddMore) == 'Y');
                              } int main() {
                              
                              	AddClients();
                              	system("pause>0");
                              	return 0;
                              }

## 56 - Write a program to ask you to enter clients and save them to file:




                              #include<iostream>
                              #include<fstream>
                              #include<string>
                              #include<vector>
                              using namespace std;
                              
                              const string ClientsFileName = "Clients.txt";
                              
                              struct stClient {
                              	string AccountNumber;
                              	string PinCode;
                              	string Name;
                              	string Phone;
                              	double AccountBalance;
                              };
                              stClient ReadNewClient() {
                              	stClient Client;
                              	cout << "Enter Account Number? ";
                              
                              	getline(cin >> ws, Client.AccountNumber);
                              	cout << "Enter PinCode? ";
                              	getline(cin, Client.PinCode);
                              	cout << "Enter Name? ";
                              	getline(cin, Client.Name);
                              	cout << "Enter Phone? ";
                              	getline(cin, Client.Phone);
                              	cout << "Enter AccountBalance? ";
                              	cin >> Client.AccountBalance;
                              	return Client;
                              }
                              string ConvertRecordToLine(stClient Client, string Seperator = "#//#")
                              {
                              	string stClientRecord = "";
                              	stClientRecord += Client.AccountNumber + Seperator;
                              	stClientRecord += Client.PinCode + Seperator;
                              	stClientRecord += Client.Name + Seperator;
                              	stClientRecord += Client.Phone + Seperator;
                              	stClientRecord += to_string(Client.AccountBalance);
                              	return stClientRecord;
                              }
                              void AddDataLineToFile(string FileName, string stDataLine)
                              {
                              	fstream MyFile;
                              	MyFile.open(FileName, ios::out | ios::app);
                              	if (MyFile.is_open()) {
                              		MyFile << stDataLine << endl;
                              		MyFile.close();
                              	}
                              }
                              void AddNewClient() {
                              	stClient Client;
                              	Client = ReadNewClient();
                              	AddDataLineToFile(ClientsFileName, ConvertRecordToLine(Client));
                              }
                              
                              void AddClients() {
                              	char AddMore = 'Y';
                              	do {
                              		system("cls");
                              		cout << "Adding New Client:\n\n";
                              		AddNewClient();
                              		cout << "\nClient Added Successfully, do you want to add more clients? Y/N? ";
                              		cin >> AddMore;
                              	} while (toupper(AddMore) == 'Y');
                              } int main() {
                              
                              	AddClients();
                              	system("pause>0");
                              	return 0;
                              }


## 57 - Write a program to read clients file and show them on the screen as follows:


                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    #include<iomanip>
                    using namespace std;
                    const string ClientsFileName = "Clients.txt";
                    struct sClient { 
                    	string AccountNumber; 
                    	string PinCode; 
                    	string Name; 
                    	string Phone;
                    	double AccountBalance = 0.0;
                    };
                    vector<string> SplitString(string S1, string Delim) {
                    
                    	vector<string> vString;
                    	
                    	size_t pos = 0;
                    	
                    	string sWord;
                    
                    	while ((pos = S1.find(Delim)) != std::string::npos) {
                    		
                    		sWord = S1.substr(0, pos);
                    		// store the word  
                    		if (sWord != "") {
                    			vString.push_back(sWord);
                    		} 
                    		S1.erase(0, pos + Delim.length());
                    	} if (S1 != "") {
                    		vString.push_back(S1); // it adds last word of the string.   
                    	}
                    	return vString;
                    }
                    
                    sClient ConvertLinetoRecord(string Line, string Seperator = "#//#") {
                    	
                    	sClient Client;
                    	
                    	vector<string> vClientData;
                    
                    	vClientData = SplitString(Line, Seperator);
                    	Client.AccountNumber = vClientData[0];
                    	Client.PinCode = vClientData[1];
                    	Client.Name = vClientData[2];
                    	Client.Phone = vClientData[3];
                    	Client.AccountBalance = stod(vClientData[4]); //cast string to double
                    	
                    	return Client;
                    } 
                    vector <sClient> LoadCleintsDataFromFile(string FileName) {
                    	
                    	vector <sClient> vClients; fstream MyFile;
                    	
                    	MyFile.open(FileName, ios::in);//read Mode
                    	
                    	if (MyFile.is_open())
                    	{
                    		string Line;
                    		sClient Client;
                    		while (getline(MyFile, Line))
                    		{
                    			Client = ConvertLinetoRecord(Line);
                    			vClients.push_back(Client);
                    		}
                    		MyFile.close();
                    	}
                    	return vClients;
                    }
                    void PrintClientRecord(sClient Client)
                    {
                    	cout << "| " << setw(15) << left << Client.AccountNumber;
                    	cout << "| " << setw(10) << left << Client.PinCode;
                    	cout << "| " << setw(40) << left << Client.Name;
                    	cout << "| " << setw(12) << left << Client.Phone;
                    	cout << "| " << setw(12) << left << Client.AccountBalance;
                    
                    }
                    void PrintAllClientsData(vector <sClient> vClients) {
                    
                    	cout << "\n\t\t\t\t\tClient List (" << vClients.size() << ") Client(s).";
                    
                    	cout << "\n_______________________________________________________";
                    	cout << "_________________________________________\n" << endl;
                    	cout << "| " << left << setw(15) << "Accout Number";
                    	cout << "| " << left << setw(10) << "Pin Code";
                    	cout << "| " << left << setw(40) << "Client Name";
                    	cout << "| " << left << setw(12) << "Phone";
                    	cout << "| " << left << setw(12) << "Balance";
                    	cout << "\n_______________________________________________________";
                    	cout << "_________________________________________\n" << endl;
                    
                    	for (sClient Client : vClients)
                    	{
                    		PrintClientRecord(Client);
                    		cout << endl;
                    	}
                    	cout << "\n_______________________________________________________";
                    	cout << "_________________________________________\n" << endl;
                    
                    }
                    int main() {
                    	vector <sClient> vClients = LoadCleintsDataFromFile(ClientsFileName);
                    	PrintAllClientsData(vClients);
                    	system("pause>0");
                    	return 0;
                    }

## 58 - Write a program to find the client by account number and print it on the screen.


                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    #include<iomanip>
                    using namespace std;
                    
                    const string ClientsFileName = "Clients.txt";
                    
                    struct sClient {
                    	string AccountNumber;
                    	string PinCode;
                    	string Name;
                    	string Phone;
                    	double AccountBalance = 0.0;
                    };
                    
                    vector<string> SplitString(string S1, string Delim) {
                    	vector<string> vString;
                    	size_t pos = 0;
                    	string sWord;
                    
                    	while ((pos = S1.find(Delim)) != std::string::npos) {
                    		sWord = S1.substr(0, pos);
                    		// store the word  
                    		if (sWord != "") {
                    			vString.push_back(sWord);
                    		}
                    		S1.erase(0, pos + Delim.length());
                    	}
                    	if (S1 != "") {
                    		vString.push_back(S1); // it adds the last word of the string.   
                    	}
                    	return vString;
                    }
                    
                    sClient ConvertLinetoRecord(string Line, string Seperator = "#//#") {
                    	sClient Client;
                    	vector<string> vClientData;
                    	vClientData = SplitString(Line, Seperator);
                    	Client.AccountNumber = vClientData[0];
                    	Client.PinCode = vClientData[1];
                    	Client.Name = vClientData[2];
                    	Client.Phone = vClientData[3];
                    	Client.AccountBalance = stod(vClientData[4]); //cast string to double
                    	return Client;
                    }
                    
                    vector <sClient> LoadCleintsDataFromFile(string FileName) {
                    	vector <sClient> vClients;
                    	fstream MyFile;
                    	MyFile.open(FileName, ios::in);//read Mode
                    	if (MyFile.is_open()) {
                    		string Line;
                    		sClient Client;
                    		while (getline(MyFile, Line)) {
                    			Client = ConvertLinetoRecord(Line);
                    			vClients.push_back(Client);
                    		}
                    		MyFile.close();
                    	}
                    	return vClients;
                    }
                    
                    void PrintClientCard(sClient Client)
                    {
                    	cout << "\nThe following are the client details:\n";
                    	cout << "\nAccout Number: " << Client.AccountNumber;
                    	cout << "\nPin Code     : " << Client.PinCode;
                    	cout << "\nName         : " << Client.Name;
                    	cout << "\nPhone        : " << Client.Phone;
                    	cout << "\nAccount Balance: " << Client.AccountBalance;
                    }
                    bool FindClientByAccountNumber(string AccountNumber, sClient& Client)
                    {
                    	vector <sClient> vClients = LoadCleintsDataFromFile(ClientsFileName);
                    	for (sClient C : vClients)
                    	{
                    		if (C.AccountNumber == AccountNumber)
                    		{
                    			Client = C;
                    			return  true;
                    		}
                    	} return false;
                    }
                    string ReadClientAccountNumber() {
                    	string AccountNumber = "";
                    	cout << "\nPlease enter AccountNumber? ";
                    	cin >> AccountNumber;
                    	return AccountNumber;
                    }
                    
                    int main()
                    {
                    	sClient Client;
                    	string AccountNumber = ReadClientAccountNumber();
                    	if (FindClientByAccountNumber(AccountNumber, Client)) 
                    	{
                    		PrintClientCard(Client); 
                    	}
                    	else 
                    	{ 
                    		cout << "\nClient with Account Number (" << AccountNumber << ") is Not Found!"; 
                    	}    
                    
                    	system("pause>0"); 
                    
                    	return 0;
                    }

## 59 - Tow Dimensional Array 

                    #include<iostream>      
                    using namespace std;
                    
                    
                    int main() {
                    
                    	int arr[3][4] = { {1,2,3,4},{5,6,7,8},{9,10,11,12} };
                    
                    	for (int i = 0; i < 3; i++) {
                    
                    		for (int j = 0; j < 4; j++) {
                    
                    			cout << arr[i][j] << " ";
                    		}
                    		cout << endl;
                    	}
                    	return 0;
                    }

## 60 Tow Dimensional Array  


                    #include<iostream>
                    using namespace std;
                    int main() {
                    
                    	int arr[10][10];
                    
                    	for (int i = 0; i < 10; i++) 
                    	{
                    		for (int j = 0; j < 10; j++) 
                    		{
                    			arr[i][j] = (i + 1) * (j + 1);
                    		}
                    	}
                    
                    	for (int i = 0; i < 10; i++)
                    	{
                    		for (int j = 0; j < 10; j++)
                    		{
                    			printf("%0*d ", 2, arr[i][j]);
                    		}
                    		cout << endl;
                    	}
                    }

## 61 write file 


                    #include<iostream>
                    #include<fstream>
                    
                    using namespace std;
                    
                    
                    int main() {
                    
                    	fstream FileOne;
                    
                    	FileOne.open("FileOne.txt", ios::out);
                    
                    	if (FileOne.is_open()) {
                    
                    		FileOne << "Mustafa saad mohammed mohammed Elgabear\n";
                    		FileOne << "Mustafa saad mohammed mohammed Elgabear\n";
                    		FileOne << "Mustafa saad mohammed mohammed Elgabear\n";
                    		FileOne << "Mustafa saad mohammed mohammed Elgabear\n";
                    
                    		FileOne.close();
                    	}
                    	return 0;
                    
                    }


## 62- append word in file


                    #include<iostream>
                    #include<fstream>
                    using namespace std;
                    
                    int main() {
                    
                    	fstream FileOne;
                    
                    	FileOne.open("FileOne.txt", ios::out | ios::app);
                    
                    	if (FileOne.is_open()) {
                    
                    		FileOne << "Mustafa saad mohammed mohammed Elgabear\n";
                    		FileOne << "Mustafa saad mohammed mohammed Elgbear\n";
                    		FileOne << "Mustafa  mohammed  \n";
                    		FileOne << "Mustafa saad mohammed  \n";	
                    		FileOne << "Mustafa saad mohammed  \n";
                    		FileOne << "Mustafa saad mohammed  \n";
                    
                    		FileOne.close();
                    	}
                    	return 0;
                    
                    }



## 63 Read from file 


                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    
                    using namespace std;
                    
                    void PrintFile(string FileName) {
                    
                    	fstream FileOne;
                    
                    	FileOne.open(FileName , ios::in);
                    
                    	if (FileOne.is_open()) {
                    	
                    		string Line;
                    
                    		while(getline(FileOne, Line))
                    		{
                    			cout << Line << endl;
                    
                    		}
                    		FileOne.close();
                    	}
                    
                    }
                    
                    int main() {
                    
                    	PrintFile("FileOne.txt");
                    	return 0;
                    
                    }

##   64  Load data from the file and store it in a vector 

                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    
                    using namespace std;
                    
                    void PrintFile(string FileName, vector <string>& Vfile) {
                    
                    	fstream FileOne;
                    
                    	FileOne.open(FileName , ios::in);
                    
                    	if (FileOne.is_open()) {
                    	
                    		string Line;
                    
                    		while(getline(FileOne, Line))
                    		{
                    			Vfile.push_back( Line);
                    
                    		}
                    		FileOne.close();
                    	}
                    
                    }
                    
                    int main() {
                    
                    	vector <string> Vfile;
                  
                    	PrintFile("FileOne.txt" , Vfile);
                    
                    	for (string& Line : Vfile) {
                    		cout << Line << endl;
                    	}
                    	return 0;
                    }

## 65 Convert Record to Line:-


                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    
                    using namespace std;
                    
                    struct sClient
                    {
                    	string AccountNumber;
                    	string Name;
                    	string pincode; 
                    	string phone;
                    	double AccountBalance;
                    
                    };
                    sClient ReadNewClient() {
                    
                    	sClient Client;
                    
                    	cout << "Please enter Client Data:" << endl;
                    
                    	cout << "enter Account Number?" << endl ;
                    	getline(cin, Client.AccountNumber);
                    	
                    	cout << " enter PinCode?" << endl;
                    	getline(cin, Client.pincode);
                    	
                    	cout << " enter Name?" << endl;
                    	getline(cin, Client.Name);
                    	
                    	cout << " enter Phone?" << endl;
                    	getline(cin, Client.phone);
                    	
                    	cout << " enter AccountBalance?" << endl;
                    	getline(cin, Client.AccountNumber);
                    
                    	return Client;
                    	
                    }
                    
                    string ConvertRecord(sClient Client, string Sperator = "#//#") {
                    
                    	string addRecord; 
                    
                    	addRecord += Client.AccountNumber + Sperator;
                    	addRecord += Client.Name + Sperator;
                    	addRecord += Client.phone + Sperator;
                    	addRecord += Client.pincode + Sperator;
                    	addRecord += to_string( Client.AccountBalance) ;
                    
                    	return addRecord;
                    }
                    
                    int main() {
                    
                    	sClient Client;
                    	Client = ReadNewClient();
                    	
                    	cout << "\n\n Client Record for Saving is: \n";
                    	cout << ConvertRecord(Client);
                    
                    	system("pause>0");
                    	return 0;
                    
                    	
                    
                    }


## 67 Splitting Function 


                    vector<string> SplitString(string S1, string Delim) {
                    
                    	vector<string> vString; 
                    	
                    	short pos = 0; 
                    	string sWord; 
                    
                    	while ((pos = S1.find(Delim)) != std::string::npos)     { 
                    
                    		sWord = S1.substr(0, pos); 
                    
                    		if (sWord != "")  
                    		{ 
                    			vString.push_back(sWord);       
                    		} S1.erase(0, pos + Delim.length()); 
                    	}
                    	if (S1 != "")   
                    	{     
                    		vString.push_back(S1); 
                    	}
                    	return Vstring;
                    } 


## 68 class and object 


                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    
                    using namespace std;
                    
                    
                    class claPerson {
                    
                    public:
                    	string FirstName;
                    	string LastName;
                    
                    	string FullName() {
                    
                    		return FirstName + " " + LastName;
                    	}
                    };
                    int main() {
                    
                    	claPerson Person1;
                    
                    	Person1.FirstName = "Mustafa";
                    	Person1.LastName = "Sad";
                    
                    	cout << Person1.FullName() << endl;
                    
                    	return 0;
                    }


## 69 object in Memory 

                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    
                    using namespace std;
                    
                    
                    class claPerson {
                    
                    public:
                    	string FirstName;
                    	string LastName;
                    
                    	string FullName() {
                    
                    		return FirstName + " " + LastName;
                    	}
                    };
                    int main() {
                    
                    	claPerson Person1 , Person2 , Person3;
                    
                    	Person1.FirstName = "Mustafa";
                    	Person1.LastName = "Sad";
                    
                    	Person2.FirstName = "mohammed";
                    	Person2.LastName = "Sad";
                    
                    	Person3.FirstName = "mahmoud";
                    	Person3.LastName = "Sad";
                    
                    
                    	cout << Person1.FullName() << endl;
                    	cout << Person2.FullName() << endl;
                    	cout << Person3.FullName() << endl;
                    
                    	return 0;
                    }
                    

## 70 public and protected and private


                              #include<iostream>
                              #include<fstream>
                              #include<string>
                              #include<vector>
                              
                              using namespace std;
                              
                              class clsPerson {
                              
                              private:
                              	int varibel1 = 100;
                              	int function1() {
                              		return 20;
                              	}
                              
                              protected:
                              	int varibel2 = 100;
                              	int function2() {
                              		return 50;
                              	}
                              
                              public:
                              	string FirstName;
                              	string LastName;
                              
                              	string FullName() {
                              		return FirstName + " " + LastName;
                              	}
                              
                              	float Function3() {
                              		return function1() * function2() * varibel1 * varibel2;
                              	}
                              };
                              
                              int main() {
                              
                              	clsPerson person1;
                              
                              	person1.FirstName = "Mustafa";
                              	person1.LastName = "saad";
                              
                              	cout << person1.Function3() << endl;
                              	cout << person1.FullName() << endl;
                              
                              	return 0;
                              }


## 71   Set and Get properties 


                              #include<iostream>
                              #include<fstream>
                              #include<string>
                              #include<vector>
                              
                              using namespace std;
                              
                              class clsPerson {
                              
                              private:
                              	string _FirstName;
                              	string _LastName;
                              
                              
                              public:
                              	
                              	void setFirstName(string firstName) {
                              		_FirstName = firstName;
                              	}
                              	string FirstName() {
                              		return _FirstName;
                              	}
                              	void setLastName(string lastName) {
                              		_LastName = lastName;
                              	}
                              	string LastName() {
                              		return _LastName;
                              	}
                              
                              };
                              
                              int main() {
                              
                              	clsPerson person1;
                              
                              	person1.setFirstName("Mustafa");
                              	person1.setLastName("saad");
                              
                              	cout << "firstName: " << person1.FirstName() << endl;
                              	cout << "lastName: " << person1.LastName() << endl;
                              
                              	
                              	system("pause>0"); 
                              	return 0;
                              }




## 72 Read Only Property 

                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    
                    using namespace std;
                    
                    class clsPerson {
                    
                    private:
                    
                    	int _ID = 10; 
                    	string _FirstName;
                    	string _LastName;
                    
                    
                    public:
                    	
                    	int ID() {
                    		return _ID;
                    	}
                    	void setFirstName(string firstName) {
                    		_FirstName = firstName;
                    	}
                    	string FirstName() {
                    		return _FirstName;
                    	}
                    	void setLastName(string lastName) {
                    		_LastName = lastName;
                    	}
                    	string LastName() {
                    		return _LastName;
                    	}
                    
                    };
                    
                    int main() {
                    
                    	clsPerson person1;
                    
                    	person1.setFirstName("Mustafa");
                    	person1.setLastName("saad");
                    
                    	cout << "firstName: " << person1.FirstName() << endl;
                    	cout << "lastName: " << person1.LastName() << endl;
                    	cout << "ID: " << person1.ID() << endl;
                    
                    	
                    	system("pause>0"); 
                    	return 0;
                    }
## 73  Properties get and set                  

                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    
                    using namespace std;
                    
                    class clsPerson {
                    
                    private:
                    	string _FirstName;
                    
                    public:
                    	
                    	
                    	void setFirstName(string firstName) {
                    		_FirstName = firstName;
                    	}
                    	string GetFirstName() {
                    		return _FirstName;
                    	}
                    	
                    	__declspec(property(get = GetFirstName, put = setFirstName)) string FirstName;
                    };
                    
                    int main() {
                    
                    	clsPerson person1;
                    
                    	person1.FirstName = "Mustafa";
                    	cout << "firstName: " << person1.FirstName << endl;
                    
                    	system("pause>0"); 
                    	return 0;
                    }


## 74  A calculator program based on OOP standards 

                    
                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    
                    using namespace std;
                    
                    class clsCacluator {
                    
                    private:
                    	
                    
                    	float _Result = 0;
                    	float _LastNumber = 0;
                    	string _LastOperation = "Clear";
                    	float _PreviousResult = 0;
                    	bool _IsZero(float Number) {
                    		return (Number == 0);
                    	}
                    
                    public:
                    
                    	void Add(float Number) {
                    		_LastNumber = Number;
                    		_PreviousResult = _Result;
                    		_LastOperation = "adding";
                    		_Result += _LastNumber;
                       }
                    
                    
                    	void Substruct(float Number) {
                    		_LastNumber = Number;
                    		_PreviousResult = _Result;
                    		_LastOperation = "Subtraction";
                    		_Result -= _LastNumber;
                       }
                    
                    
                    	void Divide(float Number) {
                    
                    		_LastNumber = Number;
                    
                    		if (_IsZero(Number)) {
                    			Number = 1; 
                    		}
                    
                    		_PreviousResult = _Result;
                    		_LastOperation = "Dividing";
                    		_Result /= _LastNumber;
                       }
                    
                    
                    	void Multiply(float Number) {
                    		_LastNumber = Number;
                    		_PreviousResult = _Result;
                    		_LastOperation = "Multiplying";
                    		_Result *= _LastNumber;
                       }	
                    
                    
                    	float GetResult() {
                    		return _Result;
                    	}
                    
                    	void Clear() {
                    		_LastNumber = 0;
                    		_PreviousResult = 0;
                    		_LastOperation = "Multiply";
                    		_Result *= 0;
                       }	
                    
                    
                    	void CancellLastOperation() {
                    		_LastNumber = 0;
                    		_LastOperation = " Cancell last operation ";
                    		_Result = _PreviousResult;
                       }
                    
                    
                    	void PrintResult() 
                    	{
                    		cout << "The Result After " << _LastOperation << " " << _LastNumber << " is : " << _Result << endl;
                    	}
                    	
                    };
                    
                    int main() {
                    
                    	clsCacluator cacl1;
                    
                    	cacl1.Clear();
                    
                    	cacl1.Add(10);
                    	cacl1.PrintResult();
                    	
                    	cacl1.Add(100);
                    	cacl1.PrintResult();
                    
                    	cacl1.Divide(20);
                    	cacl1.PrintResult();
                    
                    	cacl1.Multiply(20);
                    	cacl1.PrintResult();	
                    	
                    	cacl1.Substruct(20);
                    	cacl1.PrintResult();
                    
                    	
                    	
                    	system("pause>0"); 
                    	return 0;
                    }


## 75 Fill Matrix 3*3 BY Random Number from 1 to 100:-

                    
                    #include <iostream>
                    #include <cstdlib> // for rand() and srand()
                    #include <ctime>   // for time()
                    
                    using namespace std;
                    
                    // Function to generate a random number between 'from' and 'to'
                    int RandomNumber(int from, int to) {
                        return rand() % (to - from + 1) + from;
                    }
                    
                    // Function to fill the matrix with random numbers
                    void FillMatrix(int Row, int Col, int arr[3][3]) {
                        for (int i = 0; i < Row; i++) {
                            for (int j = 0; j < Col; j++) {
                                arr[i][j] = RandomNumber(1, 100);
                            }
                        }
                    }
                    
                    // Function to print the matrix
                    void PrintMatrix(int Row, int Col, int arr[3][3]) {
                        cout << "The value of the matrix:" << endl;
                        for (int i = 0; i < Row; i++) {
                            for (int j = 0; j < Col; j++) {
                                cout << arr[i][j] << " ";
                            }
                            cout << endl; // Move to the next line after each row
                        }
                    }
                    
                    int main() {
                        srand(time(0)); // Seed the random number generator
                    
                        int arr[3][3];
                    
                        FillMatrix(3, 3, arr);
                        PrintMatrix(3, 3, arr);
                    
                        return 0;
                    }


## 76 Sum Matrix Row 


                    #include <iostream>
                    #include <cstdlib> // for rand() and srand()
                    #include <ctime>   // for time()
                    #include <vector>
                    using namespace std;
                    
                    // Function to generate a random number between 'from' and 'to'
                    int RandomNumber(int from, int to) {
                        return rand() % (to - from + 1) + from;
                    }
                    
                    // Function to fill the matrix with random numbers
                    void FillMatrix(int Row, int Col, int arr[3][3]) {
                        for (int i = 0; i < Row; i++) {
                            for (int j = 0; j < Col; j++) {
                                arr[i][j] = RandomNumber(1, 100);
                            }
                        }
                    }
                    
                    
                    // Function to calculate the sum of each row and store it in Vsum
                    void SumOfRow(int Row, int Col, int arr[3][3], vector<int>& Vsum) {
                        for (int i = 0; i < Row; i++) {
                            int sum = 0; // Initialize sum for each row
                            for (int j = 0; j < Col; j++) {
                                sum += arr[i][j];
                            }
                            Vsum.push_back(sum);
                        }
                    }
                    
                    // Function to print the sum of each row
                    void PrintSumOfRow(int Row, const vector<int>& Vsum) {
                        for (int x = 0; x < Row; x++) {
                            cout << "The Result of Row " << x << " is: " << Vsum[x] << endl;
                        }
                    }
                    
                    int main() {
                        srand((unsigned)time(NULL)); // Seed the random number generator
                    
                        int arr[3][3];
                        vector<int> Vsum;
                    
                        FillMatrix(3, 3, arr);
                    
                    
                        SumOfRow(3, 3, arr, Vsum);
                        PrintSumOfRow(3, Vsum);
                    
                        return 0;
                    }

## 77 Sum Colum of Matrix 

                    #include <iostream>
                    #include <cstdlib> // for rand() and srand()
                    #include <ctime>   // for time()
                    #include <vector>
                    using namespace std;
                    
                    // Function to generate a random number between 'from' and 'to'
                    int RandomNumber(int from, int to) {
                        return rand() % (to - from + 1) + from;
                    }
                    
                    // Function to fill the matrix with random numbers
                    void FillMatrix(int Row, int Col, int arr[3][3]) {
                        for (int i = 0; i < Row; i++) {
                            for (int j = 0; j < Col; j++) {
                                arr[i][j] = RandomNumber(1, 100);
                            }
                        }
                    }
                    
                    
                    // Function to calculate the sum of each row and store it in Vsum
                    void SumOfRow(int Row, int Col, int arr[3][3], vector<int>& Vsum) {
                        for (int i = 0; i < Row; i++) {
                            int sum = 0; // Initialize sum for each row
                            for (int j = 0; j < Col; j++) {
                                sum += arr[j][i];
                            }
                            Vsum.push_back(sum);
                        }
                    }
                    void PrintMatrix(int Row, int Col, int arr[3][3]) {
                        for (int i = 0; i < Row; i++) {
                            for (int j = 0; j < Col; j++) {
                               cout << arr[i][j] <<" ";
                            }
                            cout << endl;
                        }
                    }
                    // Function to print the sum of each row
                    void PrintSumOfRow(int Row, const vector<int>& Vsum) {
                        for (int x = 0; x < Row; x++) {
                            cout << "The Result of Cols " << x << " is: " << Vsum[x] << endl;
                        }
                    }
                    
                    int main() {
                        srand((unsigned)time(NULL)); // Seed the random number generator
                    
                        int arr[3][3];
                        vector<int> Vsum;
                    
                        FillMatrix(3, 3, arr);
                        PrintMatrix(3, 3, arr);
                        
                    
                        SumOfRow(3, 3, arr, Vsum);
                        PrintSumOfRow(3, Vsum);
                    
                        return 0;
                    }



## 78 Write a program to fill a 3*3 Matrix with ordered Numbers.

                    
                    #include <iostream>
                    #include <vector>
                    
                    using namespace std;
                    
                    // Function to fill the matrix with incremental numbers
                    void FillMatrix(int Row, int Col, int arr[3][3]) {
                        int counter = 0;
                        for (int i = 0; i < Row; i++) {
                            for (int j = 0; j < Col; j++) {
                                arr[i][j] = counter++;
                            }
                        }
                    }
                    
                    // Function to print the matrix
                    void PrintMatrix(int Row, int Col, int arr[3][3]) {
                        cout << "The value of the matrix:" << endl;
                        for (int i = 0; i < Row; i++) {
                            for (int j = 0; j < Col; j++) {
                                cout << arr[i][j] << " ";
                            }
                            cout << endl;
                        }
                    }
                    
                    int main() {
                        int arr[3][3];
                    
                        FillMatrix(3, 3, arr);
                        PrintMatrix(3, 3, arr);
                    
                        return 0;
                    }


## 79 transpose the matrix and print it 


                    #include <iostream>
                    #include <vector>
                    
                    using namespace std;
                    
                    // Function to fill the matrix with incremental numbers
                    void FillMatrix(int Row, int Col, int arr[3][3]) {
                        int counter = 1;
                        for (int i = 0; i < Row; i++) {
                            for (int j = 0; j < Col; j++) {
                                arr[i][j] = counter++;
                            }
                        }
                    }
                    void TransposeMatrix(int Row , int Col , int arr[3][3] , int arr2[3][3]) {
                        for (int i = 0; i < Row; i++) {
                            for (int j = 0; j < Col; j++) {
                                arr2[j][i] = arr[i][j];
                            }
                        }
                    }
                    // Function to print the matrix
                    void PrintMatrix(int Row, int Col, int arr[3][3]) {
                        cout << "The value of the matrix:" << endl;
                        for (int i = 0; i < Row; i++) {
                            for (int j = 0; j < Col; j++) {
                                cout << arr[i][j] << " ";
                            }
                            cout << endl;
                        }
                    }
                    void PrintTransposeMatrix(int Row, int Col, int arr2[3][3]) {
                        cout << "The value of the TransposeMatrix:" << endl;
                        for (int i = 0; i < Row; i++) {
                            for (int j = 0; j < Col; j++) {
                                cout << arr2[i][j] << " ";
                            }
                            cout << endl;
                        }
                    }
                    
                    
                    int main() {
                        int arr[3][3] , arr2[3][3];
                    
                        FillMatrix(3, 3, arr);
                        PrintMatrix(3, 3, arr);
                    
                        TransposeMatrix(3, 3, arr, arr2);
                        PrintTransposeMatrix(3, 3, arr2);
                    
                        return 0;
                    }


## 80 Print First Letter in The Word 

                    #include <iostream>  
                    #include <vector>
                    #include <string>
                    
                    using namespace std;
                    
                    
                    string ReadString() {
                        string  Name;
                        cout << "Please Eneter Your Name : ";
                        getline(cin, Name);
                        return Name;
                    
                    }
                    
                    void PrintFirsLetter(string S1) {
                         S1 = ReadString();
                        
                         cout << S1[0] << endl;
                        for (int i = 0; i < S1.length(); i++) {
                    
                    
                            if (S1[i] == ' ') {
                                ++i;
                                cout << S1[i] << endl;
                            }
                        }
                    }
                    int main() {
                        
                        string S1;
                        PrintFirsLetter(S1);
                        return 0;
                    }


## 81 Print First Letter in The Word 

                    #include <iostream>  
                    #include <vector>
                    #include <string>
                    
                    using namespace std;
                    
                    
                    string ReadString() {
                        string  Name;
                        cout << "Please Eneter Your Name : ";
                        getline(cin, Name);
                        return Name;
                    
                    }
                    
                    void PrintFirsLetter(string S) {
                        bool isFirstLetter = true;
                    
                        for (short i = 0; i < S.length(); i++) {
                            if ( S[i] != ' '  && isFirstLetter) {
                                cout << S[i] << endl;
                            }
                            isFirstLetter = (S[i] == ' ' ? true : false);
                        }
                    }
                    int main() {
                        
                        PrintFirsLetter(ReadString());
                        return 0;
                    }

## 82 Convert the first letter to a Capital letter

                    #include <iostream>  
                    #include <vector>
                    #include <string>
                    
                    using namespace std;
                    
                    
                    string ReadString() {
                        string  Name;
                        cout << "Please Eneter Your Name : ";
                        getline(cin, Name);
                        return Name;
                    
                    }
                    
                    string PrintFirsLetter(string S) {
                        bool isFirstLetter = true;
                    
                        for (short i = 0; i < S.length(); i++) {
                            if ( S[i] != ' '  && isFirstLetter) {
                                S[i] = toupper(S[i]);
                            }
                            isFirstLetter = (S[i] == ' ' ? true : false);
                        }
                        return S;
                    }
                    int main() {
                        
                        string S = ReadString();
                       
                        S =  PrintFirsLetter(S);
                    
                        cout << S << endl;
                    
                        return 0;
                    }

## 83  Convert the first letter to a Lower letter


                    #include <iostream>  
                    #include <vector>
                    #include <string>
                    
                    using namespace std;
                    
                    
                    string ReadString() {
                        string  Name;
                        cout << "Please Eneter Your Name : ";
                        getline(cin, Name);
                        return Name;
                    
                    }
                    
                    string PrintFirsLetter(string S) {
                        bool isFirstLetter = true;
                    
                        for (short i = 0; i < S.length(); i++) {
                            if ( S[i] != ' '  && isFirstLetter) {
                                S[i] = tolower(S[i]);
                            }
                            isFirstLetter = (S[i] == ' ' ? true : false);
                        }
                        return S;
                    }
                    int main() {
                        
                        string S = ReadString();
                       
                        S =  PrintFirsLetter(S);
                    
                        cout << S << endl;
                    
                        return 0;
                    }

## 84 if word capital converts to small and Same thing in reverse


                    #include <iostream>
                    #include <string>
                    
                    using namespace std;
                    
                    string ReadString() {
                        string Name;
                        cout << "Please Enter Your Name: ";
                        getline(cin, Name);
                        return Name;
                    }
                    
                    string PrintUpperWord(string S) {
                        for (short i = 0; i < S.length(); i++) {
                            S[i] = toupper(S[i]);
                        }
                        return S;
                    }
                    
                    string PrintLowerWord(string S) {
                        for (short i = 0; i < S.length(); i++) {
                            S[i] = tolower(S[i]);
                        }
                        return S;
                    }
                    
                    int main() {
                    
                        string S = ReadString();
                    
                        string a = PrintUpperWord(S);
                        cout << "The upper name: " << a << endl;
                    
                        string b = PrintLowerWord(S);
                        cout << "The lower name: " << b << endl;
                    
                        return 0;
                    }

## 85 Invert all letter case 


                    #include <iostream>
                    #include <string>
                    #include <string>
                    using namespace std;
                    
                    
                    string ReadWord() {
                        
                        string name;
                        cout << "Please enter your name:";
                        getline(cin, name);
                        return name;
                    
                    }
                    
                    string ConvertLetter(string S) {
                    
                        for (int i = 0; i < S.length(); i++) {
                            if (isupper(S[i])) {
                                 S[i] = tolower(S[i]);
                            }
                            else 
                            {
                                S[i] = toupper(S[i]);
                            }
                        }
                        return S;
                    }
                    
                    int main() {
                    
                         string S = ReadWord();
                    
                         S = ConvertLetter(S);
                    
                        cout <<"Convert Word is: \n" << S << endl;
                    
                        return 0;
                    }


## 86 program counts all letters in the word 

                    #include <iostream>
                    #include <string>
                    #include <string>
                    using namespace std;
                    
                    
                    string ReadWord() {
                        
                        string name;
                        cout << "Please enter your name:";
                        getline(cin, name);
                        return name;
                    
                    }
                    
                    void countAllLetter(string S) {
                    
                        int counter = 0 , counter2 = 0 , counter3 = 0;
                       
                    
                        for (int i = 0; i < S.length(); i++) {
                            if (isupper(S[i])) {
                                counter2++;
                            }
                            else 
                            {
                                counter3++;
                            }
                    
                            counter++;
                        }
                        cout << "string Length = " << counter<< endl;
                        cout << "Capital letters = " << counter2 << endl;
                        cout << "Small Letters = " << counter3 << endl;
                    }
                    
                    int main() {
                    
                        countAllLetter(ReadWord());
                    
                        return 0;
                    }

## 87  How much Char Repeated 

                    
                    #include <iostream>
                    #include <string>
                    #include <string>
                    using namespace std;
                    
                    
                    string ReadWord() {
                        
                        string name;
                        cout << "Please enter your name:";
                        getline(cin, name);
                        return name;
                    
                    }
                    
                    void countAllLetter(string S) {
                    
                        int counter = 0;
                    
                        for (int i = 0; i < S.length(); i++) {
                            if (S[i] == 'M' || S[i] == 'm') {
                                counter++;
                            }
                        }
                        cout << "the char repeated  " << counter << " times";
                    }
                    int main() {
                    
                        countAllLetter(ReadWord());
                    
                        return 0;
                    }

## 88  program counts how many letters repeated in a word :-

                    #include <iostream>
                    #include <string>
                    using namespace std;
                    
                    string ReadWord() {
                        string name;
                        cout << "Please enter your name: ";
                        getline(cin, name);
                        return name;
                    }
                    
                    char ReadChar() {
                        char char1;
                        cout << "Please enter the letter: ";
                        cin >> char1;
                        return char1;
                    }
                    
                    short CountLetter(string S, char char1, bool MatchCase = true) {
                        short counter = 0;
                    
                        for (short i = 0; i < S.length(); i++) {
                            if (MatchCase) {
                                if (S[i] == char1)
                                    counter++;
                            }
                            else {
                                if (tolower(S[i]) == tolower(char1))
                                    counter++;
                            }
                        }
                    
                        return counter;
                    }
                    
                    int main() {
                        string s = ReadWord();
                        char c = ReadChar();
                    
                        short count = CountLetter(s, c);
                        cout << "The letter repeats " << count << " times (case-sensitive)" << endl;
                    
                        count = CountLetter(s, c, false);
                        cout << "The letter repeats " << count << " times (case-insensitive)" << endl;
                    
                        return 0;
                    }

## 89 program Check if the letter is a vowel or not 


                    #include <iostream>
                    #include <string>
                    using namespace std;
                    
                    char ReadChar() {
                        char char1;
                        cout << "Please enter the letter: ";
                        cin >> char1;
                        return char1;
                    }
                    
                    bool IsVowel(char char1) {
                    
                        char1 = tolower(char1);
                    
                        return ((char1 == 'a') || (char1 == 'o') || (char1 == 'u') || (char1 == 'e') || (char1 == 'i'));
                    
                    }
                    
                    int main() {
                    
                        char Ch1 = ReadChar(); 
                    
                        if (IsVowel(Ch1))    
                            cout << "\nYES Letter \'" << Ch1 << "\' is vowel";
                        else      
                            cout << "\nNO Letter \'" << Ch1 << "\' is NOT vowel";
                    
                        return 0;
                    }
## 90 program counts how many vowel letters repeated in a word 

                    #include <iostream>
                    #include <string>
                    using namespace std;
                    string ReadString() {
                        string name;
                        cout << "Please enter your name ";
                        getline(cin, name);
                        return name;
                    }
                    bool IsVowel(char char1) {
                    
                        char1 = tolower(char1);
                    
                        return ((char1 == 'a') || (char1 == 'o') || (char1 == 'u') || (char1 == 'e') || (char1 == 'i'));
                    
                    }
                    short CountVowel(string s ) {
                    
                        short counter = 0;
                        for (short i = 0; i < s.length(); i++) {
                            if (IsVowel(s[i]))
                                counter++;
                        }
                        return counter;
                    }
                    
                    int main() {
                    
                        string s = ReadString();
                    
                        short a = CountVowel(s);
                    
                        cout << "The count of vowel letter is " << a;
                    
                        return 0;
                    }


## 91  Print Vowel letter 

                    #include <iostream>
                    #include <string>
                    using namespace std;
                    string ReadString() {
                        string name;
                        cout << "Please enter your name ";
                        getline(cin, name);
                        return name;
                    }
                    bool IsVowel(char char1) {
                    
                        char1 = tolower(char1);
                    
                        return ((char1 == 'a') || (char1 == 'o') || (char1 == 'u') || (char1 == 'e') || (char1 == 'i'));
                    
                    }
                    void PrintVowel(string s ) {
                    
                    
                        for (short i = 0; i < s.length(); i++) {
                            if (!IsVowel(s[i]))
                                cout << " ";
                            else
                                cout << s[i];
                        }
                       
                    }
                    
                    int main() {
                    
                        PrintVowel(ReadString());
                    
                        return 0;
                    }

## 92 program prints Each word 


                              #include <iostream>
                              #include <string>
                              #include <vector>
                              
                              using namespace std;
                              string ReadString() {
                                  string name;
                                  cout << "Please enter your name ";
                                  getline(cin, name);
                                  return name;
                              }
                              
                              void PrintEachWord(string s ) {

                        string delim = " ";
                        short pos = 0;
                        string sWrod;
                    
                        cout << "the string words is: \n\n";
                    
                        while ((pos = s.find(delim)) != std::string::npos) {
                    
                                sWrod = s.substr(0, pos);
                                if (sWrod != " ") {
                                    cout << sWrod << endl;
                                }
                                s.erase(0, pos + delim.length());
                        }
                    
                                if (s != " ") {
                                    cout << s << endl;
                                 }
                       
                    }
                    
                    int main() {
                    
                        PrintEachWord(ReadString());
                    
                        return 0;
                    }

## 93 program reads string and counts each word in the string 


                    #include <iostream>
                    #include <string>
                    #include <vector>
                    
                    using namespace std;
                    string ReadString() {
                        string name;
                        cout << "Please enter your name ";
                        getline(cin, name);
                        return name;
                    }
                    
                    short PrintEachWord(string s ) {
                    
                        string delim = " ";
                        short pos = 0;
                        string sWrod;
                        short counter = 0;
                    
                        cout << "the string words is: \n\n";
                    
                        while ((pos = s.find(delim)) != std::string::npos) {
                    
                                sWrod = s.substr(0, pos);
                                if (sWrod != " ") {
                                    counter++;
                                }
                                s.erase(0, pos + delim.length());
                        }
                        if (s != " ") 
                        {
                            counter++;
                    
                        }
                    
                        return counter;
                       
                    }
                    
                    int main() {
                    
                        
                       short s =  PrintEachWord(ReadString());
                    
                       cout << "The number of word in string is :" << s << endl;
                    
                    
                        return 0;
                    }
## 94 Splitting function 


                    #include <iostream>
                    #include <string>
                    #include <vector>
                    
                    using namespace std;
                    string ReadString() {
                        string name;
                        cout << "Please enter your name ";
                        getline(cin, name);
                        return name;
                    }
                    
                    vector <string> SplitString(string s, string delim) {
                    
                        short pos = 0;
                        string sWrod;
                        vector <string> Vstring;
                    
                        while ((pos = s.find(delim)) != std::string::npos) {
                    
                            sWrod = s.substr(0, pos);
                            if (sWrod != " ") {
                    
                                Vstring.push_back(sWrod);
                            }
                            s.erase(0, pos + delim.length());
                        }
                    
                        return  Vstring;
                    
                    }
                    
                    
                    int main() {
                    
                       vector <string> Vstring =  SplitString(ReadString(), " ");
                    
                       cout << "the number of word is " << Vstring.size() << endl;
                    
                       for (string& s : Vstring) {
                           cout << s << endl;
                       }
                    
                    
                        return 0;
                    }

## 95  TrimLeft TrimRight TrimAll String 


                    #include <iostream>
                    #include <string>
                    #include <vector>
                    
                    using namespace std;
                    
                    
                    string TrimLeft(string s ) {
                        
                        for (short i = 0; i < s.length(); i++) {
                            if (s[i] != ' ') {
                                return  s.substr(i, s.length() - i);
                            }
                       }
                        return "";
                    }
                    string TrimRight(string s ) {
                        
                        for (short i = s.length(); i >= 0 ; i--) {
                            if (s[i] != ' ') {
                                return  s.substr(0, i+1);
                            }
                       }
                        return "";
                    }
                    
                    string Trim(string s) {
                        return TrimRight(TrimLeft(s));
                    }
                    
                    
                    
                    int main() {
                    
                        
                        string word = "     muustafa saad  ";
                    
                       
                        cout << "Right = " << TrimRight(word) << endl;
                    
                        cout << "left  = "<< TrimLeft(word) << endl;
                    
                    
                        cout << "All = " << Trim(word) << endl;
                    
                    
                        return 0;
                    }


## 96 program to join string 

                    #include <iostream>
                    #include <string>
                    #include <vector>
                    
                    using namespace std;
                    
                    string ALlString(vector <string> Vstring , string delim ) {
                    
                        string Result;
                        for (string& word : Vstring) {
                    
                            Result = Result + word + delim ;
                        }
                        return Result.substr(0,Result.length()-delim.length());
                    }
                    int main() {
                    
                        
                        vector <string> Vstring = { "Mohammed " , "Faid" , "Ali" , "Maher" };
                    
                        cout << "words after join : " << endl;
                        cout << ALlString(Vstring ," ");
                    
                        return 0;
                    }

## 97 join string and Reverse string 

                    #include <iostream>
                    #include <string>
                    #include <vector>
                    
                    using namespace std;
                    
                    string Readstring() {
                        string name;
                        cout << "Please enter your name" << endl;
                        getline(cin, name);
                        return name;
                    }
                    
                    vector<string> LoadString(string s, vector<string>& Vstring, string delim) {
                        size_t pos = 0;
                        string word;
                    
                        while ((pos = s.find(delim)) != string::npos) {
                            word = s.substr(0, pos);
                            if (!word.empty() && word != " ") {
                                Vstring.push_back(word);
                            }
                            s.erase(0, pos + delim.length());
                        }
                        if (!s.empty() && s != " ") {
                            Vstring.push_back(s);
                        }
                    
                        return Vstring;
                    }
                    
                    void ReverseString(vector <string> Vstring) {
                    
                        cout << "the Reverse word is :";
                    
                        for (short i = Vstring.size() - 1; i >= 0; i--) {
                            cout << Vstring[i] + " ";
                        }
                    }
                    
                    int main() {
                        vector<string> Vstring;
                        string inputString = Readstring();
                        LoadString(inputString, Vstring, " ");
                        ReverseString(Vstring);
                    
                        return 0;
                    }

## 98 Replace string 

                    
                    #include <iostream>
                    #include <string>
                    #include <vector>
                    
                    using namespace std;
                    
                    string Readstring() {
                        string name;
                        cout << "Please enter your name" << endl;
                        getline(cin, name);
                        return name;
                    }
                    
                    string ReplaceWord(string s, string r, string rto) {
                        short pos = s.find(r);
                    
                        while(pos != std::string::npos) {
                    
                            s = s.replace(pos, r.length(), rto);
                            pos = s.find(r);
                        }
                        return s;
                    }
                    
                    int main() {
                        string s = Readstring();
                        string r = "Egypt", r2 = "USA";
                    
                        cout << ReplaceWord(s, r, r2);
                    
                        
                        
                    
                        return 0;
                    }


## 99 Remove Punctuations 

                    #include <iostream>
                    #include <string>
                    #include <vector>
                    
                    using namespace std;
                    
                    string Readstring() {
                        string name;
                        cout << "Please enter your name" << endl;
                        getline(cin, name);
                        return name;
                    }
                    string RemovePunctuations(string s) {
                    
                        string S2 = " ";
                    
                        for (short i = 0; i < s.length() - 1; i++) {
                            if (!ispunct(s[i])) {
                                S2 += s[i] ;
                            }
                        }
                        return S2;
                    }
                    
                    
                    int main() {
                    
                      
                    
                        cout << "string after remove \n " << RemovePunctuations(Readstring());
                    
                        return 0;
                    }


## 100 program converts string to record 

                    #include <iostream>
                    #include <string>
                    #include <vector>
                    
                    using namespace std;
                    
                    struct stClient {
                    
                        string Name, AccountNumber, Phone, PinCode;
                        double AccountBalance ;
                    
                    };
                    stClient  ReadClinet() {
                    
                        stClient Client;
                      
                        cout << "Please enter your name" << endl;
                        getline(cin, Client.Name);
                    
                        cout << "Please enter Account Number " << endl;
                        cin >> Client.AccountNumber; 
                    
                        cout << "Please enter Account Balance " << endl;
                        cin >> Client.AccountBalance;
                    
                        cout << "Please enter Phone " << endl;
                        cin >> Client.Phone;
                    
                        cout << "Please enter Pin Code " << endl;
                        cin >> Client.PinCode;
                    
                        return  Client;
                    }
                    string ConvertRecord(stClient Client, string Sperator = "###") {
                    
                        string stClientRecord = " ";
                    
                        stClientRecord += Client.Name + Sperator;
                        stClientRecord += Client.AccountNumber + Sperator;
                        stClientRecord += Client.Phone + Sperator;
                        stClientRecord += Client.PinCode + Sperator;
                        stClientRecord += to_string( Client.AccountBalance) ;
                    
                        return stClientRecord;
                    }
                    
                    int main() {
                    
                        stClient Client = ReadClinet();
                    
                        cout << "the Record " << endl;
                    
                        cout << ConvertRecord(Client);
                    
                        return 0;
                    }

## 101 




