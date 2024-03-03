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
## 24 - 




