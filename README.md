# Problem_Solving

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

## 101 Convert line to Record 

                    #include <iostream>
                    #include <string>
                    #include <vector>
                    
                    using namespace std;
                    
                    struct stClient {
                        string Name, AccountNumber, Phone, PinCode;
                        double AccountBalance;
                    };
                    
                    vector<string> SplitString(const string& s, const string& delim = "##") {
                        size_t pos = 0, start = 0;
                        vector<string> Vstring;
                        string token;
                        string temp = s; // Create a copy of the string to manipulate
                    
                        while ((pos = temp.find(delim, start)) != string::npos) {
                            token = temp.substr(start, pos - start);
                            if (!token.empty()) {
                                Vstring.push_back(token);
                            }
                            start = pos + delim.length();
                        }
                    
                        // Add the last token
                        token = temp.substr(start);
                        if (!token.empty()) {
                            Vstring.push_back(token);
                        }
                    
                        return Vstring;
                    }
                    
                    stClient ConvertClientToRecord(const vector<string>& Vstring) {
                        stClient Client;
                    
                        if (Vstring.size() == 5) {
                            Client.PinCode = Vstring[0];
                            Client.AccountNumber = Vstring[1];
                            Client.Name = Vstring[2];
                            Client.Phone = Vstring[3];
                            Client.AccountBalance = stod(Vstring[4]);
                        }
                        else {
                            cerr << "Invalid input data!" << endl;
                        }
                    
                        return Client;
                    }
                    
                    void Print(const stClient& Client) {
                        cout << "The Record is:" << endl;
                        cout << "Name: " << Client.Name << endl;
                        cout << "Account Number: " << Client.AccountNumber << endl;
                        cout << "Phone: " << Client.Phone << endl;
                        cout << "Pin Code: " << Client.PinCode << endl;
                        cout << "Account Balance: " << Client.AccountBalance << endl;
                    }
                    
                    int main() {
                        string stringClient = "A150##1234##Mustafa Saad##08987894##5270.0000";
                    
                        vector<string> Vstring = SplitString(stringClient);
                        stClient Client = ConvertClientToRecord(Vstring);
                    
                        Print(Client);
                    
                        return 0;
                    }

## 102 Read Clients and Save them in a file 

                    #include <iostream>
                    #include <string>
                    #include <vector>
                    #include <fstream>
                    
                    using namespace std;
                    
                    const string ClientFileName = "MyFile.txt";
                    
                    struct stClient {
                    
                        string Name, AccountNumber, Phone, PinCode;
                        double AccountBalance;
                    
                    };
                    stClient  ReadClinet() {
                    
                        stClient Client;
                        
                            cout << "Please enter your name" << endl;
                            getline(cin >> ws , Client.Name);
                    
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
                    string  ConvertRecordToLine(stClient Client , string sperator = "#||#") {
                    
                        string S2 = " ";
                    
                        S2 += to_string(Client.AccountBalance) + sperator;
                        S2 += Client.AccountNumber + sperator; 
                        S2 += Client.Name + sperator;
                        S2 += Client.Phone + sperator;
                        S2 += Client.PinCode + sperator;
                    
                        return S2;
                    }
                    
                    void  AddDatatLineToFile(string FileName , string stDataLine) {
                        
                        fstream MyFile;
                        MyFile.open(FileName, ios::out | ios::app); // write mode
                        
                        if (MyFile.is_open())
                        {
                            MyFile << stDataLine << endl;
                            MyFile.close();
                        }
                    }
                    void AddNewClient() {
                        stClient Client;
                    
                        Client = ReadClinet(); 
                        AddDatatLineToFile(ClientFileName , ConvertRecordToLine(Client));
                    
                    }
                    void AddClients() {
                        char AddMore = 'Y';
                        do
                        {
                            cout << "Adding New Client \n";
                    
                            AddNewClient();
                    
                            cout << "\n client added successfuly , do you want to add more clients ? Y/n";
                            cin >> AddMore; 
                        } while (toupper(AddMore) == 'Y');
                    }
                    int main() {
                    
                        AddClients();
                    
                        return 0;
                    } 


## 103 read a line from file 

                    
                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    #include<iomanip>
                    
                    using namespace std;
                    
                    const string ClientsFileName = "Clients.txt";
                    
                    struct  sClient{
                    	string AccountNumber; 
                    	string PinCode;
                    	string Name;
                    	string Phone;
                    	double AccountBalance;
                    }; 
                    
                    vector<string> SplitString(string S1, string Delim)
                    {
                    	vector<string> vString; 
                    	short pos = 0;
                    	string sWord; 
                    
                        while ((pos = S1.find(Delim)) != std::string::npos)  
                    	{      
                    		sWord = S1.substr(0, pos);
                    	  if (sWord != "")     
                    	  { 
                    		  vString.push_back(sWord); 
                    	  }
                    	  S1.erase(0, pos + Delim.length());
                    	}
                    	if (S1 != "") 
                    	{     
                    		vString.push_back(S1); 
                    	}
                    	return vString; 
                    } 
                    
                    sClient ConvertLinetoRecord(string Line, string Seperator = "#//#") 
                    {
                    	sClient Client;
                    	vector<string> vClientData;   
                    	vClientData = SplitString(Line, Seperator);  
                    	Client.AccountNumber = vClientData[0];  
                    	Client.PinCode = vClientData[1];  
                    	Client.Name = vClientData[2];  
                    	Client.Phone = vClientData[3];  
                    	Client.AccountBalance = stod(vClientData[4]);
                    
                    }
                    vector <sClient> LoadCleintsDataFromFile(string FileName)
                    {
                    	vector <sClient> vClients;
                    	fstream MyFile; 
                    	MyFile.open(FileName, ios::in);
                    	if (MyFile.is_open())  
                    	{
                    		string Line; 
                    		sClient Client;
                    
                    		while (getline(MyFile, Line))   
                    		{  
                    			Client = ConvertLinetoRecord(Line);  
                    			vClients.push_back(Client);      
                    		}         MyFile.close();   
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
                    	 void PrintAllClientsData(vector <sClient> vClients)
                    	 {
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
                    		 for (sClient Client : vClients) { PrintClientRecord(Client);   
                    		 cout << endl; }  
                    		 cout << "\n_______________________________________________________";   
                    		 cout << "_________________________________________\n" << endl;
                    	 
                    	 }
                    
                    	int main() {
                    
                    		vector <sClient> vClients = LoadCleintsDataFromFile(ClientsFileName);
                    
                    		PrintAllClientsData(vClients);  
                    
                    		system("pause>0");
                    
                    		return 0;
                    	}
                    
                    
                    
## 104 Find Client Information  By Account Number in file 


                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    #include<iomanip>
                    using namespace std;
                    const string ClientsFileName = "Clients.txt";
                    struct sClient{
                    	string AccountNumber;
                    	string PinCode;
                    	string Name; 
                    	string Phone;
                    	double AccountBalance;
                    }; 
                    vector<string> SplitString(string S1, string Delim)
                    { 
                    	vector<string> vString;
                    	short pos = 0;
                     string sWord; 
                     while ((pos = S1.find(Delim)) != std::string::npos)  
                     {       
                    	 sWord = S1.substr(0, pos); 
                    	 if (sWord != "")         { 
                    		 vString.push_back(sWord);  
                    	 } 
                    	 S1.erase(0, pos + Delim.length()); 
                     } 
                     if (S1 != "")  
                     {     
                    	 vString.push_back(S1); 
                     }
                     return vString; 
                    } 
                    sClient ConvertLinetoRecord(string Line, string Seperator = "#//#")
                    {
                    	sClient Client;
                    	vector<string> vClientData;   
                    	vClientData = SplitString(Line, Seperator);   
                    	Client.AccountNumber = vClientData[0]; 
                    	Client.PinCode = vClientData[1]; 
                    	Client.Name = vClientData[2];  
                    	Client.Phone = vClientData[3]; 
                    	Client.AccountBalance = stod(vClientData[4]);
                    	return Client;
                    }
                    vector <sClient> LoadCleintsDataFromFile(string FileName)
                    { 
                    	vector <sClient> vClients;
                    	fstream MyFile;   
                    	MyFile.open(FileName, ios::in);
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
                    	  void PrintClientCard(sClient Client) 
                    	  {
                    		  cout << "\nThe following are the client details:\n";  
                    		  cout << "\nAccout Number: " << Client.AccountNumber; 
                    		  cout << "\nPin Code     : " << Client.PinCode;  
                    		  cout << "\nName         : " << Client.Name;  
                    		  cout << "\nPhone        : " << Client.Phone;  
                    		  cout << "\nAccount Balance: " << Client.AccountBalance;
                    	  }
                    	  bool FindClientByAccountNumber(string AccountNumber, sClient & Client)
                    	  {
                    		  vector <sClient> vClients = LoadCleintsDataFromFile(ClientsFileName);
                    		  for (sClient C : vClients) 
                    		  { 
                    			  if (C.AccountNumber == AccountNumber)
                    			  {
                    				  Client = C; return true;
                    			  }
                    		  }
                    		  return false; 
                    	  } 
                    	  string ReadClientAccountNumber() {
                    		  string AccountNumber = ""; 
                    		  cout << "\nPlease enter AccountNumber? "; 
                    		  cin >> AccountNumber;
                    		  return AccountNumber;
                    	  }
                    	  int main() { 
                    
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


##. 105 Delete Client from File 


                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    const string ClientsFileName = "Clients.txt";
                    
                    struct sClient {
                        string AccountNumber;
                        string PinCode;
                        string Name;
                        string Phone;
                        double AccountBalance;
                        bool MarkForDelete = false;
                    };
                    
                    vector<string> SplitString(const string& S1, const string& Delim) {
                        vector<string> vString;
                        size_t pos = 0, start = 0;
                        string sWord;
                    
                        while ((pos = S1.find(Delim, start)) != string::npos) {
                            sWord = S1.substr(start, pos - start);
                            if (!sWord.empty()) {
                                vString.push_back(sWord);
                            }
                            start = pos + Delim.length();
                        }
                        sWord = S1.substr(start);
                        if (!sWord.empty()) {
                            vString.push_back(sWord);
                        }
                        return vString;
                    }
                    
                    sClient ConvertLinetoRecord(const string& Line, const string& Seperator = "#||#") {
                        sClient Client;
                        vector<string> vClientData = SplitString(Line, Seperator);
                    
                        if (vClientData.size() == 5) {
                            Client.AccountNumber = vClientData[0];
                            Client.PinCode = vClientData[1];
                            Client.Name = vClientData[2];
                            Client.Phone = vClientData[3];
                            Client.AccountBalance = stod(vClientData[4]);
                        }
                        return Client;
                    }
                    
                    string ConvertRecordToLine(const sClient& Client, const string& sper = "#||#") {
                        string s = "";
                        s += Client.AccountNumber + sper;
                        s += Client.PinCode + sper;
                        s += Client.Name + sper;
                        s += Client.Phone + sper;
                        s += to_string(Client.AccountBalance);
                        return s;
                    }
                    
                    vector<sClient> LoadClientsDataFromFile(const string& FileName) {
                        vector<sClient> vClients;
                        ifstream MyFile(FileName);
                        if (MyFile.is_open()) {
                            string Line;
                            while (getline(MyFile, Line)) {
                                sClient Client = ConvertLinetoRecord(Line);
                                vClients.push_back(Client);
                            }
                            MyFile.close();
                        }
                        return vClients;
                    }
                    
                    void SaveClientsDataToFile(const string& FileName, const vector<sClient>& vClients) {
                        ofstream MyFile(FileName, ios::out);
                        if (MyFile.is_open()) {
                            for (const sClient& Client : vClients) {
                                if (!Client.MarkForDelete) {
                                    MyFile << ConvertRecordToLine(Client) << endl;
                                }
                            }
                            MyFile.close();
                        }
                    }
                    
                    void PrintClientCard(const sClient& Client) {
                        cout << "\nThe following are the client details:\n";
                        cout << "Account Number: " << Client.AccountNumber << "\n";
                        cout << "Pin Code      : " << Client.PinCode << "\n";
                        cout << "Name          : " << Client.Name << "\n";
                        cout << "Phone         : " << Client.Phone << "\n";
                        cout << "Account Balance: " << Client.AccountBalance << "\n";
                    }
                    
                    bool FindClientByAccountNumber(const string& AccountNumber, const vector<sClient>& vClients, sClient& Client) {
                        for (const sClient& C : vClients) {
                            if (C.AccountNumber == AccountNumber) {
                                Client = C;
                                return true;
                            }
                        }
                        return false;
                    }
                    
                    string ReadClientAccountNumber() {
                        string AccountNumber;
                        cout << "\nPlease enter Account Number: ";
                        cin >> AccountNumber;
                        return AccountNumber;
                    }
                    
                    bool MarkClientForDeleteByAccountNumber(const string& AccountNumber, vector<sClient>& vClients) {
                        for (sClient& c : vClients) {
                            if (c.AccountNumber == AccountNumber) {
                                c.MarkForDelete = true;
                                return true;
                            }
                        }
                        return false;
                    }
                    
                    bool DeleteClientByAccountNumber(const string& AccountNumber, vector<sClient>& vClients) {
                        sClient Client;
                        char Answer = 'n';
                    
                        if (FindClientByAccountNumber(AccountNumber, vClients, Client)) {
                            PrintClientCard(Client);
                    
                            cout << "\n\nDo you want to delete your account? (y/n): ";
                            cin >> Answer;
                    
                            if (Answer == 'Y' || Answer == 'y') {
                                MarkClientForDeleteByAccountNumber(AccountNumber, vClients);
                                SaveClientsDataToFile(ClientsFileName, vClients);
                    
                                vClients = LoadClientsDataFromFile(ClientsFileName);
                                cout << "\n\nClient deleted successfully.";
                                return true;
                            }
                        }
                        else {
                            cout << "\nClient with Account Number (" << AccountNumber << ") is not found!";
                        }
                        return false;
                    }
                    
                    int main() {
                        vector<sClient> vClients = LoadClientsDataFromFile(ClientsFileName);
                        string AccountNumber = ReadClientAccountNumber();
                        DeleteClientByAccountNumber(AccountNumber, vClients);
                        return 0;
                               }

## .106  Update client by account number in the file 


                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    const string ClientsFileName = "Clients.txt";
                    
                    struct sClient {
                        string AccountNumber;
                        string PinCode;
                        string Name;
                        string Phone;
                        double AccountBalance;
                        bool MarkForDelete = false;
                    };
                    
                    vector<string> SplitString(const string& S1, const string& Delim) {
                        vector<string> vString;
                        size_t pos = 0, start = 0;
                        string sWord;
                    
                        while ((pos = S1.find(Delim, start)) != string::npos) {
                            sWord = S1.substr(start, pos - start);
                            if (!sWord.empty()) {
                                vString.push_back(sWord);
                            }
                            start = pos + Delim.length();
                        }
                        sWord = S1.substr(start);
                        if (!sWord.empty()) {
                            vString.push_back(sWord);
                        }
                        return vString;
                    }
                    
                    sClient ConvertLinetoRecord(const string& Line, const string& Seperator = "#||#") {
                        sClient Client;
                        vector<string> vClientData = SplitString(Line, Seperator);
                    
                        if (vClientData.size() == 5) {
                            Client.AccountNumber = vClientData[0];
                            Client.PinCode = vClientData[1];
                            Client.Name = vClientData[2];
                            Client.Phone = vClientData[3];
                            Client.AccountBalance = stod(vClientData[4]);
                        }
                        return Client;
                    }
                    
                    string ConvertRecordToLine(const sClient& Client, const string& sper = "#||#") {
                        string s = "";
                        s += Client.AccountNumber + sper;
                        s += Client.PinCode + sper;
                        s += Client.Name + sper;
                        s += Client.Phone + sper;
                        s += to_string(Client.AccountBalance);
                        return s;
                    }
                    
                    vector<sClient> LoadClientsDataFromFile(const string& FileName) {
                        vector<sClient> vClients;
                        ifstream MyFile(FileName);
                        if (MyFile.is_open()) {
                            string Line;
                            while (getline(MyFile, Line)) {
                                sClient Client = ConvertLinetoRecord(Line);
                                vClients.push_back(Client);
                            }
                            MyFile.close();
                        }
                        return vClients;
                    }
                    
                    void SaveClientsDataToFile(const string& FileName, const vector<sClient>& vClients) {
                        ofstream MyFile(FileName, ios::out);
                        if (MyFile.is_open()) {
                            for (const sClient& Client : vClients) {
                                if (!Client.MarkForDelete) {
                                    MyFile << ConvertRecordToLine(Client) << endl;
                                }
                            }
                            MyFile.close();
                        }
                    }
                    
                    void PrintClientCard(const sClient& Client) {
                        cout << "\nThe following are the client details:\n";
                        cout << "Account Number: " << Client.AccountNumber << "\n";
                        cout << "Pin Code      : " << Client.PinCode << "\n";
                        cout << "Name          : " << Client.Name << "\n";
                        cout << "Phone         : " << Client.Phone << "\n";
                        cout << "Account Balance: " << Client.AccountBalance << "\n";
                    }
                    
                    bool FindClientByAccountNumber(const string& AccountNumber, const vector<sClient>& vClients, sClient& Client) {
                        for (const sClient& C : vClients) {
                            if (C.AccountNumber == AccountNumber) {
                                Client = C;
                                return true;
                            }
                        }
                        return false;
                    }
                    
                    string ReadClientAccountNumber() {
                        string AccountNumber;
                        cout << "\nPlease enter Account Number: ";
                        cin >> AccountNumber;
                        return AccountNumber;
                    }
                    
                    void  UpdateClient(const string& AccountNumber, vector<sClient>& vClients) {
                        for (sClient& c : vClients) {
                            if (c.AccountNumber == AccountNumber) {
                                cout << "Enter pin code?";
                                getline(cin >> ws , c.PinCode);
                                cout << "Enter Name?";
                                getline(cin , c.Name);
                                cout << "Enter Phone?";
                                getline(cin, c.Phone);
                                cout << "Enter Account Banlace?";
                                cin >> c.AccountBalance;
                    
                                cout << "\nClient Update Successfully.";
                            }
                        }
                        
                    }
                    
                    bool UpdateAccount(const string& AccountNumber, vector<sClient>& vClients) {
                        sClient Client;
                        char Answer = 'n';
                    
                        if (FindClientByAccountNumber(AccountNumber, vClients, Client)) {
                            PrintClientCard(Client);
                    
                            cout << "\n\nDo you want to Update your account? (y/n): ";
                            cin >> Answer;
                    
                            if (Answer == 'Y' || Answer == 'y') {
                                UpdateClient(AccountNumber, vClients);
                                SaveClientsDataToFile(ClientsFileName, vClients);
                    
                                vClients = LoadClientsDataFromFile(ClientsFileName);
                                cout << "\n\nClient deleted successfully.";
                                return true;
                            }
                        }
                        else {
                            cout << "\nClient with Account Number (" << AccountNumber << ") is not found!";
                        }
                        return false;
                    }
                    
                    int main() {
                        vector<sClient> vClients = LoadClientsDataFromFile(ClientsFileName);
                        string AccountNumber = ReadClientAccountNumber();
                        UpdateAccount(AccountNumber, vClients);
                        return 0;
                    }

## 107 Bank Project 

                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    const string ClientsFileName = "Clients.txt";
                    
                    struct sClient {
                        string AccountNumber;
                        string PinCode;
                        string Name;
                        string Phone;
                        double AccountBalance;
                        bool MarkForDelete = false;
                    };
                    
                    vector<string> SplitString(const string& S1, const string& Delim) {
                        vector<string> vString;
                        size_t pos = 0, start = 0;
                        string sWord;
                    
                        while ((pos = S1.find(Delim, start)) != string::npos) {
                            sWord = S1.substr(start, pos - start);
                            if (!sWord.empty()) {
                                vString.push_back(sWord);
                            }
                            start = pos + Delim.length();
                        }
                        sWord = S1.substr(start);
                        if (!sWord.empty()) {
                            vString.push_back(sWord);
                        }
                        return vString;
                    }
                    
                    sClient ReadClient() {
                        sClient Client;
                    
                        cout << "Please enter your name" << endl;
                        getline(cin >> ws, Client.Name);
                    
                        cout << "Please enter Account Number " << endl;
                        cin >> Client.AccountNumber;
                    
                        cout << "Please enter Account Balance " << endl;
                        cin >> Client.AccountBalance;
                    
                        cout << "Please enter Phone " << endl;
                        cin >> Client.Phone;
                    
                        cout << "Please enter Pin Code " << endl;
                        cin >> Client.PinCode;
                    
                        return Client;
                    }
                    
                    sClient ConvertLineToRecord(const string& Line, const string& Seperator = "#||#") {
                        sClient Client;
                        vector<string> vClientData = SplitString(Line, Seperator);
                    
                        if (vClientData.size() == 5) {
                            Client.AccountNumber = vClientData[0];
                            Client.PinCode = vClientData[1];
                            Client.Name = vClientData[2];
                            Client.Phone = vClientData[3];
                            Client.AccountBalance = stod(vClientData[4]);
                        }
                        return Client;
                    }
                    
                    string ConvertRecordToLine(const sClient& Client, const string& sper = "#||#") {
                        string s = "";
                        s += Client.AccountNumber + sper;
                        s += Client.PinCode + sper;
                        s += Client.Name + sper;
                        s += Client.Phone + sper;
                        s += to_string(Client.AccountBalance);
                        return s;
                    }
                    
                    vector<sClient> LoadClientsDataFromFile(const string& FileName) {
                        vector<sClient> vClients;
                        ifstream MyFile(FileName);
                        if (MyFile.is_open()) {
                            string Line;
                            while (getline(MyFile, Line)) {
                                sClient Client = ConvertLineToRecord(Line);
                                vClients.push_back(Client);
                            }
                            MyFile.close();
                        }
                        return vClients;
                    }
                    
                    void SaveClientsDataToFile(const string& FileName, const vector<sClient>& vClients) {
                        ofstream MyFile(FileName, ios::out);
                        if (MyFile.is_open()) {
                            for (const sClient& Client : vClients) {
                                if (!Client.MarkForDelete) {
                                    MyFile << ConvertRecordToLine(Client) << endl;
                                }
                            }
                            MyFile.close();
                        }
                    }
                    
                    void PrintClientCard(const sClient& Client) {
                        cout << "\nThe following are the client details:\n";
                        cout << "Account Number: " << Client.AccountNumber << "\n";
                        cout << "Pin Code      : " << Client.PinCode << "\n";
                        cout << "Name          : " << Client.Name << "\n";
                        cout << "Phone         : " << Client.Phone << "\n";
                        cout << "Account Balance: " << Client.AccountBalance << "\n";
                    }
                    
                    bool FindClientByAccountNumber(const string& AccountNumber, const vector<sClient>& vClients, sClient& Client) {
                        for (const sClient& C : vClients) {
                            if (C.AccountNumber == AccountNumber) {
                                Client = C;
                                return true;
                            }
                        }
                        return false;
                    }
                    
                    string ReadClientAccountNumber() {
                        string AccountNumber;
                        cout << "\nPlease enter Account Number: ";
                        cin >> AccountNumber;
                        return AccountNumber;
                    }
                    
                    void UpdateClient(const string& AccountNumber, vector<sClient>& vClients) {
                        for (sClient& c : vClients) {
                            if (c.AccountNumber == AccountNumber) {
                                cout << "Enter pin code?";
                                getline(cin >> ws, c.PinCode);
                                cout << "Enter Name?";
                                getline(cin, c.Name);
                                cout << "Enter Phone?";
                                getline(cin, c.Phone);
                                cout << "Enter Account Balance?";
                                cin >> c.AccountBalance;
                    
                                cout << "\nClient Updated Successfully.";
                            }
                        }
                    }
                    
                    bool UpdateAccount(const string& AccountNumber, vector<sClient>& vClients) {
                        sClient Client;
                        char Answer = 'n';
                    
                        if (FindClientByAccountNumber(AccountNumber, vClients, Client)) {
                            PrintClientCard(Client);
                    
                            cout << "\n\nDo you want to update your account? (y/n): ";
                            cin >> Answer;
                    
                            if (Answer == 'Y' || Answer == 'y') {
                                UpdateClient(AccountNumber, vClients);
                                SaveClientsDataToFile(ClientsFileName, vClients);
                    
                                vClients = LoadClientsDataFromFile(ClientsFileName);
                                cout << "\n\nClient updated successfully.";
                                return true;
                            }
                        }
                        else {
                            cout << "\nClient with Account Number (" << AccountNumber << ") is not found!";
                        }
                        return false;
                    }
                    
                    short MainMenu() {
                        short Number;
                        cout << "__________________________________________________________________________\n";
                        cout << "\t\t\t\tMain Menu Screen\n";
                        cout << "__________________________________________________________________________\n";
                        cout << "\t\t[1] Show Client List\n";
                        cout << "\t\t[2] Add New Client\n";
                        cout << "\t\t[3] Delete Client\n";
                        cout << "\t\t[4] Update Client Info\n";
                        cout << "\t\t[5] Find Client\n";
                        cout << "\t\t[6] Exit\n";
                        cout << "__________________________________________________________________________\n";
                        cout << "Choose what do you want to do? [1 to 6]? ";
                        cin >> Number;
                        return Number;
                    }
                    
                    void PrintClientRecord(sClient Client) {
                        cout << "| " << setw(15) << left << Client.AccountNumber;
                        cout << "| " << setw(10) << left << Client.PinCode;
                        cout << "| " << setw(40) << left << Client.Name;
                        cout << "| " << setw(12) << left << Client.Phone;
                        cout << "| " << setw(12) << left << Client.AccountBalance;
                    }
                    
                    void PrintAllClientsData(vector<sClient> vClients) {
                        cout << "\n\t\t\t\t\tClient List (" << vClients.size() << ") Client(s).\n";
                        cout << "_______________________________________________________";
                        cout << "_________________________________________\n";
                        cout << "| " << left << setw(15) << "Account Number";
                        cout << "| " << left << setw(10) << "Pin Code";
                        cout << "| " << left << setw(40) << "Client Name";
                        cout << "| " << left << setw(12) << "Phone";
                        cout << "| " << left << setw(12) << "Balance\n";
                        cout << "_______________________________________________________";
                        cout << "_________________________________________\n";
                        for (const sClient& Client : vClients) {
                            PrintClientRecord(Client);
                            cout << endl;
                        }
                        cout << "_______________________________________________________";
                        cout << "_________________________________________\n";
                    }
                    
                    void AddNewClient(const string& FileName, vector<sClient>& vClients) {
                        sClient Client = ReadClient();
                        vClients.push_back(Client);
                        SaveClientsDataToFile(FileName, vClients);
                    }
                    
                    bool MarkClientForDeleteByAccountNumber(const string& AccountNumber, vector<sClient>& vClients) {
                        for (sClient& c : vClients) {
                            if (c.AccountNumber == AccountNumber) {
                                c.MarkForDelete = true;
                                return true;
                            }
                        }
                        return false;
                    }
                    
                    bool DeleteClientByAccountNumber(const string& AccountNumber, vector<sClient>& vClients) {
                        sClient Client;
                        char Answer = 'n';
                    
                        if (FindClientByAccountNumber(AccountNumber, vClients, Client)) {
                            PrintClientCard(Client);
                    
                            cout << "\n\nDo you want to delete your account? (y/n): ";
                            cin >> Answer;
                    
                            if (Answer == 'Y' || Answer == 'y') {
                                MarkClientForDeleteByAccountNumber(AccountNumber, vClients);
                                SaveClientsDataToFile(ClientsFileName, vClients);
                    
                                vClients = LoadClientsDataFromFile(ClientsFileName);
                                cout << "\n\nClient deleted successfully.";
                                return true;
                            }
                        }
                        else {
                            cout << "\nClient with Account Number (" << AccountNumber << ") is not found!";
                        }
                        return false;
                    }
                    
                    void FindAndPrintClient(const string& AccountNumber, const vector<sClient>& vClients) {
                        sClient Client;
                        if (FindClientByAccountNumber(AccountNumber, vClients, Client)) {
                            PrintClientCard(Client);
                        }
                        else {
                            cout << "\nClient with Account Number (" << AccountNumber << ") is not found!\n";
                        }
                    }
                    
                    int main() {
                        vector<sClient> vClients = LoadClientsDataFromFile(ClientsFileName);
                        short Number;
                    
                        do {
                            Number = MainMenu();
                    
                            switch (Number) {
                            case 1:
                                PrintAllClientsData(vClients);
                                break;
                            case 2:
                                AddNewClient(ClientsFileName, vClients);
                                break;
                            case 3: {
                                string AccountNumber = ReadClientAccountNumber();
                                DeleteClientByAccountNumber(AccountNumber, vClients);
                                break;
                            }
                            case 4: {
                                string AccountNumber = ReadClientAccountNumber();
                                UpdateAccount(AccountNumber, vClients);
                                break;
                            }
                            case 5: {
                                string AccountNumber = ReadClientAccountNumber();
                                FindAndPrintClient(AccountNumber, vClients);
                                break;
                            }
                            case 6:
                                cout << "Exiting program..." << endl;
                                break;
                            default:
                                cout << "Invalid choice. Please select a valid option." << endl;
                            }
                        } while (Number != 6);
                    
                        return 0;
                    }


## 108 Update file and word conversion by another word 


                    
                    #include<iostream>
                    #include<fstream>
                    #include<string>
                    #include<vector>
                    using namespace std;
                    void LoadDataFromFileToVector(string FileName, vector <string> & vFileContent)
                    {
                    	fstream MyFile;   
                    	MyFile.open("file.txt", ios::in);//read Mode
                    	if (MyFile.is_open()) 
                    	{ 
                    		string Line;
                    		
                    	 while (getline(MyFile, Line))  
                    	{
                    			vFileContent.push_back(Line);      
                    	}   
                    		MyFile.close();   
                    	}
                    }
                    void SaveVectorToFile(string FileName, vector <string> vFileContent) 
                    { 
                    	fstream MyFile;   
                    	MyFile.open("file.txt", ios::out);
                    	if (MyFile.is_open()) 
                    	{
                    		for (string Line : vFileContent)  
                    		{ 
                    			if (Line != "") 
                    		{            
                    			MyFile << Line << endl;  
                    		}  
                    
                    		}  
                    
                    		MyFile.close(); 
                    	}
                    } 
                    
                    void UpdateRecordFromFile(string FileName, string Record , string UpdateTo) 
                    	{ 
                    	vector <string> vFileContent; 
                    
                    	LoadDataFromFileToVector(FileName, vFileContent);
                    
                    	for (string &Line : vFileContent) 
                    	{ 
                    		short pos = 0; 
                    		while ((pos = Line.find(Record, pos)) != std::string::npos) {
                    			Line.replace(pos, Record.length(), UpdateTo);
                    			pos += UpdateTo.length();
                    		}
                    	
                    	}   
                    	        SaveVectorToFile(FileName, vFileContent);
                    	
                    }
                    void PrintFileContent(string FileName) {
                    
                    		fstream MyFile;   
                    		MyFile.open(FileName, ios::in);//read Mode
                    
                    		if (MyFile.is_open())
                    		{ 
                    			string Line; while (getline(MyFile, Line))  
                    		{          
                    				cout << Line << endl;    
                    		}       
                    			MyFile.close();  
                    		} 
                    }
                    int main() {
                    
                    			cout << "File Content Before Delete.\n";
                    			PrintFileContent("file.txt"); 
                    
                    			UpdateRecordFromFile("file.txt", "ali" , "Omar");
                    
                    			cout << "\n\nFile Content After Delete.\n";
                    
                    			PrintFileContent("file.txt"); return 0;
                    
                    }

## 109  Two matrices filled by a random number and compare to if equal or not equal 




                    
                    #include <iostream>
                    #include <cstdlib>
                    #include <ctime>
                    using namespace std;
                    
                    int RandomNumber(int From, int To) {
                        return rand() % (To - From + 1) + From;
                    }
                    
                    void FillMatrix1(int Matrix1[3][3], int Size) {
                        for (int i = 0; i < Size; i++) {
                            for (int j = 0; j < Size; j++) {
                                Matrix1[i][j] = RandomNumber(0, 10);
                            }
                        }
                    }
                    
                    void FillMatrix2(int Matrix2[3][3], int Size) {
                        for (int i = 0; i < Size; i++) {
                            for (int j = 0; j < Size; j++) {
                                Matrix2[i][j] = RandomNumber(0, 10);
                            }
                        }
                    }
                    
                    int SumMatrix(int Matrix[3][3], int Size) {
                        int Sum = 0;
                        for (int i = 0; i < Size; i++) {
                            for (int j = 0; j < Size; j++) {
                                Sum += Matrix[i][j];
                            }
                        }
                        return Sum;
                    }
                    void PrintMatrix(int Matrix[3][3] ) {
                        
                        for (int i = 0; i < 3; i++) {
                            for (int j = 0; j < 3; j++) {
                                cout << Matrix[i][j] << " ";
                            }
                            cout << endl;
                        }
                    
                    }
                    void CheckMatrices(int arr1[3][3], int arr2[3][3], int Size) {
                        int Sum1 = SumMatrix(arr1, Size);
                        int Sum2 = SumMatrix(arr2, Size);
                    
                        if (Sum1 == Sum2) {
                            cout << "Sum1 = " << Sum1 << "\nSum2 = " << Sum2 << "\nMatrices are Equal" << endl;
                        }
                        else {
                            cout << "Sum1 = " << Sum1 << "\nSum2 = " << Sum2 << "\nMatrices are not Equal" << endl;
                        }
                    }
                    
                    int main() {
                        srand((unsigned)time(NULL));
                    
                        int Matrix1[3][3], Matrix2[3][3];
                    
                        FillMatrix1(Matrix1, 3);
                        FillMatrix2(Matrix2, 3);
                    
                        
                        cout << "\nMatrix1:" << endl;
                        PrintMatrix(Matrix1);
                    
                        cout << "\nMatrix2:" << endl;
                        PrintMatrix(Matrix2);
                    
                        CheckMatrices(Matrix1, Matrix2, 3);
                    
                        return 0;
                    }


## 110 Print Each Row in the Matrix 


                    #include <iostream>
                    #include <cstdlib>
                    #include <ctime>
                    #include <vector>
                    using namespace std;
                    
                    int RandomNumber(int From, int To) {
                        return rand() % (To - From + 1) + From;
                    }
                    
                    void FillMatrix1(int Matrix1[3][3], int Size) {
                        for (int i = 0; i < Size; i++) {
                            for (int j = 0; j < Size; j++) {
                                Matrix1[i][j] = RandomNumber(0, 10);
                            }
                        }
                    }
                    
                    
                    vector <int> SumEachRow( int Matrix[3][3], int Size) {
                     
                        vector <int> vSum ;
                    
                        for (int i = 0; i < Size; i++) {
                            int Sum = 0;
                            for (int j = 0; j < Size; j++) {
                    
                                Sum += Matrix[i][j];
                            }
                            vSum.push_back(Sum);
                        }
                        return vSum;
                    }
                    void PrintEachRow(vector <int> & vSum) {
                        
                        int counter = 1;
                        for (int sum : vSum) {
                            cout << "Row (" << counter << ") = "<< sum << endl;
                            counter++;
                        }
                    }
                    
                    int main() {
                    
                        srand((unsigned)time(NULL));
                    
                        int Matrix1[3][3];
                    
                        FillMatrix1(Matrix1, 3);
                    
                        vector <int> vSum =  SumEachRow( Matrix1, 3);
                    
                        cout << "\nMatrix Row Sums :" << endl;
                        PrintEachRow(vSum);
                    
                    
                        return 0;
                    }


## 111  Sum Clomns in Matrix 


                    #include <iostream>
                    #include <cstdlib>
                    #include <ctime>
                    #include <vector>
                    using namespace std;
                    
                    int RandomNumber(int From, int To) {
                        return rand() % (To - From + 1) + From;
                    }
                    
                    void FillMatrix1(int Matrix1[3][3], int Size) {
                        for (int i = 0; i < Size; i++) {
                            for (int j = 0; j < Size; j++) {
                                Matrix1[i][j] = RandomNumber(0, 10);
                            }
                        }
                    }
                    
                    
                    vector <int> SumEachRow( int Matrix[3][3], int Size) {
                     
                        vector <int> vSum ;
                    
                        for (int i = 0; i < Size; i++) {
                            int Sum = 0;
                            for (int j = 0; j < Size; j++) {
                    
                                Sum += Matrix[j][i];
                            }
                            vSum.push_back(Sum);
                        }
                        return vSum;
                    }
                    void PrintMatrix(int Matrix[3][3] , int Size) {
                    
                        for (int i = 0; i < Size; i++) {
                            for (int j = 0; j < Size; j++) {
                                cout << Matrix[i][j] << " ";
                            }
                            cout << endl;
                        }
                    }
                    void PrintEachRow(vector <int> & vSum) {
                        
                        int counter = 1;
                        for (int sum : vSum) {
                            cout << "Row (" << counter << ") = "<< sum << endl;
                            counter++;
                        }
                    }
                    
                    int main() {
                    
                        srand((unsigned)time(NULL));
                    
                        int Matrix1[3][3];
                    
                        FillMatrix1(Matrix1, 3);
                        PrintMatrix(Matrix1, 3);
                    
                        
                        vector <int> vSum =  SumEachRow( Matrix1, 3);
                    
                        cout << "\nMatrix Cols Sums :" << endl;
                        PrintEachRow(vSum);
                    
                    
                        return 0;
                    }


## 112 Reverse String 

                    #include <iostream>
                    #include <vector>
                    #include <string>
                    using namespace std;
                    
                    string ReadString() {
                        string Name;
                        cout << "Please Enter Your String ?" << endl;
                        getline(cin, Name);
                        return Name;
                    }
                    
                    vector<string> SplitString(const string& s, const string& delim) {
                        vector<string> vWord;
                        size_t pos = 0;
                        size_t start = 0;
                    
                        while ((pos = s.find(delim, start)) != string::npos) {
                            string sWord = s.substr(start, pos - start);
                            if (!sWord.empty()) {
                                vWord.push_back(sWord);
                            }
                            start = pos + delim.length();
                        }
                    
                        if (start < s.size()) {
                            vWord.push_back(s.substr(start));
                        }
                    
                        return vWord;
                    }
                    
                    void PrintReverse(const vector<string>& vWord) {
                        for (int i = vWord.size() - 1; i >= 0; i--) {
                            cout << vWord[i] << " ";
                        }
                        cout << endl;
                    }
                    
                    int main() {
                        vector<string> vWord = SplitString(ReadString(), " ");
                        PrintReverse(vWord);
                        return 0;
                    }

## 113 Load Data to file 


                    #include <iostream>
                    #include <vector>
                    #include <string>
                    #include <fstream>
                    using namespace std;
                    
                    struct sClient {
                        string AccountNumber , pinCode , Name , Phone ;
                        double AccountBalance; 
                    
                    };
                    sClient ReadRecord() {
                    
                        sClient Client;
                        cout << "Enter Account Number? ";
                       getline( cin , Client.AccountNumber);
                    
                        cout << "Enter Pin Code ? ";
                        getline(cin, Client.pinCode);
                    
                        cout << "Enter Name? ";
                        getline(cin, Client.Name);
                    
                        cout << "Enter Phone? ";
                        getline(cin, Client.Phone);
                    
                        cout << "Enter Account Balance? ";
                        cin >> Client.AccountBalance;
                    
                        return Client;
                    
                    }
                    string SumString(string Delim) {
                    
                        sClient  Client = ReadRecord();
                        string S2;
                    
                        S2 += Client.AccountNumber + Delim;
                        S2 += Client.Name + Delim;
                        S2 += Client.Phone + Delim;
                        S2 += Client.pinCode + Delim;
                        S2 += to_string(Client.AccountBalance) ;
                    
                        return S2;
                    
                    }
                    void LoadDataToFile() {
                    
                    
                        string s = SumString("#//#");  
                        
                        fstream MyFile;
                    
                        MyFile.open("file.txt", ios::out);
                    
                        if (MyFile.is_open()) {
                            MyFile << s;
                        }
                        MyFile.close();
                    }
                    int main() {
                      
                    
                        LoadDataToFile();
                    
                        return 0;
                    }


## 114 Load Data from the file and print it 


                              #include <iostream>
                              #include <vector>
                              #include <string>
                              #include <fstream>
                              using namespace std;
                              
                              struct sClient {
                                  string AccountNumber, pinCode, Name, Phone;
                                  double AccountBalance;
                              
                              };
                              
                              string LoadDataFromFile() {

                        fstream MyFile;
                        MyFile.open("file.txt", ios::in); // read from file 
                    
                        string Line , AllData;
                        
                        if (MyFile.is_open()) {
                    
                            while (getline(MyFile, Line)) {
                                AllData +=  Line + "\n";
                            }
                        }
                        MyFile.close();
                        return AllData;
                    }
                    vector <string> SplitLine( string delim) {
                        vector <string> vClient ;
                    
                        string s = LoadDataFromFile();
                        short pos = 0;
                        string sWord;
                    
                        while ((pos = s.find(delim)) != std::string::npos) {
                    
                            sWord = s.substr(0, pos);
                    
                            if (sWord != " ") {
                                vClient.push_back(sWord);
                            }
                            s.erase(0, pos + delim.length());
                    
                        }
                        if (s != " ") {
                            vClient.push_back(s);
                        }
                        return vClient;
                    }
                    sClient ConvertLineToRecord() {
                    
                            sClient Client;
                            vector <string> vClient = SplitLine("#//#");
                    
                            Client.AccountNumber = vClient[0];
                            Client.pinCode = vClient[1];
                            Client.Name = vClient[2];
                            Client.Phone = vClient[3];
                            Client.AccountBalance = stod(vClient[4]);
                    
                            return Client;
                    
                    }
                    void PrintRecod(sClient Client) {
                    
                        cout << "Account Number: " << Client.AccountNumber << endl;
                        cout << "Pin Code : " << Client.pinCode << endl;
                        cout << "Name : " << Client.Name << endl;
                        cout << "Phone : " << Client.Phone << endl;
                        cout << "Account Balance : " << Client.AccountBalance << endl;
                        cout << "=========================================" << endl;
                    }
                    int main() {
                        
                        sClient Client =  ConvertLineToRecord();
                    
                        PrintRecod(Client);
                    
                        return 0;
                    }

## 115 Add More Client in File 


                    #include <iostream>
                    #include <vector>
                    #include <string>
                    #include <fstream>
                    using namespace std;
                    
                    struct sClient {
                        string AccountNumber, pinCode, Name, Phone;
                        double AccountBalance;
                    
                    };
                    sClient ReadRecord() {
                    
                        sClient Client;
                        cout << "Enter Account Number? ";
                        getline(cin >> ws, Client.AccountNumber);
                    
                        cout << "Enter Pin Code ? ";
                        getline(cin, Client.pinCode);
                    
                        cout << "Enter Name? ";
                        getline(cin, Client.Name);
                    
                        cout << "Enter Phone? ";
                        getline(cin, Client.Phone);
                    
                        cout << "Enter Account Balance? ";
                        cin >> Client.AccountBalance;
                    
                        return Client;
                    
                    }
                    string ConvertRecordToLine(string Delim) {
                    
                        sClient  Client = ReadRecord();
                        string S2;
                    
                        S2 += Client.AccountNumber + Delim;
                        S2 += Client.Name + Delim;
                        S2 += Client.Phone + Delim;
                        S2 += Client.pinCode + Delim;
                        S2 += to_string(Client.AccountBalance);
                    
                        return S2;
                    
                    }
                    void LoadDataToFile() {
                    
                    
                        string s = ConvertRecordToLine("#//#");
                    
                        fstream MyFile;
                    
                        MyFile.open("file.txt", ios::out | ios::app);
                    
                        if (MyFile.is_open()) {
                            MyFile << s << endl;
                        }
                        MyFile.close();
                    }
                    void AddMoreClient() {
                        char c1; 
                    
                    
                        do {
                    
                            LoadDataToFile();
                            cout << "Do you need add more client (y/n)?";
                            cout << endl;
                            cin >> c1;
                        } while (c1 == 'y' || c1 == 'Y');
                    }
                    int main() {
                    
                    
                        AddMoreClient();
                        
                    
                        return 0;
                    }

## 116 Print All Clients in File 


                    #include <iostream>
                    #include <vector>
                    #include <string>
                    #include <fstream>
                    #include <iomanip>
                    using namespace std;
                    
                    const string ClientsFileName = "file.txt";
                    
                    struct sClient {
                        string AccountNumber, pinCode, Name, Phone;
                        double AccountBalance;
                    
                    };
                    vector <string> SplitLine(string s, string delim) {
                        vector <string> vClient;
                    
                        short pos = 0;
                        string sWord;
                    
                        while ((pos = s.find(delim)) != std::string::npos) {
                    
                            sWord = s.substr(0, pos);
                    
                            if (sWord != " ") {
                                vClient.push_back(sWord);
                            }
                            s.erase(0, pos + delim.length());
                    
                        }
                        if (s != " ") {
                            vClient.push_back(s);
                        }
                        return vClient;
                    }
                    sClient ConvertLineToRecord(string Line , string sper = "#//#") {
                    
                        sClient Client;
                    
                        vector <string> vClient = SplitLine(Line , sper);
                    
                        Client.AccountNumber = vClient[0];
                        Client.pinCode = vClient[1];
                        Client.Name = vClient[2];
                        Client.Phone = vClient[3];
                        Client.AccountBalance = stod(vClient[4]);
                    
                        return Client;
                    
                    }
                    
                    vector <sClient> LoadDataFromFile(string FileName) {
                    
                        fstream MyFile;
                        MyFile.open(FileName, ios::in); // read from file 
                    
                        string Line;
                        sClient Client;
                    
                        vector <sClient> vClient;
                    
                        if (MyFile.is_open()) {
                    
                            while (getline(MyFile, Line)) {
                                Client = ConvertLineToRecord(Line);
                                vClient.push_back(Client);
                            }
                        }
                        MyFile.close();
                        return vClient;
                    }
                    
                    
                    void PrintClientRecord(sClient Client) {
                    
                        cout << "| " << setw(15) << left << Client.AccountNumber; 
                        cout << "| " << setw(30) << left << Client.pinCode;   
                        cout << "| " << setw(40) << left << Client.Name; 
                        cout << "| " << setw(12) << left << Client.Phone;  
                        cout << "| " << setw(12) << left << Client.AccountBalance;
                    }
                    void PrintAllClient(vector <sClient> vClients) {
                        
                        cout << "\n\t\t\t\tClient List( " << vClients.size() << ") Client(s)";
                    
                        cout << "\n_______________________________________________________";  
                        cout << "_________________________________________\n" << endl;  
                    
                        cout << "| " << left << setw(15) << "Accout Number";   
                        cout << "| " << left << setw(40) << "Client Name"; 
                        cout << "| " << left << setw(10) << "Pin Code";   
                        cout << "| " << left << setw(12) << "Phone";   
                        cout << "| " << left << setw(12) << "Balance";  
                    
                        cout << "\n_______________________________________________________";    
                        cout << "_________________________________________\n" << endl;
                    
                        for (sClient Client : vClients) {
                            PrintClientRecord(Client);
                            cout << endl;
                        }
                    
                    }
                    int main() {
                    
                       
                        vector < sClient> vClients = LoadDataFromFile(ClientsFileName);
                    
                    
                        PrintAllClient(vClients);
                    
                        return 0;
                    }
                    

## 117 Find Client by Account Number 



                    #include <iostream>
                    #include <vector>
                    #include <string>
                    #include <fstream>
                    #include <iomanip>
                    using namespace std;
                    
                    const string ClientsFileName = "file.txt";
                    
                    struct sClient {
                        string AccountNumber, pinCode, Name, Phone;
                        double AccountBalance;
                    
                    };
                    vector <string> SplitLine(string s, string delim) {
                        vector <string> vClient;
                    
                        short pos = 0;
                        string sWord;
                    
                        while ((pos = s.find(delim)) != std::string::npos) {
                    
                            sWord = s.substr(0, pos);
                    
                            if (sWord != " ") {
                                vClient.push_back(sWord);
                            }
                            s.erase(0, pos + delim.length());
                    
                        }
                        if (s != " ") {
                            vClient.push_back(s);
                        }
                        return vClient;
                    }
                    sClient ConvertLineToRecord(string Line , string sper = "#//#") {
                    
                        sClient Client;
                    
                        vector <string> vClient = SplitLine(Line , sper);
                    
                        Client.AccountNumber = vClient[0];
                        Client.pinCode = vClient[1];
                        Client.Name = vClient[2];
                        Client.Phone = vClient[3];
                        Client.AccountBalance = stod(vClient[4]);
                    
                        return Client;
                    
                    }
                    
                    vector <sClient> LoadDataFromFile(string FileName) {
                    
                        fstream MyFile;
                        MyFile.open(FileName, ios::in); // read from file 
                    
                        string Line;
                        sClient Client;
                    
                        vector <sClient> vClient;
                    
                        if (MyFile.is_open()) {
                    
                            while (getline(MyFile, Line)) {
                                Client = ConvertLineToRecord(Line);
                                vClient.push_back(Client);
                            }
                        }
                        MyFile.close();
                        return vClient;
                    }
                    void PrintRecord(sClient &Client) {
                           
                            cout << "Account Number: " << Client.AccountNumber << endl;
                            cout << "pin code: " << Client.pinCode << endl;
                            cout << "Name : " << Client.Name << endl;
                            cout << "Phone : " << Client.Phone << endl;
                            cout << "Account Balance: " << Client.AccountBalance << endl;
                    
                    }
                    void FindClient(vector < sClient>& vClients) {
                    
                        string Account;
                        cout << "Please Enter Account Number : ";
                        cin >> Account;
                    
                        bool Found = false;
                        
                        for (sClient Client : vClients) {
                            if (Account == Client.AccountNumber) {
                    
                                PrintRecord(Client);
                            }
                        }
                        if (!Found) {
                            cout << "Client with Account Number " << Account << "Not found." << endl;
                        }
                    
                    }
                    
                    int main() {
                    
                       
                        vector < sClient> vClients = LoadDataFromFile(ClientsFileName);
                    
                        FindClient(vClients);
                    
                        return 0;
                    }

 ## 118 Delete Client From File 

                     #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    const string ClientsFileName = "Clients.txt";
                    
                    struct sClient {
                        string AccountNumber;
                        string PinCode;
                        string Name;
                        string Phone;
                        double AccountBalance;
                        bool MarkForDelete = false;
                    };
                    
                    vector<string> SplitString(string S1, const string& Delim) {
                        vector<string> vString;
                        size_t pos = 0;
                        while ((pos = S1.find(Delim)) != string::npos) {
                            string sWord = S1.substr(0, pos);
                            if (!sWord.empty()) {
                                vString.push_back(sWord);
                            }
                            S1.erase(0, pos + Delim.length());
                        }
                        if (!S1.empty()) {
                            vString.push_back(S1);
                        }
                        return vString;
                    }
                    
                    sClient ConvertLinetoRecord(const string& Line, const string& Seperator = "#//#") {
                        sClient Client;
                        vector<string> vClientData = SplitString(Line, Seperator);
                        if (vClientData.size() == 5) {
                            Client.AccountNumber = vClientData[0];
                            Client.PinCode = vClientData[1];
                            Client.Name = vClientData[2];
                            Client.Phone = vClientData[3];
                            Client.AccountBalance = stod(vClientData[4]);
                        }
                        return Client;
                    }
                    
                    string ConvertRecordToLine(const sClient& Client, const string& Seperator = "#//#") {
                        string stClientRecord = Client.AccountNumber + Seperator +
                                                Client.PinCode + Seperator +
                                                Client.Name + Seperator +
                                                Client.Phone + Seperator +
                                                to_string(Client.AccountBalance);
                        return stClientRecord;
                    }
                    
                    vector<sClient> LoadCleintsDataFromFile(const string& FileName) {
                        vector<sClient> vClients;
                        fstream MyFile(FileName, ios::in);
                        if (MyFile.is_open()) {
                            string Line;
                            while (getline(MyFile, Line)) {
                                sClient Client = ConvertLinetoRecord(Line);
                                vClients.push_back(Client);
                            }
                            MyFile.close();
                        }
                        return vClients;
                    }
                    
                    void SaveCleintsDataToFile(const string& FileName, const vector<sClient>& vClients) {
                        fstream MyFile(FileName, ios::out);
                        if (MyFile.is_open()) {
                            for (const sClient& C : vClients) {
                                if (!C.MarkForDelete) {
                                    string DataLine = ConvertRecordToLine(C);
                                    MyFile << DataLine << endl;
                                }
                            }
                            MyFile.close();
                        }
                    }
                    
                    void PrintClientCard(const sClient& Client) {
                        cout << "\nThe following are the client details:\n";
                        cout << "\nAccount Number: " << Client.AccountNumber;
                        cout << "\nPin Code     : " << Client.PinCode;
                        cout << "\nName         : " << Client.Name;
                        cout << "\nPhone        : " << Client.Phone;
                        cout << "\nAccount Balance: " << Client.AccountBalance << endl;
                    }
                    
                    bool FindClientByAccountNumber(const string& AccountNumber, const vector<sClient>& vClients, sClient& Client) {
                        for (const sClient& C : vClients) {
                            if (C.AccountNumber == AccountNumber) {
                                Client = C;
                                return true;
                            }
                        }
                        return false;
                    }
                    
                    bool MarkClientForDeleteByAccountNumber(const string& AccountNumber, vector<sClient>& vClients) {
                        for (sClient& C : vClients) {
                            if (C.AccountNumber == AccountNumber) {
                                C.MarkForDelete = true;
                                return true;
                            }
                        }
                        return false;
                    }
                    
                    bool DeleteClientByAccountNumber(const string& AccountNumber, vector<sClient>& vClients) {
                        sClient Client;
                        char Answer = 'n';
                    
                        if (FindClientByAccountNumber(AccountNumber, vClients, Client)) {
                            PrintClientCard(Client);
                            cout << "\n\nAre you sure you want to delete this client? y/n ? ";
                            cin >> Answer;
                            if (Answer == 'y' || Answer == 'Y') {
                                MarkClientForDeleteByAccountNumber(AccountNumber, vClients);
                                SaveCleintsDataToFile(ClientsFileName, vClients);
                                cout << "\n\nClient Deleted Successfully." << endl;
                                return true;
                            }
                        } else {
                            cout << "\nClient with Account Number (" << AccountNumber << ") is Not Found!" << endl;
                        }
                        return false;
                    }
                    
                    string ReadClientAccountNumber() {
                        string AccountNumber;
                        cout << "\nPlease enter Account Number? ";
                        cin >> AccountNumber;
                        return AccountNumber;
                    }
                    
                    int main() {
                        vector<sClient> vClients = LoadCleintsDataFromFile(ClientsFileName);
                        string AccountNumber = ReadClientAccountNumber();
                        DeleteClientByAccountNumber(AccountNumber, vClients);
                        return 0;
                    }
          

## 119 Program Convert Number to String Value 

                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    
                    string NumberToText(int Number) {
                    
                        if (Number == 0) {
                            return  " ";
                        }
                        if (Number >= 1 && Number <= 19) 
                        {
                            string arr[] = { "" ," One ","Two ","Three ","Four ","Five","Six","Seven",
                                "Eight","Nine","Ten","Eleven","Twelve","Thirteen","Fourteen", "Fifteen",
                                "Sixteen","Seventeen","Eighteen","Nineteen" };
                            return arr[Number] + " ";
                        }
                        if (Number >= 20 && Number <= 99)
                        {
                            string arr[] = { "" , "", " Twenty " , " Thirty " ,  " Forty" , " Fifty " 
                                ," Sixty " , " Seventy " , " Eighty " , " Ninety " };
                            return arr[Number / 10] + " " + NumberToText(Number % 10);
                            
                        }
                        if (Number >= 100 && Number <= 199) 
                        {
                            return " One Hundred " + NumberToText(Number % 100);
                        }
                        if (Number >= 200 && Number <= 999)
                        {
                            return NumberToText(Number / 100) + " Hundreds " + NumberToText(Number % 100);
                        }
                        if (Number >= 1000 && Number <= 1999)
                        {
                            return  " One Thousand " + NumberToText(Number % 1000);
                        }
                        if (Number >= 2000 && Number <= 999999 ) {
                            return NumberToText(Number / 1000) + " Thousands " + NumberToText(Number % 1000);
                        }
                        if (Number >= 2000000 && Number <= 999999999) {
                            return   NumberToText(Number / 1000000) + " Millions " + NumberToText(Number % 1000000);
                        }
                        if (Number >= 1000000000 && Number <= 1999999999) { 
                            return"One Billion " + NumberToText(Number % 1000000000);
                        }
                        else { 
                            return   NumberToText(Number / 1000000000) + " Billions " + NumberToText(Number % 1000000000);
                        }
                    }
                    int ReadNumber() {
                    
                        int Number = 0;
                        cout << "Please Enter Number : ";
                        cin >> Number;
                        return Number;
                    }
                    int main() {
                        
                        int Number = ReadNumber();
                    
                        cout << NumberToText(Number);
                        return 0;
                    }
                    


## 120 Write a program to check whether the year is a leap year or not Leap.


                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    int ReadYear() {
                        int Year;
                        cout << "Please enter year: ";
                        cin >> Year;
                        return Year;
                    }
                    bool IsLeapYear(int Year) {
                        if (Year % 400 == 0 || Year % 4 == 0) {
                            return true;
                        }
                        else if (Year % 100 == 0 )
                        {
                            return false;
                        }
                        else {
                            return false;
                        }
                    }
                    
                    int main() {
                    
                        
                        int Year = ReadYear();
                    
                        if (IsLeapYear(Year)) {
                            cout << "Yes, Year [ " << Year << "] is a leap \n";
                        }
                        else {
                            cout << "No, Year [ " << Year << "] is a No't leap \n";
                        }
                        return 0;
                    }
                    
   ## 121  Write a program to check whether the year is a leap year or not Leap.

                       
                      #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    int ReadYear() {
                        int Year;
                        cout << "Please enter year : ";
                        cin >> Year;
                        return Year;
                    }
                    bool IsLeapYear(int Year) {
                    
                        return (Year % 400 == 0) || (Year % 4 == 0 && Year % 100 != 0);
                     
                    }
                    
                    int main() {
                    
                        
                        int Year = ReadYear();
                    
                        if (IsLeapYear(Year)) {
                            cout << "Yes, Year [ " << Year << "] is a leap \n";
                        }
                        else {
                            cout << "No, Year [ " << Year << "] is a No't leap \n";
                        }
                        return 0;
                    }


## 122 Write a program print all day and hours and minutes and seconds in years 


                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    int ReadYear() {
                        int Year;
                        cout << "Please enter year : ";
                        cin >> Year;
                        return Year;
                    }
                    bool IsLeapYear(int Year) {
                    
                        return (Year % 400 == 0) || (Year % 4 == 0 && Year % 100 != 0);
                     
                    }
                    
                    void Printleap(int Year) {
                        cout << "Number of Days       in Year [" << Year << "] is 365\n" ;
                        cout << "Number of Hours      in Year [" << Year << "] is 8760\n";
                        cout << "Number of Minutes    in Year [" << Year << "] is 525600\n";
                        cout << "Number of Seconds    in Year [" << Year << "] is 31536000\n";
                    }
                    void PrintNotleap(int Year) {
                        cout << "Number of Days       in Year [" << Year << "] is 366\n";
                        cout << "Number of Hours      in Year [" << Year << "] is 8784\n";
                        cout << "Number of Minutes    in Year [" << Year << "] is 527040\n";
                        cout << "Number of Seconds    in Year [" << Year << "] is 31622400\n";
                    }
                    int main() {
                    
                        
                        int Year = ReadYear();
                    
                        if (IsLeapYear(Year)) {
                            Printleap(Year);
                        }
                        else {
                            PrintNotleap(Year);
                        }
                        return 0;
                    }


## 123 Another solution 

                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    short ReadYear() {
                        short Year;
                        cout << "Please enter year : ";
                        cin >> Year;
                        return Year;
                    }
                    bool IsLeapYear(int Year) {
                        return (Year % 400 == 0) || (Year % 4 == 0 && Year % 100 != 0);
                    }
                    short NumberOfDaysInYear(short Year) {
                        return IsLeapYear(Year) ? 365 : 366;
                    }
                    short NumberOfHoursInYear(short Year) {
                        return NumberOfDaysInYear(Year) * 24;
                    }
                    int NumberOfMinutesInYear(short Year) {
                        return NumberOfHoursInYear(Year) * 60;
                    }
                    int NumberOfSecondsInYear(short Year) {
                        return NumberOfMinutesInYear(Year) * 60;
                    }
                    int main() {
                    
                        
                        short Year = ReadYear();
                    
                        cout << "\n Number of Days       in Year [" << Year << "] is " << NumberOfDaysInYear (Year);
                        cout << "\n Number of Hours      in Year [" << Year << "] is " << NumberOfHoursInYear(Year);
                        cout << "\n Number of Minutes    in Year [" << Year << "] is " << NumberOfMinutesInYear(Year);
                        cout << "\n Number of Seconds    in Year [" << Year << "] is " << NumberOfSecondsInYear(Year);
                        return 0;
                    }

 ## 124  Write a program print all day and hours and minutes and seconds in Month

                     #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    short ReadYear() {
                        short Year;
                        cout << "Please enter year : ";
                        cin >> Year;
                        return Year;
                    }
                    short ReadMonth() {
                        short Month;
                        cout << "Please Enter Month";
                        cin >> Month;
                        return Month;
                    }
                    bool IsLeapYear(short Year, short Month) {
                        return (Year % 400 == 0) || (Year % 4 == 0 && Year % 100 != 0);
                    }
                    short NumberOfDaysInMonth(short Year, short Month) {
                    
                        if (Month < 1 || Month > 12)
                            return 0;
                    
                        if (Month == 2) {
                    
                            return IsLeapYear(Year, Month) ? 28 : 29;
                        }
                    
                        short arr31Day[7] = { 1,3,5,7,8,10,12 };
                    
                        for (short i = 0; i < 7; i++) {
                            if (arr31Day[i] == Month) {
                    
                                return 31;
                            }
                        }
                    
                        return 30;
                    }
                    short NumberOfHoursInMonth(short Year, short Month) {
                        return NumberOfDaysInMonth(Year, Month) * 24;
                    }
                    int NumberOfMinutesInMonth(short Year, short Month) {
                        return NumberOfHoursInMonth(Year, Month) * 60;
                    }
                    int NumberOfSecondsInYear(short Year, short Month) {
                        return NumberOfMinutesInMonth(Year, Month) * 60;
                    }
                    int main() {
                    
                    
                        short Year = ReadYear();
                        short Month = ReadMonth();
                    
                        cout << "\n Number of Days       in Month [" << Month << "] is " << NumberOfDaysInMonth(Year, Month);
                        cout << "\n Number of Hours      in Month [" << Month << "] is " << NumberOfHoursInMonth(Year, Month);
                        cout << "\n Number of Minutes    in Month [" << Month << "] is " << NumberOfMinutesInMonth(Year, Month);
                        cout << "\n Number of Seconds    in Month [" << Month << "] is " << NumberOfSecondsInYear(Year, Month);
                        return 0;
                    }

## 125  another solution 


                    
                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    short ReadYear() {
                        short Year;
                        cout << "Please enter year : ";
                        cin >> Year;
                        return Year;
                    }
                    short ReadMonth() {
                        short Month;
                        cout << "Please Enter Month";
                        cin >> Month;
                        return Month;
                    }
                    bool IsLeapYear(short Year, short Month) {
                        return (Year % 400 == 0) || (Year % 4 == 0 && Year % 100 != 0);
                    }
                    short NumberOfDaysInMonth(short Year, short Month) {
                    
                        short NumberOfMonth[12] = { 31,29,31,30,31,30,31,31,30,31,30,31 };
                        return Month == 2 ? (IsLeapYear(Year, Month) ? 28 : 29) : NumberOfMonth[Month - 1];
                    }
                    short NumberOfHoursInMonth(short Year, short Month) {
                        return NumberOfDaysInMonth(Year, Month) * 24;
                    }
                    int NumberOfMinutesInMonth(short Year, short Month) {
                        return NumberOfHoursInMonth(Year, Month) * 60;
                    }
                    int NumberOfSecondsInYear(short Year, short Month) {
                        return NumberOfMinutesInMonth(Year, Month) * 60;
                    }
                    int main() {
                    
                    
                        short Year = ReadYear();
                        short Month = ReadMonth();
                    
                        cout << "\n Number of Days       in Month [" << Month << "] is " << NumberOfDaysInMonth(Year, Month);
                        cout << "\n Number of Hours      in Month [" << Month << "] is " << NumberOfHoursInMonth(Year, Month);
                        cout << "\n Number of Minutes    in Month [" << Month << "] is " << NumberOfMinutesInMonth(Year, Month);
                        cout << "\n Number of Seconds    in Month [" << Month << "] is " << NumberOfSecondsInYear(Year, Month);
                        return 0;
                    }

## 126 program calculates the day order and day name from the number of (year, month, day)



                    
                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    short ReadYear() {
                        short Year;
                        cout << "Please enter year : ";
                        cin >> Year;
                        return Year;
                    }
                    short ReadMonth() {
                        short Month;
                        cout << "Please Enter Month : ";
                        cin >> Month;
                        return Month;
                    }
                    short ReadDay() {
                        short Day;
                        cout << "Please Enter Day : ";
                        cin >> Day;
                        return Day;
                    }
                    short DayOfWeekOrder(short Day, short Month, short Year) {
                        
                        short a, y, m;
                        a = (14 - Month) / 12;
                        y = Year - a;
                        m = Month + (12 * a) - 2;
                        //Gregoraian low
                        return (Day + y + (y / 4) - (y / 100) + (y / 400) + ((31 * m) / 12)) % 7;
                    
                    }
                    string DayShortName(short DayOfWeekOrder) {
                        string arrDayName[] = { "Sun","Mon","Tue","Wed","Thu","Fri","Sat" };
                    
                        return arrDayName[DayOfWeekOrder];
                    }
                    void Print(short Year , short Month , short Day) {
                    
                        cout << "Date       :" << Year << "/" << Month << "/" << Day << endl;
                        cout << "Day Order  :" << DayOfWeekOrder(Year, Month, Day);
                        cout << "\nDay Name  :" << DayShortName(DayOfWeekOrder(Year, Month, Day));
                    }
                    int main() {
                    
                    
                        short Year = ReadYear();
                        short Month = ReadMonth();
                        short Day = ReadDay();
                    
                        Print(Year, Month, Day);
                        return 0;
                    }

## 127 Write program print the calendar month 

                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    short ReadYear() {
                        short Year;
                        cout << "Please enter year : ";
                        cin >> Year;
                        return Year;
                    }
                    short ReadMonth() {
                        short Month;
                        cout << "Please Enter Month : ";
                        cin >> Month;
                        return Month;
                    }
                    short DayOfWeekOrder(short Day, short Month, short Year) {
                    
                        short a, y, m;
                        a = (14 - Month) / 12;
                        y = Year - a;
                        m = Month + (12 * a) - 2;
                        //Gregoraian low
                        return (Day + y + (y / 4) - (y / 100) + (y / 400) + ((31 * m) / 12)) % 7;
                    
                    }
                    string DayShortName(short DayOfWeekOrder) {
                        string arrDayName[] = { "Sun","Mon","Tue","Wed","Thu","Fri","Sat" };
                    
                        return arrDayName[DayOfWeekOrder];
                    }
                    bool IsLeapYear(short Year, short Month) {
                        return (Year % 400 == 0) || (Year % 4 == 0 && Year % 100 != 0);
                    }
                    short NumberOfDaysInMonth(short Year, short Month) {
                    
                        if (Month < 1 || Month > 12) {
                            return 0;
                        }
                    
                        short NumberOfMonth[] = { 31,IsLeapYear(Year, Month) ? 28 : 29,31,30,31,30,31,31,30,31,30,31 };
                        return  NumberOfMonth[Month - 1];
                    }
                    string MonthName(short Month) {
                    
                        string arrMonth[12] = { "Jan" , "Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec" };
                        return arrMonth[Month - 1];
                    }
                    void Print(short Year, short Month) {
                    
                        short DaysInMonth = NumberOfDaysInMonth(Year, Month);
                        string sMonth = MonthName(Month);
                    
                        cout << "__________________" << sMonth << "__________________" << endl;
                    
                        printf("  Sun  Mon  Tue  Wed  Thu  Fri  Sat\n");
                    
                        short StartDay = DayOfWeekOrder(1, Month, Year);
                    
                        for (short i = 0; i < StartDay; i++) {
                            cout << setw(5) << " ";
                        }
                    
                        for (int i = 1; i <= DaysInMonth; i++) {
                    
                            cout << setw(5) << i;
                            if ((StartDay + i) % 7 == 0)
                                cout << endl;
                    
                        }
                        printf("\n_______________________________________");
                    }
                    int main() {
                    
                    
                        short Year = ReadYear();
                        short Month = ReadMonth();
                        
                    
                        Print(Year, Month);
                        return 0;
                    }

## 128 Write a program to print a year's calendar 
                    
                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    short ReadYear() {
                        short Year;
                        cout << "Please enter year : ";
                        cin >> Year;
                        return Year;
                    }
                    short DayOfWeekOrder(short Day, short Month, short Year) {
                    
                        short a, y, m;
                        a = (14 - Month) / 12;
                        y = Year - a;
                        m = Month + (12 * a) - 2;
                        //Gregoraian low
                        return (Day + y + (y / 4) - (y / 100) + (y / 400) + ((31 * m) / 12)) % 7;
                    
                    }
                    bool IsLeapYear(short Year, short Month) {
                        return (Year % 400 == 0) || (Year % 4 == 0 && Year % 100 != 0);
                    }
                    short NumberOfDaysInMonth(short Year, short Month) {
                    
                        if (Month < 1 || Month > 12) {
                            return 0;
                        }
                    
                        short NumberOfMonth[] = { 31,IsLeapYear(Year, Month) ? 28 : 29,31,30,31,30,31,31,30,31,30,31 };
                        return  NumberOfMonth[Month - 1];
                    }
                    string MonthName(short Month) {
                    
                        string arrMonth[12] = { "Jan" , "Feb","Mar","Apr","May","Jun","Jul","Aug","Sep","Oct","Nov","Dec" };
                        return arrMonth[Month - 1];
                    }
                    void Print(short Year, short Month) {
                    
                        short DaysInMonth = NumberOfDaysInMonth(Year, Month);
                        string sMonth = MonthName(Month);
                    
                        cout << "__________________" << sMonth << "__________________" << endl;
                    
                        printf("  Sun  Mon  Tue  Wed  Thu  Fri  Sat\n");
                    
                        short StartDay = DayOfWeekOrder(1, Month, Year);
                    
                        for (short i = 0; i < StartDay; i++) {
                            printf("    ");
                        }
                    
                        for (int i = 1; i <= DaysInMonth; i++) {
                    
                            cout << setw(5) << i;
                            if ((StartDay + i) % 7 == 0)
                                cout << endl;
                    
                        }
                        printf("\n_______________________________________");
                    }
                    int main() {
                    
                    
                    
                        short Year = ReadYear();
                        
                        for (short i = 1; i <= 12; i++) {
                    
                          short Month = i;
                          Print(Year, Month);
                          cout << endl;
                        }
                    
                        return 0;
                    }


## 129 Write a program to print the total number of days from one day in a year to user inter 



                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    short ReadYear() {
                        short Year;
                        cout << "Please enter year : ";
                        cin >> Year;
                        return Year;
                    }
                    short ReadMonth() {
                        short Month;
                        cout << "Please enter Month : ";
                        cin >> Month;
                        return Month;
                    }
                    short ReadDay() {
                        short Day;
                        cout << "Please enter Day : ";
                        cin >> Day;
                        return Day;
                    }
                    
                    
                    bool IsLeapYear(short Year, short Month) {
                        return (Year % 400 == 0) || (Year % 4 == 0 && Year % 100 != 0);
                    }
                    short NumberOfDaysInMonth(short Year, short Month) {
                    
                        if (Month < 1 || Month > 12) {
                            return 0;
                        }
                    
                        short NumberOfMonth[] = { 31,IsLeapYear(Year, Month) ? 28 : 29,31,30,31,30,31,31,30,31,30,31 };
                        return  NumberOfMonth[Month - 1];
                    }
                    short PrintTotalNumberOfDay(short Day ,  short Month, short Year) {
                    
                        short TotalDays = 0;
                    
                        for (int i = 1; i <= Month - 1; i++) {
                            TotalDays += NumberOfDaysInMonth(Year,i );
                        }
                    
                        TotalDays += Day;
                    
                        return  TotalDays ;
                    }
                    int main() {
                    
                    
                    
                        short Year = ReadYear();
                        short Month = ReadMonth();
                        short Day = ReadDay();
                    
                        cout << "Number of days from the begining of the year is " <<
                            PrintTotalNumberOfDay(Day, Month, Year);
                    
                        return 0;
                    }

## 130  Write program print date 


                              #include <iostream>
                              #include <fstream>
                              #include <string>
                              #include <vector>
                              #include <iomanip>
                              using namespace std;
                              
                              short ReadYear() {
                                  short Year;
                                  cout << "Please enter year : ";
                                  cin >> Year;
                                  return Year;
                              }
                              short ReadMonth() {
                                  short Month;
                                  cout << "Please enter Month : ";
                                  cin >> Month;
                                  return Month;
                              }
                              short ReadDay() {
                                  short Day;
                                  cout << "Please enter Day : ";
                                  cin >> Day;
                                  return Day;
                              }
                              
                              
                              bool IsLeapYear(short Year) {
                                  return (Year % 400 == 0) || (Year % 4 == 0 && Year % 100 != 0);
                              }
                              short NumberOfDaysInMonth(short Year, short Month) {
                              
                                  if (Month < 1 || Month > 12) {
                                      return 0;
                                  }
                              
                                  short NumberOfMonth[] = { 31,IsLeapYear(Year) ? 28 : 29,31,30,31,30,31,31,30,31,30,31 };
                                  return  NumberOfMonth[Month - 1];
                              }
                              short PrintTotalNumberOfDay(short Day, short Month, short Year) {
                              
                                  short TotalDays = 0;
                              
                                  for (int i = 1; i <= Month - 1; i++) {
                                      TotalDays += NumberOfDaysInMonth(Year, i);
                                  }
                              
                                  TotalDays += Day;
                              
                                  return  TotalDays;
                              }
                              struct sDate {
                                  short Day, Month;
                              };
                              sDate PrintDate(short TotalDay, short Year) {
                              
                                  sDate Date;
                                  short MonthDays = 0;
                                  Date.Month = 1;
                              
                                  while (true) {
                              
                                      MonthDays = NumberOfDaysInMonth(Year, Date.Month);
                              
                                      if (TotalDay > MonthDays) {
                              
                                          TotalDay -= MonthDays;
                                          Date.Month++;
                                      }
                                      else {
                                          Date.Day = TotalDay;
                                          break;
                                      }
                              
                                  }
                                  return Date;
                              }
                              
                              int main() {
                              
                              
                              
                                  short Year = ReadYear();
                                  short Month = ReadMonth();
                                  short Day = ReadDay();
                              
                                  short TotalDay = PrintTotalNumberOfDay(Day, Month, Year);
                              
                              
                                  sDate Date = PrintDate(TotalDay, Year);
                              
                                  cout << "Number of days from the begining of the year is " << TotalDay << endl;
                                  cout << "Date for [" << TotalDay << "[ is: " << Date.Day << "/" << Date.Month << "/" << Year;
                              
                                  return 0;
                              }

## 131 Write a program to read date and read how many days to add to it, print the results on screen 


                              #include <iostream>
                              #include <fstream>
                              #include <string>
                              #include <vector>
                              #include <iomanip>
                              using namespace std;
                              
                              short ReadYear() {
                                  short Year;
                                  cout << "Please enter year : ";
                                  cin >> Year;
                                  return Year;
                              }
                              short ReadMonth() {
                                  short Month;
                                  cout << "Please enter Month : ";
                                  cin >> Month;
                                  return Month;
                              }
                              short ReadDay() {
                                  short Day;
                                  cout << "Please enter Day : ";
                                  cin >> Day;
                                  return Day;
                              }
                              short AddDays() {
                                  short Days;
                                  cout << "How Many days to add? " ;
                                  cin >> Days;
                                  return Days;
                              
                              }
                              
                              bool IsLeapYear(short Year) {
                                  return (Year % 400 == 0) || (Year % 4 == 0 && Year % 100 != 0);
                              }
                              short NumberOfDaysInMonth(short Year, short Month) {
                              
                                  if (Month < 1 || Month > 12) {
                                      return 0;
                                  }
                              
                                  short NumberOfMonth[] = { 31,IsLeapYear(Year) ? 28 : 29,31,30,31,30,31,31,30,31,30,31 };
                                  return  NumberOfMonth[Month - 1];
                              }
                              short PrintTotalNumberOfDay(short Day, short Month, short Year) {
                              
                                  short TotalDays = 0;
                              
                                  for (int i = 1; i <= Month - 1; i++) {
                                      TotalDays += NumberOfDaysInMonth(Year, i);
                                  }
                              
                                  TotalDays += Day;
                              
                                  return  TotalDays;
                              }
                              struct sDate {
                                  short Day, Month;
                              };
                              sDate PrintDate(short TotalDay, short Year) {
                              
                                  sDate Date;
                                  short MonthDays = 0;
                                  Date.Month = 1;
                              
                                  while (true) {
                              
                                      MonthDays = NumberOfDaysInMonth(Year, Date.Month);
                              
                                      if (TotalDay > MonthDays) {
                              
                                          TotalDay -= MonthDays;
                                          Date.Month++;
                                      }
                                      else {
                                          Date.Day = TotalDay;
                                          break;
                                      }
                              
                                  }
                                  return Date;
                              }
                              
                              int main() {
                              
                              
                              
                                  short Year = ReadYear();
                                  short Month = ReadMonth();
                                  short Day = ReadDay();
                                  short Days = AddDays();
                              
                                  short TotalDay = Days +  PrintTotalNumberOfDay(Day, Month, Year);
                              
                              
                                  sDate Date = PrintDate(TotalDay, Year);
                              
                                  cout << "Date after adding  [" << Days << "] days is: " << Date.Day << "/" << Date.Month << "/" << Year;
                              
                                  return 0;
                              }

## 132 Write a program  to read a date and check if it is last day in month  2- if it is last Month in year 


                              #include <iostream>
                              #include <fstream>
                              #include <string>
                              #include <vector>
                              #include <iomanip>
                              using namespace std;
                              
                              short ReadYear() {
                                  short Year;
                                  cout << "Please enter year : " ;
                                  cin >> Year;
                                  return Year;
                              }
                              short ReadMonth() {
                                  short Month;
                                  cout << "Please enter Month : ";
                                  cin >> Month;
                                  return Month;
                              }
                              short ReadDay() {
                                  short Day;
                                  cout << "Please enter Day : ";
                                  cin >> Day;
                                  return Day;
                              }
                              struct sDate {
                                  short year, month, day;
                              };
                              static sDate ReadFullDate() {
                                  sDate Date;
                              
                                  Date.year = ReadYear();
                                  Date.month = ReadMonth();
                                  Date.day = ReadDay();
                              
                                  return Date;
                              }
                              bool IsLeapYear(short Year) {
                                  return (Year % 400 == 0) || (Year % 4 == 0 && Year % 100 != 0);
                              }
                              short NumberOfDaysInMonth(short Year, short Month ) {
                              
                                  if (Month < 1 || Month > 12) {
                                      return 0;
                                  }
                              
                                  short NumberOfMonth[] = { 31,IsLeapYear(Year) ? 28 : 29,31,30,31,30,31,31,30,31,30,31 };
                                  return  NumberOfMonth[Month - 1];
                              }
                              bool checkDay(sDate Date ) {
                                 
                                  return (Date.day == NumberOfDaysInMonth(Date.year, Date.month));
                              }
                              bool  CheckMonth(sDate Date) {
                                  
                                  return (Date.month == 12);
                              }
                              int main()
                              {
                                  sDate Date = ReadFullDate();
                              
                              
                                  if (checkDay(Date))
                                      cout << " \n You, day is last day in month ";
                                  else
                                      cout << "\n No , day is not last in month ";
                                  
                                   if (CheckMonth (Date))
                                       cout << "\n You , month  is last Month  in Year ";
                                   else
                                       cout << "\n No , Month is not last in Month in year  ";
                              
                                  return 0;
                              }

## 133 Write a program to read a date and  make a function to increase the date by one day.



                              #include <iostream>
                              #include <fstream>
                              #include <string>
                              #include <vector>
                              #include <iomanip>
                              using namespace std;
                              
                              short ReadYear() {
                                  short Year;
                                  cout << "Please enter year : ";
                                  cin >> Year;
                                  return Year;
                              }
                              short ReadMonth() {
                                  short Month;
                                  cout << "Please enter Month : ";
                                  cin >> Month;
                                  return Month;
                              }
                              short ReadDay() {
                                  short Day;
                                  cout << "Please enter Day : ";
                                  cin >> Day;
                                  return Day;
                              }
                              struct sDate {
                                  short year, month, day;
                              };
                              sDate ReadFullDate() {
                                  sDate Date;
                              
                                  Date.year = ReadYear();
                                  Date.month = ReadMonth();
                                  Date.day = ReadDay();
                              
                                  return Date;
                              }
                              bool isLeapYear(short Year) {  
                                  return (Year % 4 == 0 && Year % 100 != 0) || (Year % 400 == 0);
                              }
                              short NumberOfDaysInAMonth(short Month, short Year) 
                              { 
                                  if (Month < 1 || Month>12)
                                      return  0; 
                              
                                  int days[12] = { 31,isLeapYear(Year) ? 29 : 28,31,30,31,30,31,31,30,31,30,31 };
                              
                                  return days[ Month - 1];
                              }
                              
                              bool IsLastDayInMonth(sDate Date) {
                              
                                  return (Date.day == NumberOfDaysInAMonth(Date.month, Date.year));
                              
                              }
                              bool IsLastMonthInYear(short  month) {
                                  return (month == 12);
                              }
                              sDate IncreaseDateByOneDay(sDate Date) {
                              
                                  if (IsLastDayInMonth(Date)) {
                              
                                      if (IsLastMonthInYear(Date.month)) {
                                          Date.month = 1; 
                                          Date.day = 1;
                                          Date.year++; 
                                      }
                                      else {
                                          Date.day = 1; 
                                          Date.month++;
                                      }
                                  }
                                  else {
                                      Date.day++;
                                  }
                                  return Date;
                              }
                              int main()
                              {
                                  sDate Date = ReadFullDate();
                              
                                  Date = IncreaseDateByOneDay(Date);
                              
                              
                                  cout << "the new date is : " << Date.day << "/" << Date.month << "/" << Date.year << endl;
                              
                                  return 0;
                              }



## 134  Write a program to read date1 and date2 and make a function to calculate  the difference in days. 
## Date1 should be less than Date2 

                   
                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    short ReadYear() {
                        short Year;
                        cout << "Please enter year : ";
                        cin >> Year;
                        return Year;
                    }
                    short ReadMonth() {
                        short Month;
                        cout << "Please enter Month : ";
                        cin >> Month;
                        return Month;
                    }
                    short ReadDay() {
                        short Day;
                        cout << "Please enter Day : ";
                        cin >> Day;
                        return Day;
                    }
                    struct sDate {
                        short year, month, day;
                    };
                    sDate ReadFullDate() {
                        sDate Date;
                    
                        Date.year = ReadYear();
                        Date.month = ReadMonth();
                        Date.day = ReadDay();
                    
                        return Date;
                    }
                    bool isLeapYear(short Year) {  
                        return (Year % 4 == 0 && Year % 100 != 0) || (Year % 400 == 0);
                    }
                    short NumberOfDaysInAMonth(short Month, short Year) 
                    { 
                        if (Month < 1 || Month>12)
                            return  0; 
                    
                        int days[12] = { 31,isLeapYear(Year) ? 29 : 28,31,30,31,30,31,31,30,31,30,31 };
                    
                        return days[ Month - 1];
                    }
                    
                    short DifferneceBettwenTwoDates(sDate Date , sDate Date2) {
                    
                        short Diffrence = 0;
                    
                        if (Date.year > Date2.year)
                            Diffrence = Date.year - Date2.year; 
                        else
                            Diffrence = Date2.year - Date.year ;
                    
                        if(Date.month > Date2.month)
                            Diffrence += Date.month - Date2.month;
                        else
                            Diffrence += Date2.month - Date.month;
                    
                        if (Date.day > Date2.day)
                            Diffrence += Date.day - Date2.day;
                        else
                            Diffrence += Date2.day - Date.day;
                    
                        return Diffrence; 
                    
                    }
                    
                    int main()
                    {
                        sDate Date = ReadFullDate();
                        sDate Date2 = ReadFullDate();
                    
                        cout << "Diffrence (Including End Day ) is:" << DifferneceBettwenTwoDates(Date, Date2);
                    
                        return 0;
                    }





#       OOP  [Object Oriented Programming ] 


## 1-  class  
                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    class clsPerson {
                    private:
                    
                        int x = 5; 
                    public :
                        string FirstName, LastName;
                    
                        string FullName() {
                            return FirstName + " " + LastName;
                        }
                    
                    };
                    int main()
                    {
                        clsPerson Person1;
                    
                        Person1.FirstName = "Mustafa";
                        Person1.LastName = "Saad";
                    
                        cout << Person1.FullName() << endl;
                      
                        return 0;
                    }


## 2 - property set and get 

                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    class clsPerson {
                    private:
                    
                        string _FirstName, _LastName; 
                    public :
                      
                        void setFirstName(string name) {  // set property 
                    
                            _FirstName = name;
                        }
                    
                        string FirstName() {
                            return _FirstName;
                        }
                    
                        void setLastName(string name) {  // set property 
                    
                            _LastName = name;
                        }
                    
                        string LastName() {
                            return _LastName;
                        }
                    
                        string FullName() {
                            return   _FirstName + " " + _LastName;
                        }
                    
                    };
                    int main()
                    {
                        clsPerson Person1;
                    
                        Person1.setFirstName("Mustafa") ;
                        Person1.setLastName("Saad");
                    
                        cout << Person1.FullName() << endl;
                    
                      
                        return 0;
                    }


## 3 - Read Only property 
                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    class clsPerson {
                    private:
                    
                        string _FirstName, _LastName; 
                        short _ID = 10;
                    
                    public :
                      
                        void setFirstName(string name) {  // set property 
                    
                            _FirstName = name;
                        }
                    
                        string FirstName() {
                            return _FirstName;
                        }
                    
                        void setLastName(string name) {  // set property 
                    
                            _LastName = name;
                        }
                    
                        string LastName() {
                            return _LastName;
                        }
                    
                        string FullName() {
                            return   _FirstName + " " + _LastName;
                        }
                    
                        int ID() {  // Read only property Get 
                            return _ID;
                        }
                    };
                    int main()
                    {
                        clsPerson Person1;
                    
                        Person1.setFirstName("Mustafa") ;
                        Person1.setLastName("Saad");
                    
                        cout << Person1.FullName() << endl;
                        cout << "Id = " << Person1.ID();
                      
                        return 0;
                    }

## 4 - Property Set and Get through "=" 
                    
                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std;
                    
                    class clsPerson {
                    private:
                    
                        string _FirstName; 
                    
                    public :
                      
                        void setFirstName(string name) {  // set property 
                    
                            _FirstName = name;
                        }
                    
                        string GetFirstName() {
                            return _FirstName;
                        }
                    
                        __declspec(property(get = GetFirstName, put = setFirstName)) string FirstName;
                      
                    };
                    int main()
                    {
                        clsPerson Person1;
                    
                        Person1.FirstName = "Mustafa";
                        cout <<  Person1.FirstName;
                        
                    
                        return 0;
                    }
                    

## 5 - Calculator 

                    
                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std; 
                    
                    class clsCalcuator {
                    private:
                       
                        float _Number = 0 , _Result = 0 , _PreivseValue = 0 ;
                        string _LastOperation;
                    
                        bool _IsZero(float Number) {
                            return (Number == 0);
                        }
                    
                    public :
                      
                       
                        void Adding(float Number ) {
                            _Number = Number;
                            _PreivseValue = _Result;
                            _LastOperation = "Adding";
                            _Result += Number;
                           
                        }
                        void Subtraction(float Number) {
                            _Number = Number;
                            _PreivseValue = _Result;
                            _LastOperation = "Subtracting";
                            _Result -= Number;
                    
                        }
                        void Divide(float Number) {
                    
                            _Number = Number;
                    
                           if( _IsZero(Number) ){
                                Number = 1;
                            }
                    
                            _PreivseValue = _Result;
                            _LastOperation = "Dividing";
                            _Result /= Number;
                    
                    
                        }
                        void Mulitply(float Number) {
                    
                            _Number = Number;
                            _PreivseValue = _Result;
                            _LastOperation = "Multiplying";
                            _Result *= Number;
                    
                        }
                        float GetFinalResult() {
                            return _Result;
                        }
                        void Clear() {
                    
                            _Number = 0;
                            _PreivseValue = 0;
                            _LastOperation = "Clear";
                            _Result = 0;
                    
                        }
                        void CancelLastOperation() {
                    
                            _Number = 0;
                            _LastOperation = "Cancelling Last Operation";
                            _Result = _PreivseValue;
                    
                        }
                        void PrintResult() {
                           
                            cout << " the Result After " << _LastOperation << " " << _Number  << " is " << _Result << endl;
                        }
                        
                    
                    };
                    int main()
                    {
                        clsCalcuator Calcuator1;
                    
                        Calcuator1.Adding(1000);
                        Calcuator1.PrintResult();
                    
                        Calcuator1.Subtraction(10);
                        Calcuator1.PrintResult();
                    
                        Calcuator1.Mulitply(10);
                        Calcuator1.PrintResult();
                    
                        Calcuator1.Divide(10);
                        Calcuator1.PrintResult();
                    
                        Calcuator1.CancelLastOperation();
                        Calcuator1.PrintResult();
                    
                        Calcuator1.Clear();
                        Calcuator1.PrintResult();
                    
                    
                        return 0;
                    }


## 6 Copy Constructor 

                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std; 
                    
                    
                    class clsAddress {
                    private:
                        string _AddressLine1;
                        string _AddressLine2;
                        string _POBox;
                        string _ZipCode;
                    public:
                        clsAddress(string AddressLine1 , string AddressLine2, string POBox , string ZipCode ) {
                            _AddressLine1 = AddressLine1;
                            _AddressLine2 = AddressLine2;
                            _POBox = POBox;
                            _ZipCode = ZipCode;
                        }
                        // copy Constructor 
                      /*  clsAddress(clsAddress& old_obj ) {
                            _AddressLine1 = old_obj.AddressLine1();
                            _AddressLine2 = old_obj.AddressLine2();
                            _POBox = old_obj.PoBox();
                            _ZipCode = old_obj.ZipCode();
                        }*/
                        void setAddressLine1(string AddressLine1) {
                            _AddressLine1 = AddressLine1;
                        }
                        string AddressLine1() {
                            return _AddressLine1;
                        }
                        void setAddressLine2(string AddressLine2) {
                            _AddressLine2 = AddressLine2;
                        }
                        string AddressLine2() {
                            return _AddressLine2;
                        }
                        void setPoBox(string POBox) {
                            _POBox = POBox;
                        }
                        string PoBox() {
                            return _POBox;
                        }
                        void setZipCode(string ZipCode) {
                            _ZipCode = ZipCode;
                        }
                        string ZipCode() {
                            return _ZipCode;
                        }
                        void Print() {
                            cout << "\n Address Detalis: \n ";
                            cout << "__________________________";
                            cout << "\n AddressLine1 : " << _AddressLine1 << endl;
                            cout << "AddressLine2 : " << _AddressLine2 << endl;
                            cout << "POBox        : " << _POBox << endl;
                            cout << "ZipCode      : " << _ZipCode << endl;
                        }
                    };
                    int main()
                    {
                        clsAddress Address1("Queen Alia Street " , "B 303" ,"111213" , "555555555");
                        Address1.Print();
                        
                        clsAddress Address2 = Address1;
                        Address2.Print(); 
                    
                    
                        return 0;
                    }


## 7 Destructor 

                    
                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std; 
                    
                    
                    class clsPerson {
                    
                    public:
                        string FullName;
                    
                        clsPerson() {
                            FullName = "Mustafa Sad ";
                            cout << "\n hi , i'm constructor";
                        }
                        ~clsPerson() {
                            cout << "\n hi , i'm Destructor ";
                    
                        }
                        void fun1() {
                            clsPerson person1;
                        }
                        void fun2() {
                            clsPerson* Person2 = new clsPerson;
                            delete Person2;
                    
                        }
                    
                    };
                    
                    int main() 
                    {
                        
                        clsPerson obj; // إنشاء كائن للوصول إلى الدوال
                    
                        obj.fun1();  // استدعاء الدالة الأولى
                        obj.fun2();  // استدعاء الدالة الثانية
                    
                        return 0;
                    }


## 8 static members 

                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std; 
                    
                    
                    class clsA {
                    
                    public:
                        int var;
                        static int counter;
                        
                        clsA() {
                            counter++;
                        }
                        void Print() {
                            cout << "\n var = " << var << endl;
                            cout << "\n counter = " << counter;
                        }
                    
                    };
                    int clsA::counter = 0;
                    int main() 
                    {
                        
                        clsA A1, A2, A3;
                    
                        A1.var = 10;
                        A2.var = 20;
                        A3.var = 30;
                    
                        A1.Print();
                        A2.Print();
                        A3.Print();
                    
                        A1.counter = 500;
                        
                        cout << "\n after chaning \n";
                        
                        A1.Print();
                        A2.Print();
                        A3.Print();
                    
                        return 0;
                    }


## 9 Static method (function)

                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std; 
                    
                    
                    class clsA {
                    
                    public:
                        
                        static int Function1() {
                            return 10;
                        }
                        int Function2() {
                            return 20;
                        }
                    };
                    int main() 
                    {
                       cout << clsA::Function1() << endl;
                    
                       clsA A1, A2;
                    
                       cout << A1.Function1() << endl;
                       cout << A2.Function2() << endl;
                       cout << A1.Function2() << endl;
                    
                        return 0;
                    }


## 10 Exercise 


                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std; 
                    
                    
                    class clsPerson {
                    
                        string _FirstName, _LastName, _FullName, _Email, _Phone;
                        int _ID;
                    
                    public:
                    
                        clsPerson(int Id, string FirstName, string LastName, string FullName, string Email, string Phone) {
                            _ID = Id;
                            _FirstName = FirstName;
                            _LastName = LastName;
                            _FullName = FullName;
                            _Email = Email;
                            _Phone = Phone;
                        }
                    
                        // read only property  يعني اللي بره ميقدرش يعدل عليها 
                        int ID() {
                            return _ID;
                        }
                    
                        void setFristName(string FirstName) {
                            _FirstName = FirstName;
                        }
                        string FirstName() {
                            return _FirstName;
                        }
                        void setLastName(string LastName) {
                            _LastName = LastName;
                        }
                        string LastName() {
                            return _LastName;
                        }
                    
                        string FullName() {
                            return _FullName = _FirstName + " " + _LastName;
                        }
                        void setEmail(string Email) {
                            _Email = Email;
                        }
                        string Email() {
                            return _Email;
                        }
                    
                        void setPhone(string Phone) {
                            _Phone = Phone;
                        }
                        string Phone() {
                            return _Phone;
                        }
                    
                        void Print() {
                    
                            cout << "Info:" << endl;
                    
                            cout << "____________________________" << endl;
                            cout << "ID       :" << _ID << endl;
                            cout << "FirstName:" << _FirstName << endl;
                            cout << "LastName :" << _LastName << endl;
                            cout << "FullName :" << _FullName << endl;
                            cout << "Email    :" << _Email << endl;
                            cout << "Phone    :" << _Phone << endl;
                            cout << "____________________________";
                    
                        }
                    
                        void SendEmail(string Subject, string Body) {
                    
                            cout << endl;
                            cout << "the following messsage sent successfully to Email: " << _Email << endl;
                            cout << "Subject : " << Subject << endl;
                            cout << "Body : " << Body << endl;
                    
                        }
                        void SendSMS(string TextMessage) {
                            cout << "The following SMS sent successfully to phone: " << _Phone;
                            cout << "\n" << TextMessage << endl;
                        }
                    };
                    
                    
                    int main() 
                    {
                        
                        clsPerson Person1(10 , "Mustafa" ,"saad" , "Mustafa saad " , "My@mail.com" , "0128183109");
                        Person1.Print();
                    
                        Person1.SendEmail("Hi" , "How are you ? ");
                        Person1.SendSMS("How are you ? ");
                    
                        return 0;
                    }
                    

## 11 Inheritance 

     
                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    #include <iomanip>
                    using namespace std; 
                    
                    
                    class clsPerson {
                    
                        string _FirstName, _LastName, _FullName, _Email, _Phone;
                        int _ID;
                    
                    public:
                    
                        clsPerson(int Id, string FirstName, string LastName, string Email, string Phone) {
                            _ID = Id;
                            _FirstName = FirstName;
                            _LastName = LastName;
                            _Email = Email;
                            _Phone = Phone;
                        }
                    
                        // read only property  يعني اللي بره ميقدرش يعدل عليها 
                        int ID() {
                            return _ID;
                        }
                    
                        void setFristName(string FirstName) {
                            _FirstName = FirstName;
                        }
                        string FirstName() {
                            return _FirstName;
                        }
                        void setLastName(string LastName) {
                            _LastName = LastName;
                        }
                        string LastName() {
                            return _LastName;
                        }
                    
                        string FullName() {
                            return _FullName = _FirstName + " " + _LastName;
                        }
                        void setEmail(string Email) {
                            _Email = Email;
                        }
                        string Email() {
                            return _Email;
                        }
                    
                        void setPhone(string Phone) {
                            _Phone = Phone;
                        }
                        string Phone() {
                            return _Phone;
                        }
                    
                        void Print() {
                    
                            cout << "Info:" << endl;
                    
                            cout << "____________________________" << endl;
                            cout << "ID                          :" << _ID << endl;
                            cout << "FirstName                   :" << _FirstName << endl;
                            cout << "LastName                    :" << _LastName << endl;
                            cout << "FullName                    :" << FullName() << endl;
                            cout << "Email                       :" << _Email << endl;
                            cout << "Phone                       :" << _Phone << endl;
                           
                    
                        }
                    
                        void SendEmail(string Subject, string Body) {
                    
                            cout << endl;
                            cout << "the following messsage sent successfully to Email: " << _Email << endl;
                            cout << "Subject : " << Subject << endl;
                            cout << "Body : " << Body << endl;
                    
                        }
                        void SendSMS(string TextMessage) {
                            cout << "The following SMS sent successfully to phone: " << _Phone;
                            cout << "\n" << TextMessage << endl;
                        }
                    };
                    
                    
                    class clsEmployee : public clsPerson {
                    
                    
                    
                        string _Title, _Department;
                        float  _Salary;
                    public :
                    
                    
                        clsEmployee(int Id, string FirstName, string LastName, string Email, string Phone , string Title , string Department , 
                       float Salary )
                         : clsPerson(Id , FirstName , LastName , Email , Phone )
                        {
                            _Title = Title;
                            _Department = Department; 
                            _Salary = Salary;
                        }
                        void setTitle(string Title ) {
                            _Title = Title;
                        }
                        string Title() {
                            return _Title;
                        }
                    
                        void setSalary(float Salary) {
                            _Salary = Salary; 
                        }
                        float Salary() {
                            return _Salary;
                        }
                    
                        void setDepartment(string Department) {
                            _Department = Department;
                        }
                        string Department() {
                            return _Department;
                        }
                        // Function Overriding 
                        // ممكن اجيب القيم من الكلاس الاب الاصلي ولكن مقدرش اجيب الا الميمبر لكن البرايفت تورثها انما متقدرش تكتبها 
                        void Print() {
                            clsPerson::Print();
                    
                            cout << "Title                       :" << _Title << endl;
                            cout << "Department                  :" << _Department << endl;
                            cout << "Salary                      :" << _Salary << endl;
                           
                        }
                    
                    };
                    
                    class clsDeveloper :public clsEmployee {
                        string _ProgrammingLanguage;
                    
                    public:
                    
                    
                    
                        clsDeveloper(int Id, string FirstName, string LastName, string Email, string Phone, string Title, string Department, 
                    float Salary , string ProgrammingLanguage)
                            : clsEmployee(Id, FirstName, LastName, Email, Phone , Title, Department , Salary ) {
                    
                            _ProgrammingLanguage = ProgrammingLanguage; 
                        }
                    
                    
                        void SetProgrammingLanguage(string Pl) {
                            _ProgrammingLanguage = Pl;
                        }
                        string ProgrammingLanguage() {
                            return _ProgrammingLanguage;
                        }
                    
                        void Print() {
                    
                             clsEmployee::Print();
                             cout << "Main Progarmming Language   : " << ProgrammingLanguage() << endl;
                             cout << "____________________________";
                        }
                    
                    };
                    
                    int main() 
                    {
                        
                        clsDeveloper Developer1(10, "Mustafa " , "saad","a@.com","010234234","CEO","ProgrammingHero",5000 , "C#");
                    
                        Developer1.Print();
                    
                    
                    
                        return 0;
                    }

## 12 برنامج بيشوف القيمه اللي انت كاتبها لو رقم يطبعها لو لا بيرجع تاني يقولك اكتب الرقم مره اخري 

                    #include <iostream>
                    
                    using namespace std;
                    
                    int ReadNumber() {
                        int number;
                        cout << "Please enter number" << endl;
                        cin >> number;
                        while (cin.fail()) {
                    
                            cin.clear();
                            cin.ignore(std::numeric_limits<std::streamsize>::max(), '\n');
                            cout << "Invalid Number, Enter a valid one:" << endl;
                            cin >> number;
                    
                        }
                        return number;
                    
                    }
                     
                    int main()
                    {
                        
                        cout << "yes number is " << ReadNumber();
                         return 0;
                    }

                    
## 13 Two dimensional array

                    #include <iostream>
                    #include <iomanip>
                    using namespace std;
                    
                    int main()
                    {
                    	// int [row][cols];
                    	int x[10][10];
                    
                    	for (int i = 0; i < 10; i++) {
                    		for (int j = 0; j < 10; j++) {
                    			 x[i][j] = (i+1) * (j+1) ;
                    		}
                    		cout << endl;
                    	}
                    	for (int i = 0; i < 10; i++) {
                    		for (int j = 0; j < 10; j++) {
                    			printf("%0*d ", 2, x[i][j]);
                    		}
                    		cout << endl;
                    	}
                    	return 0;
                    }

## 14 - Add elements in vector 

                    #include <iostream>
                    #include <iomanip>
                    #include <vector>
                    using namespace std;
                    vector <int> ReadNumber(vector <int> &vNum) {
                    	
                    
                    	int Number;
                    	string check;
                    
                    	do {
                    
                    	cout << "Pleas enter number : ";
                    	cin >> Number;
                    	vNum.push_back(Number);
                    	
                    	cout << "Do you need enter more number? ";
                    	cin >> check;
                    	} while (check == "Yes" || check == "yes");
                    	
                    	return vNum;
                    }
                    void PrintNumbers(vector <int> &vNum ) {
                    
                    	cout << "vector Numbers" << endl;
                    
                    	for (int & Num : vNum) {
                    		cout << Num << " ";
                    
                    	}
                    	cout << endl;
                    }
                    int main()
                    {
                    	vector <int> vNum;
                    
                    	ReadNumber(vNum);
                    	PrintNumbers(vNum);
                    
                    }

## 15 - vector example 


                    #include <iostream>
                    #include <iomanip>
                    #include <vector>
                    using namespace std;
                    vector <int> ReadNumber(vector <int> &vNum) {
                    	
                    
                    	int Number;
                    	string check;
                    
                    	do {
                    
                    	cout << "Pleas enter number : ";
                    	cin >> Number;
                    	vNum.push_back(Number);
                    	
                    	cout << "Do you need enter more number? ";
                    	cin >> check;
                    	} while (check == "Yes" || check == "yes");
                    	
                    	return vNum;
                    }
                    void PrintNumbers(vector <int> &vNum ) {
                    
                    	cout << "vector Numbers" << endl;
                    
                    	for (int & Num : vNum) {
                    		cout << Num << " ";
                    
                    	}
                    	cout << endl;
                    }
                    int main()
                    {
                    	vector <int> vNum;
                    
                    	ReadNumber(vNum);
                    	PrintNumbers(vNum);
                    
                    }

## 16 -  Vector of Structure


                    #include <iostream>
                    #include <iomanip>
                    #include <vector>
                    using namespace std;
                    struct stEmployee {
                    	string firstName;
                    	string LastName;
                    	float Salary;
                    };
                    
                    vector <stEmployee>  ReadEmployee(vector <stEmployee> & vEmployee) {
                    
                    	stEmployee Employee;
                    	
                    	char check;
                    	do {
                    
                    	cout << "Please enter first name: ";
                    	cin >> Employee.firstName;
                    
                    	cout << "Please enter last name: ";
                    	cin >> Employee.LastName;
                    
                    	cout << "Please enter you Salary: ";
                    	cin >> Employee.Salary;
                    
                    	cout << "do you need add more employee (y/N)";
                    	cin >> check;
                    
                    	vEmployee.push_back(Employee);
                    
                    	} while (check == 'y' || check == 'Y');
                    	
                    
                    	return vEmployee;
                    }
                    
                    void PrintEmployees(vector <stEmployee>& vEmployee) {
                    
                    	cout << endl;
                    	for (stEmployee &Employees : vEmployee) {
                    		cout << "first name : " <<  Employees.firstName << endl;
                    		cout << "last name :" <<  Employees.LastName << endl;
                    		cout << "salary :" <<  Employees.Salary << endl;
                    	}
                    }
                    int main()
                    {
                    
                    	vector <stEmployee> vEmployee;
                    
                    	ReadEmployee(vEmployee);
                    	PrintEmployees(vEmployee);
                    
                    	return 0;
                    }

## 17 - Remove elements from vector 

                    
                    #include <iostream>
                    #include <iomanip>
                    #include <vector>
                    using namespace std;
                    
                    int main()
                    {
                    
                    	vector <int> vNumbers;
                    
                    	vNumbers.push_back(10);
                    	vNumbers.push_back(20);
                    	vNumbers.push_back(30);
                    	vNumbers.push_back(40);
                    
                    	cout << "Stack Size = " << vNumbers.size() << endl;
                    
                    	vNumbers.clear();
                    
                    	if (!vNumbers.empty())
                    		vNumbers.pop_back();
                    
                    	//if (vNumbers.size() > 0)
                    	//	vNumbers.pop_back();
                    
                    
                    	for (int Num : vNumbers) {
                    		cout << Num << endl;
                    	}
                    
                    	return 0;
                    }

## 18 - more function about vector 

                    #include <iostream>
                    #include <iomanip>
                    #include <vector>
                    using namespace std;
                    
                    int main()
                    {
                    
                    	vector <int> vNumbers;
                    
                    	vNumbers.push_back(10);
                    	vNumbers.push_back(20);
                    	vNumbers.push_back(30);
                    	vNumbers.push_back(40);
                    	vNumbers.push_back(5);
                    
                    	cout << "First Element : " << vNumbers.front() << endl;
                    	cout << "End Element : " << vNumbers.back() << endl;
                    
                    	cout << "Size : " << vNumbers.size() << endl;
                    	cout << "Capacity : " << vNumbers.capacity() << endl;
                    
                    	cout << "Empty : " << vNumbers.empty();
                    
                    
                    	return 0;
                    }

## 19 - by Refernce by value
                    
                    #include <iostream>
                    #include <iomanip>
                    #include <vector>
                    using namespace std;
                    
                    
                    int main()
                    {
                    	int a = 10;
                    	int& x = a;
                    
                    	cout << &a << endl;
                    	cout << &x << endl; //hexadecimal address; 
                    
                    	x = 20;
                    
                    	cout << a << endl;
                    	cout << x << endl;
                    
                    
                    	return 0;
                    }

## 20 - Write Mode: Write Data To File

                    #include <iostream>
                    #include <fstream>
                    using namespace std;
                    
                    int main()
                    {
                    	fstream MyFile;
                    
                    	MyFile.open("MyFile.txt", ios::out);
                    	
                    	if (MyFile.is_open()) {
                    		MyFile << "Hi , this is the first line\n";
                    		MyFile << "Hi , this is the second line\n";
                    		MyFile << "Hi , this is the third line\n";
                    
                    
                    		MyFile.close();
                    	}
                    	return 0;
                    }

## 21 -  Append Mode: Append Data to File



                    #include <iostream>
                    #include <fstream>
                    using namespace std;
                    
                    int main()
                    {
                    	fstream MyFile;
                    
                    
                    	MyFile.open("MyFile.txt",ios::out |  ios::app);  //append mode 
                    
                    	if (MyFile.is_open()) {
                    
                    		MyFile << "Mustafa sad mohammed mohammed" << endl;
                    		MyFile << "Mustafa sad mohammed mohammed" << endl;
                    		MyFile << "Mustafa sad mohammed mohammed" << endl;
                    		MyFile << "Mustafa sad mohammed mohammed" << endl;
                    
                    		MyFile.close();
                    	}
                    	return 0;
                    }

## 22 - Read Mode: Print File Content 


                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    using namespace std;
                    
                    void PrintFileContent(string FileName) {
                    	fstream MyFile;
                        
                    	MyFile.open(FileName, ios::in);// Read Mode
                    
                        if (MyFile.is_open()) {
                    			string Line; 
                    
                    			while (getline(MyFile, Line)) {
                    				cout << Line << endl;
                    			}
                    			MyFile.close();
                    	}
                    }
                    int main()
                    {
                    	PrintFileContent("MyFile.txt");
                    	return 0;
                    }


## 23 -  Load Data From File to Vector



                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    using namespace std;
                    
                    void LoadDataFromFileToVector(string FileName, vector <string> &vFile) {
                    	fstream MyFile;
                    
                    	MyFile.open(FileName, ios::in);// Read Mode
                    
                        if (MyFile.is_open()) {
                    			string Line; 
                    
                    			while (getline(MyFile, Line)) {
                    				vFile.push_back( Line );
                    			}
                    			MyFile.close();
                    	}
                    }
                    int main()
                    {
                    
                    	vector <string> vFile;
                    
                    	LoadDataFromFileToVector("MyFile.txt" , vFile);
                    
                    	for (string& Line : vFile) {
                    		cout << Line << endl;
                    	}
                    	return 0;
                    }

## 24 -  Save Vector to File

                    
                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    using namespace std;
                    
                    void SaveVectorToFile(string FileName, vector <string> vFileContent) {
                    	fstream MyFile;
                    
                    	MyFile.open(FileName, ios::out | ios::app);// append Mode
                    
                        if (MyFile.is_open()) {
                    			
                    		    for (string Line : vFileContent) {
                    
                    				if(Line != "")
                    			     MyFile << Line << endl;
                    			}
                    	         
                    			MyFile.close();
                    	}
                    }
                    int main()
                    {
                    
                    	vector <string> vFileContent{ "Ali" ,"Mohammed" , "Sad" , "Fadi" , "Lama" };
                    
                    	SaveVectorToFile("MyFile.txt" , vFileContent);
                    
                    	return 0;
                    }

## 25 - Delete Record From File


                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    using namespace std;
                    
                    void SaveVectorToFile(string FileName, vector <string>  vFileContent) {
                    	fstream MyFile;
                    
                    	MyFile.open(FileName, ios::out );// append Mode
                    
                        if (MyFile.is_open()) {
                    			
                    		    for (string Line : vFileContent) {
                    
                    				if(Line != "")
                    			     MyFile << Line << endl;
                    			}
                    	         
                    			MyFile.close();
                    	}
                    }
                    void LoadDataFromFile(string FileName , vector <string> & vFile) {
                    
                    	fstream MyFile;
                    	MyFile.open(FileName, ios::in);
                    
                    	if (MyFile.is_open()) {
                    
                    		string Line;
                    
                    		while (getline(MyFile, Line)) {
                    			vFile.push_back(Line);
                    		}
                    	}
                    }
                    void DeletRecordFromFile(string FileName, string Record) {
                    
                    	vector <string> vFile;
                    	LoadDataFromFile(FileName, vFile);
                    
                    	for ( string& Line : vFile) {
                    		if (Line == Record) {
                    
                    			Line = "";
                    		}
                    	}
                    	SaveVectorToFile(FileName, vFile);
                    }
                    void PrintFileContent(string FileName ) {
                    	fstream MyFile;
                    	MyFile.open(FileName, ios::in);
                    
                    	if (MyFile.is_open()) {
                    		string Line; 
                    		while (getline(MyFile,Line))
                    		{
                    			cout << Line << endl;
                    		}
                    		MyFile.close();
                    	}
                    }
                    int main()
                    {
                    
                    	cout << "File content Before Delete. \n";
                    	PrintFileContent("MyFile.txt");
                    	
                    	DeletRecordFromFile("MyFile.txt" , "Sad");
                    
                    	cout << "File content After Delete. \n";
                    	PrintFileContent("MyFile.txt");
                    
                    	return 0;
                    }

## 26 -  Update Record In File 


                    #include <iostream>
                    #include <fstream>
                    #include <string>
                    #include <vector>
                    using namespace std;
                    
                    void SaveVectorToFile(string FileName, vector <string>  vFileContent) {
                    	fstream MyFile;
                    
                    	MyFile.open(FileName, ios::out );// append Mode
                    
                        if (MyFile.is_open()) {
                    			
                    		    for (string Line : vFileContent) {
                    
                    				if(Line != "")
                    			     MyFile << Line << endl;
                    			}
                    	         
                    			MyFile.close();
                    	}
                    }
                    void LoadDataFromFile(string FileName , vector <string> & vFile) {
                    
                    	fstream MyFile;
                    	MyFile.open(FileName, ios::in);
                    
                    	if (MyFile.is_open()) {
                    
                    		string Line;
                    
                    		while (getline(MyFile, Line)) {
                    			vFile.push_back(Line);
                    		}
                    	}
                    }
                    void UpdateRecordFromFile(string FileName, string Record , string Record2) {
                    
                    	vector <string> vFile;
                    	LoadDataFromFile(FileName, vFile);
                      
                    	for ( string& Line : vFile) {
                    		if (Line == Record) {
                    
                    			Line = Record2;
                    		}
                    	}
                    	SaveVectorToFile(FileName, vFile);
                    }
                    void PrintFileContent(string FileName ) {
                    	fstream MyFile;
                    	MyFile.open(FileName, ios::in);
                    
                    	if (MyFile.is_open()) {
                    		string Line; 
                    		while (getline(MyFile,Line))
                    		{
                    			cout << Line << endl;
                    		}
                    		MyFile.close();
                    	}
                    }
                    int main()
                    {
                    
                    	cout << "File content Before Delete. \n";
                    	PrintFileContent("MyFile.txt");
                    	
                    	UpdateRecordFromFile("MyFile.txt" , "Lama" , "Mohammed");
                    
                    	cout << "File content After Delete. \n";
                    	PrintFileContent("MyFile.txt");
                    
                    	return 0;
                    }

## 27 - Write a program to fill a 3*3 matrix with random numbers

                                   
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    int RandomNumber(int From, int To) {
                    	
                    	int RandomNumber = rand() % (To - From + 
                        1) + From;
                    	return RandomNumber;
                    }
                    void FillMatrixWithRandomNumber(int arr[3][3],     
                    Row, short Col) {
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			arr[i][j] = 
                  RandomNumber(1, 100);
                    		}
                    	}
                    }
                    void PrintMatrix(int arr[3][3], short Row, short 
                       Col) {
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			cout << setw(3) << 
                     arr[i][j] << "   ";
                    		}
                    		cout << "\n";
                    	}
                    }
                    int main()
                    {
                    
                    	srand((unsigned)time(NULL));
                    	int arr[3][3]; 
                    
                    	FillMatrixWithRandomNumber(arr, 3, 3);
                    	PrintMatrix(arr, 3, 3);
                    
                    	return 0;
                    }

## 28 -- Write a program to fill a 3*3 matrix with random numbers, then print each row sum: 

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    int RandomNumber(int From, int To) {
                    	
                    	int RandomNumber = rand() % (To - From + 1) + From;
                    	return RandomNumber;
                    }
                    void FillMatrixWithRandomNumber(int arr[3][3], short Row, short Col) {
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			arr[i][j] = RandomNumber(1, 100);
                    		}
                    	}
                    }
                    void PrintMatrix(int arr[3][3], short Row, short Col) {
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			cout << setw(3) << arr[i][j] << "   ";
                    		}
                    		cout << "\n";
                    	}
                    }
                    void SumArr(int arr[3][3], short Row, short Col) {
                    
                    	for (int i = 0; i < Row; i++) {
                    		int Sum = 0;
                    		for (int j = 0; j < Col; j++) {
                    			Sum += arr[i][j];
                    		}
                    		cout << "Row " << i  << "Sum = " << Sum << endl;
                    		cout << "\n";
                    	}
                    }
                    int main()
                    {
                    
                    	srand((unsigned)time(NULL));
                    	int arr[3][3]; 
                    
                    	FillMatrixWithRandomNumber(arr, 3, 3);
                    	PrintMatrix(arr, 3, 3);
                    
                    	SumArr(arr, 3, 3);
                    
                    	return 0;
                    }

## 29 - Write a program to fill a 3*3 matrix with random numbers, then sum each row in a separate array and print the result :

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    int RandomNumber(int From, int To) {
                    	
                    	int RandomNumber = rand() % (To - From + 1) + From;
                    	return RandomNumber;
                    }
                    void FillMatrixWithRandomNumber(int arr[3][3], short Row, short Col) {
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			arr[i][j] = RandomNumber(1, 100);
                    		}
                    	}
                    }
                    void PrintMatrix(int arr[3][3], short Row, short Col) {
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			cout << setw(3) << arr[i][j] << "   ";
                    		}
                    		cout << "\n";
                    	}
                    }
                    void SumArr(int arr2[3], int arr[3][3], short Row, short Col) {
                    
                    	for (int i = 0; i < Row; i++) {
                    		int Sum = 0;
                    		for (int j = 0; j < Col; j++) {
                    			Sum += arr[i][j];
                    		}
                    		arr2[i] = Sum;
                    	}
                    }
                    void PrintSumArr(int arr2[3] , int Row ) {
                    	for (int i = 0; i < Row; i++) {
                    		cout << "Row " << i+1 << "Sum = " << arr2[i] << endl;
                    	}
                    }
                    int main()
                    {
                    
                    	srand((unsigned)time(NULL));
                    	int arr[3][3]; 
                    	int arr2[3];
                    
                    	FillMatrixWithRandomNumber(arr, 3, 3);
                    	PrintMatrix(arr, 3, 3);
                    
                        SumArr(arr2, arr, 3, 3);
                    	PrintSumArr(arr2, 3);
                    
                    	return 0;
                    }


## 30 - write a program to fill a 3*3 matrix with random numbers, then print each col sum.


                              #include <iostream>
                              #include <string>
                              #include <iomanip>
                              using namespace std;
                              
                              int RandomNumber(int From, int To) {
                              	
                              	int RandomNumber = rand() % (To - From + 1) + From;
                              	return RandomNumber;
                              }
                              void FillMatrixWithRandomNumber(int arr[3][3], short Row, short Col) {
                              	for (int i = 0; i < Row; i++) {
                              		for (int j = 0; j < Col; j++) {
                              			arr[i][j] = RandomNumber(1, 100);
                              		}
                              	}
                              }
                              void PrintMatrix(int arr[3][3], short Row, short Col) {
                              	for (int i = 0; i < Row; i++) {
                              		for (int j = 0; j < Col; j++) {
                              			cout << setw(3) << arr[i][j] << "   ";
                              		}
                              		cout << "\n";
                              	}
                              }
                              void SumArrCols(int arr2[3], int arr[3][3], short Row, short Col) {
                              
                              	for (int i = 0; i < Row; i++) {
                              		int Sum = 0;
                              		for (int j = 0; j < Col; j++) {
                              			Sum += arr[j][i];
                              		}
                              		arr2[i] = Sum;
                              	}
                              }
                              void PrintSumArr(int arr2[3] , int Col ) {
                              	for (int i = 0; i < Col; i++) {
                              		cout << "cols " << i+1 << "Sum = " << arr2[i] << endl;
                              	}
                              }
                              int main()
                              {
                              
                              	srand((unsigned)time(NULL));
                              	int arr[3][3]; 
                              	int arr2[3];
                              
                              	FillMatrixWithRandomNumber(arr, 3, 3);
                              	PrintMatrix(arr, 3, 3);
                              
                              	SumArrCols(arr2, arr, 3, 3);
                              
                              	cout << "The following are the sum of each col in the matrix: " << endl;
                              	PrintSumArr(arr2, 3);
                              
                              	return 0;
                              }

## 31 - write aa program to fill a 3*3 orderd matrix:

                                        
                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    
                    void FillMatrixWithRandomNumber(int arr[3][3], short Row, short Col) {
                    
                    	int Counter = 0 ;
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			Counter++;
                    			arr[i][j] = Counter;
                    		}
                    	}
                    }
                    void PrintMatrix(int arr[3][3], short Row, short Col) {
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			cout << setw(3) << arr[i][j] << "   ";
                    		}
                    		cout << "\n";
                    	}
                    }
                    
                    int main()
                    {
                    
                    	srand((unsigned)time(NULL));
                    	int arr[3][3]; 
                    	int arr2[3];
                    
                    	FillMatrixWithRandomNumber(arr, 3, 3);
                    	PrintMatrix(arr, 3, 3);
                    
                    	return 0;
                    }

## 32 - write a program to fill a 3*3 matrix with orderd numbers and print it , then transpose matrix and print it.


                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    
                    void FillMatrixWithRandomNumber(int arr[3][3], short Row, short Col) {
                    
                    	int Counter = 0 ;
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			Counter++;
                    			arr[i][j] = Counter;
                    		}
                    	}
                    }
                    void PrintMatrix(int arr[3][3], short Row, short Col) {
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			cout << setw(3) << arr[i][j] << "   ";
                    		}
                    		cout << "\n";
                    	}
                    }
                    void ReverseMatrix(int arr2[3][3] , int arr[3][3], short Row, short Col) {
                    
                    	
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			arr2[i][j] = arr[j][i];
                    		}
                    	}
                    }
                    void PrintReverseMatrix(int arr2[3][3], short Row, short Col) {
                    
                    	cout << "The Rverse Matrix" << endl;
                    	for (int i = 0; i < Row; i++) {
                    		for (int j = 0; j < Col; j++) {
                    			cout << setw(3) <<  arr2[i][j] << "   ";
                    		}
                    		cout << endl;
                    	}
                    }
                    int main()
                    {
                    
                    	int arr[3][3]; 
                    
                    	int arr2[3][3];
                    
                    	FillMatrixWithRandomNumber(arr, 3, 3);
                    	PrintMatrix(arr, 3, 3);
                    
                    	ReverseMatrix(arr2, arr, 3, 3);
                    
                    	PrintReverseMatrix(arr2, 3, 3);
                    
                    	return 0;
                    }

## 33 - write a program to read a string then print the first letter of each word in that string 


                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    string  ReadName() {
                    	 
                    	string name;
                    	cout << "Please Enter your name ? " << endl;
                    	getline(cin  ,name); 
                    	return name;
                    }
                    //void FirstLetterInName() {
                    //
                    //	string name = ReadName();
                    //
                    //	cout << "the first letter in string " << endl;
                    //
                    //	for (int i = 0; i < name.length(); i++) {
                    //		if (name[i] == ' ') {
                    //			cout << name[i + 1] << endl;
                    //		}
                    //	}
                    //}
                    
                    void PrintFirstLetterOfEachWord(string S1) {
                    	
                    	bool IsFirstLetter = true; 
                    
                    	cout << "\n First Letter Of this string : \n";
                    	 
                    	for (short i = 0; i < S1.length(); i++) {
                    		if (S1[i] != ' ' && IsFirstLetter) {
                    			cout << S1[i] << endl;
                    		}
                    		IsFirstLetter = (S1[i] == ' ' ? true : false);
                    	}
                    }
                    int main()
                    {
                    
                    	PrintFirstLetterOfEachWord(ReadName());
                    
                    	return 0;
                    }


## 34 - write a program to read a stringg then uppercase the first letter of each word in that string :


                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    string  ReadName() {
                    	 
                    	string name;
                    	cout << "Please Enter your name ? " << endl;
                    	getline(cin  ,name); 
                    	return name;
                    }
                    
                    string UpperFirstLetterOfEachWord(string S1) {
                    	
                    	bool IsFirstLetter = true; 
                    
                    	 
                    	for (short i = 0; i < S1.length(); i++) {
                    		if (S1[i] != ' ' && IsFirstLetter) {
                    			S1[i] = toupper(S1[i]) ;
                    		}
                    		IsFirstLetter = (S1[i] == ' ' ? true : false);
                    	}
                    	return S1;
                    }
                    int main()
                    {
                    
                    	string Name = ReadName();
                    	Name = UpperFirstLetterOfEachWord(Name);
                    
                    	cout << "String after conversion : \n";
                    	cout << Name << endl;
                    
                    	return 0;
                    }
                    
## 35 - write a program to read a stringg then LowerCase the first letter of each word in that string :



                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    string  ReadName() {
                    	 
                    	string name;
                    	cout << "Please Enter your name ? " << endl;
                    	getline(cin  ,name); 
                    	return name;
                    }
                    
                    string UpperFirstLetterOfEachWord(string S1) {
                    	
                    	bool IsFirstLetter = true; 
                    
                    	 
                    	for (short i = 0; i < S1.length(); i++) {
                    		if (S1[i] != ' ' && IsFirstLetter) {
                    			S1[i] = tolower(S1[i]) ;
                    		}
                    		IsFirstLetter = (S1[i] == ' ' ? true : false);
                    	}
                    	return S1;
                    }
                    int main()
                    {
                    
                    	string Name = ReadName();
                    	Name = UpperFirstLetterOfEachWord(Name);
                    
                    	cout << "String after conversion : \n";
                    	cout << Name << endl;
                    
                    	return 0;
                    }


## 36 - write a program to read a string then upper all letters, then lower all letters , and print them.



                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    using namespace std;
                    
                    string  ReadName() {
                    	 
                    	string name;
                    	cout << "Please Enter your name ? " << endl;
                    	getline(cin  ,name); 
                    	return name;
                    }
                    
                    string UpperFirstLetterOfEachWord(string S1) {
                    	
                    	cout << "String After Upper" << endl;
                    	for (short i = 0; i < S1.length(); i++) {
                    		if (S1[i] != ' ' ) {
                    			S1[i] = toupper(S1[i]) ;
                    		}
                    	}
                    	return S1;
                    }
                    
                    string LowerFirstLetterOfEachWord(string S1) {
                    
                    	cout << endl;
                    
                    	cout << "String After Upper" << endl;
                    	for (short i = 0; i < S1.length(); i++) {
                    		if (S1[i] != ' ') {
                    			S1[i] = tolower(S1[i]);
                    		}
                    	}
                    	return S1;
                    }
                    int main()
                    {
                    
                    	string Name = ReadName();
                        
                    	cout << UpperFirstLetterOfEachWord(Name);
                    
                    	cout << LowerFirstLetterOfEachWord(Name);
                    
                    	return 0;
                    }

## 37 - writ ea program to read bank client data record and convert it ot on line:


                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    using namespace std;
                    
                    struct stClient {
                        string AccountNumber;
                        string PinCode;
                        string Name;
                        string Phone;
                        double AccountBalance;
                    };
                    
                    // Function to read client data
                    stClient ReadClientData() {
                        stClient sClient;
                    
                        // Use getline for all string inputs to avoid mixing with cin
                        cout << "Please enter account number: ";
                        getline(cin, sClient.AccountNumber);
                    
                        cout << "Please enter pin code: ";
                        getline(cin, sClient.PinCode);
                    
                        cout << "Please enter name: ";
                        getline(cin, sClient.Name);
                    
                        cout << "Please enter phone: ";
                        getline(cin, sClient.Phone);
                    
                        cout << "Please enter account balance: ";
                        cin >> sClient.AccountBalance;
                    
                        return sClient;
                    }
                    
                    // Function to convert client data to a delimited record string
                    string ConvertLineToRecord(const stClient& sClient, const string& Delim) {
                        string Record = "";
                    
                        // Construct the delimited string for the client
                        Record += sClient.AccountNumber + Delim;
                        Record += sClient.PinCode + Delim;
                        Record += sClient.Name + Delim;
                        Record += sClient.Phone + Delim;
                        Record += to_string(sClient.AccountBalance);
                    
                        return Record;
                    }
                    
                    int main() {
                        // Read client data
                        stClient sClient = ReadClientData();
                    
                        // Convert client data to delimited record
                        string record = ConvertLineToRecord(sClient, "#//#");
                    
                        // Display the record
                        cout << "Client record for saving is:\n" << record << endl;
                    
                        return 0;
                    }


## 38 - Write a program to convert line data to record and print it:

                    
                   #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    using namespace std;
                    
                    struct stClient {
                        string Name, PinCode, AccountNumber, Phone;
                        double AccountBalance;
                    };
                    
                    vector <string> SplitString(string S1, string Delim) {
                        size_t Pos = 0;  // تعديل نوع المتغير إلى size_t
                        string Word;
                        vector<string> vString;
                    
                        while ((Pos = S1.find(Delim)) != std::string::npos) {
                            Word = S1.substr(0, Pos);
                            if (!Word.empty()) {
                                vString.push_back(Word);
                            }
                            S1.erase(0, Pos + Delim.length());
                        }
                    
                        if (!S1.empty()) {
                            vString.push_back(S1);
                        }
                    
                        return vString;
                    }
                    
                    stClient ConvertLineToRecord(string S1, string Delim = "#//#") {
                        stClient sClient;
                    
                        vector<string> vString = SplitString(S1, Delim);
                    
                        sClient.AccountNumber = vString[0];
                        sClient.PinCode = vString[1];
                        sClient.Name = vString[2];
                        sClient.Phone = vString[3];
                        sClient.AccountBalance = stod(vString[4]);
                    
                        return sClient;
                    }
                    
                    void PrintRecord(stClient sClient) {
                        cout << "Account Number: " << sClient.AccountNumber << endl;
                        cout << "PinCode: " << sClient.PinCode << endl;
                        cout << "Name: " << sClient.Name << endl;
                        cout << "Phone: " << sClient.Phone << endl;
                        cout << "Account Balance: " << sClient.AccountBalance << endl;
                    }
                    
                    int main() {
                        // مثال لنص مفصول
                        string stLine = "A150#//#1234#//#Mohammed Abu-Hadhoud#//#079999#//#5270.000000";
                    
                        // تحويل النص إلى سجل عميل
                        stClient sClient = ConvertLineToRecord(stLine, "#//#");
                    
                        // طباعة سجل العميل
                        PrintRecord(sClient);
                    
                        return 0;
                    }
                    

## 39 - Write a program to ask you to enter clients and save them to a file:

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    struct stClient {
                        string Name, PinCode, AccountNumber, Phone;
                        double AccountBalance;
                    };
                    
                    stClient ReadClient() {
                        stClient sClient;
                    
                        cout << "Enter Account Number: ";
                        getline(cin >> ws, sClient.AccountNumber);
                    
                        cout << "Enter PinCode: ";
                        getline(cin, sClient.PinCode);
                    
                        cout << "Enter Name: ";
                        getline(cin, sClient.Name);
                    
                        cout << "Enter Phone: ";
                        getline(cin, sClient.Phone);
                    
                        cout << "Enter Account Balance: ";
                        cin >> sClient.AccountBalance;
                    
                       
                        
                        return sClient;
                    }
                    
                    string ConvertRecordToLine(const stClient& sClient, const string& Delim) {
                        string Record = "";
                    
                        // Construct the delimited string for the client
                        Record += sClient.AccountNumber + Delim;
                        Record += sClient.PinCode + Delim;
                        Record += sClient.Name + Delim;
                        Record += sClient.Phone + Delim;
                        Record += to_string(sClient.AccountBalance);
                    
                        return Record;
                    }
                    
                    void SaveRecord(const stClient& sClient) {
                    
                        string Record = ConvertRecordToLine(sClient, "#//#");
                    
                        fstream MyFile;
                        MyFile.open("MyFile.txt", ios::app);
                    
                        if (MyFile.is_open()) {
                            MyFile << Record << endl;
                            MyFile.close();
                            cout << "Client Added Successfully." << endl;
                        }
                        else {
                            cout << "Failed to open file for writing." << endl;
                        }
                    }
                    
                    void AddClients() {
                        char AddMore = 'Y';
                    
                        do {
                            
                            system("cls");
                            cout << "Adding New Client:\n\n";
                    
                            SaveRecord(ReadClient());
                    
                            cout << "Client Added Successfully, do you want to add more Clients (Y/N)? ";
                            cin >> AddMore;
                    
                    
                        } while (tolower(AddMore) == 'Y');
                    }
                    
                    int main() {
                        AddClients();
                    
                        return 0;
                    }


## 40 - write a program to read clients file and show them on the screen as follows:

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    struct stClient {
                        string Name, PinCode, AccountNumber, Phone;
                        double AccountBalance;
                    };
                    
                    // دالة تقسيم النص باستخدام محدد معين
                    vector<string> SplitString(string S1, string Delim) {
                        size_t Pos = 0;
                        string Word;
                        vector<string> vString;
                    
                        while ((Pos = S1.find(Delim)) != std::string::npos) {
                            Word = S1.substr(0, Pos);
                            if (!Word.empty()) {
                                vString.push_back(Word);
                            }
                            S1.erase(0, Pos + Delim.length());
                        }
                    
                        if (!S1.empty()) {
                            vString.push_back(S1);
                        }
                    
                        return vString;
                    }
                    
                    // دالة تحويل السطر من الملف إلى سجل عميل
                    stClient ConvertLineToRecord(string S1, string Delim = "#//#") {
                        stClient sClient;
                        vector<string> vString = SplitString(S1, Delim);
                    
                        sClient.AccountNumber = vString[0];
                        sClient.PinCode = vString[1];
                        sClient.Name = vString[2];
                        sClient.Phone = vString[3];
                        sClient.AccountBalance = stod(vString[4]);
                    
                        return sClient;
                    }
                    
                    // دالة تحميل بيانات العملاء من الملف
                    vector<stClient> LoadClientsDataFromFile() {
                        vector<stClient> vClients;
                        fstream MyFile;
                        MyFile.open("MyFile.txt", ios::in);
                    
                        if (MyFile.is_open()) {
                            string Line;
                            stClient sClient;
                            while (getline(MyFile, Line)) {
                                sClient = ConvertLineToRecord(Line);
                                vClients.push_back(sClient);
                            }
                            MyFile.close();
                        }
                        return vClients;
                    }
                    
                    // دالة لطباعة بيانات عميل واحد
                    void PrintClientRecord(stClient Client) {
                        cout << "| " << setw(15) << left << Client.AccountNumber;
                        cout << "| " << setw(10) << left << Client.PinCode;
                        cout << "| " << setw(40) << left << Client.Name;
                        cout << "| " << setw(12) << left << Client.Phone;
                        cout << "| " << setw(12) << left << fixed << setprecision(2) << Client.AccountBalance;
                        cout << "|" << endl;
                    }
                    
                    // دالة لطباعة جميع بيانات العملاء في جدول
                    void PrintAllClientsData(vector<stClient> vClients) {
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
                    
                        for (stClient Client : vClients) {
                            PrintClientRecord(Client);
                        }
                    
                        cout << "\n_______________________________________________________";
                        cout << "_________________________________________\n" << endl;
                    }
                    
                    int main() {
                        vector<stClient> vClients = LoadClientsDataFromFile();
                        PrintAllClientsData(vClients);
                    
                        return 0;
                    }

## 41 - write a program to find client by account number and print it to the screen:

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    struct stClient {
                        string Name, PinCode, AccountNumber, Phone;
                        double AccountBalance;
                    };
                    
                    // دالة تقسيم النص باستخدام محدد معين
                    vector<string> SplitString(string S1, string Delim) {
                        size_t Pos = 0;
                        string Word;
                        vector<string> vString;
                    
                        while ((Pos = S1.find(Delim)) != std::string::npos) {
                            Word = S1.substr(0, Pos);
                            if (!Word.empty()) {
                                vString.push_back(Word);
                            }
                            S1.erase(0, Pos + Delim.length());
                        }
                    
                        if (!S1.empty()) {
                            vString.push_back(S1);
                        }
                    
                        return vString;
                    }
                    
                    // دالة تحويل السطر من الملف إلى سجل عميل
                    stClient ConvertLineToRecord(string S1, string Delim = "#//#") {
                        stClient sClient;
                        vector<string> vString = SplitString(S1, Delim);
                    
                        sClient.AccountNumber = vString[0];
                        sClient.PinCode = vString[1];
                        sClient.Name = vString[2];
                        sClient.Phone = vString[3];
                        sClient.AccountBalance = stod(vString[4]);
                    
                        return sClient;
                    }
                    
                    // دالة تحميل بيانات العملاء من الملف
                    vector<stClient> LoadClientsDataFromFile() {
                        vector<stClient> vClients;
                        fstream MyFile;
                        MyFile.open("MyFile.txt", ios::in);
                    
                        if (MyFile.is_open()) {
                            string Line;
                            stClient sClient;
                            while (getline(MyFile, Line)) {
                                sClient = ConvertLineToRecord(Line);
                                vClients.push_back(sClient);
                            }
                            MyFile.close();
                        }
                        return vClients;
                    }
                    string ReadClientAccountNumber() {
                    
                        string AccountNumber;
                    
                        cout << "Please Enter AccountNumber?";
                        cin >> AccountNumber;
                    
                        return AccountNumber;
                    
                    }
                    bool FindClientByAccountNumber(string AccountNumber, stClient& Client) {
                    
                        vector<stClient> vClients = LoadClientsDataFromFile();
                    
                        for (stClient c : vClients) {
                            if (AccountNumber == c.AccountNumber) {
                                Client = c;
                                return true;
                            }
                        }
                        return false;
                    }
                    
                    void PrintCard(stClient Client) {
                        cout << "\nThe following are the client details:\n";   
                        cout << "\nAccout Number: " << Client.AccountNumber;    
                        cout << "\nPin Code     : " << Client.PinCode;   
                        cout << "\nName         : " << Client.Name;  
                        cout << "\nPhone        : " << Client.Phone;  
                        cout << "\nAccount Balance: " << Client.AccountBalance;
                       
                    }
                    
                    int main() {
                    
                        stClient Client;
                        vector<stClient> vClients = LoadClientsDataFromFile();
                    
                        string AccountNumber =   ReadClientAccountNumber();
                        if (FindClientByAccountNumber(AccountNumber, Client)) 
                        {
                            PrintCard(Client);
                        }
                        else 
                        {
                            cout << "\nClient with Account Number (" << AccountNumber << ") is Not Found!";
                        }
                       
                        return 0;
                    }

## 42 - class 

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    class clsPerson {
                    private: 
                        int x = 0;
                    public: 
                    
                        string FristName, LastName;
                    
                        string FullName() {
                    
                            return FristName + " " + LastName; 
                        }
                    };
                    
                    int main() {
                    
                        clsPerson Person1;
                        
                        Person1.FristName = "Mustafa";
                        Person1.LastName = "Abu-Hadhoud";
                    
                        cout << Person1.FullName() << endl;
                    
                        
                        return 0;
                    }

## 43 -  Constructors

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    class clsAddress {
                    
                    private:
                    
                        string _AddressLine1;
                        string _AddressLine2;
                        string _POBox;
                        string _ZipCode;
                    
                    public:
                    
                        // constructors 
                    
                       clsAddress(string AddressLine1 , string AddressLine2 , string POBox , string ZipCode) {
                    
                            _AddressLine1 = AddressLine1;
                            _AddressLine2 = AddressLine2;
                            _POBox = POBox; 
                            _ZipCode = ZipCode; 
                        }
                        void SetAddressLine1(string AddressLine1) {
                            _AddressLine1 = AddressLine1;
                        }
                        string AddressLine1() {
                            return  _AddressLine1;
                        }
                        void SetAddressLine2(string AddressLine2) {
                            _AddressLine2 = AddressLine2;
                        }
                        string AddressLine2() {
                            return  _AddressLine2;
                        }
                        void SetPOBox(string POBox) {
                            _POBox = POBox;
                        }
                        string POBox() {
                            return  _POBox;
                        }
                        void SetZipCode(string ZipCode) {
                            _ZipCode = ZipCode;
                        }
                        string ZipCode() {
                            return  _ZipCode;
                        }
                        void Print() {
                            cout << "\nAddress Details:\n"; 
                            cout << "----------------------------";
                            cout << "\nAddressLine1: " << _AddressLine1 << endl;
                            cout << "AddressLine2: " << _AddressLine2 << endl;
                            cout << "POBox : " << _POBox << endl;
                            cout << "ZipCode : " << _ZipCode << endl;
                        }
                    };
                    
                    int main() {
                         
                        clsAddress Address1("mansoura", "MitGamer", "b 330", "234w3");
                    
                        Address1.Print();
                       cout <<  Address1.POBox();
                       
                        return 0;
                    }

## 44 - Destructors


                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    class clsAddress {
                    
                    private:
                    
                        string _AddressLine1;
                        string _AddressLine2;
                        string _POBox;
                        string _ZipCode;
                    
                    public:
                    
                        // constructors (بناء) 
                    
                       clsAddress(string AddressLine1 , string AddressLine2 , string POBox , string ZipCode) {
                    
                            _AddressLine1 = AddressLine1;
                            _AddressLine2 = AddressLine2;
                            _POBox = POBox; 
                            _ZipCode = ZipCode; 
                        }
                       ~clsAddress(){  // example for Destrouctor (تدمير )
                           cout << "\n Hi , I'm Constructor ";
                       }
                        void SetAddressLine1(string AddressLine1) {
                            _AddressLine1 = AddressLine1;
                        }
                        string AddressLine1() {
                            return  _AddressLine1; 
                        }
                        void SetAddressLine2(string AddressLine2) {
                            _AddressLine2 = AddressLine2;
                        }
                        string AddressLine2() {
                            return  _AddressLine2;
                        }
                        void SetPOBox(string POBox) {
                            _POBox = POBox;
                        }
                        string POBox() {
                            return  _POBox;
                        }
                        void SetZipCode(string ZipCode) {
                            _ZipCode = ZipCode;
                        }
                        string ZipCode() {
                            return  _ZipCode;
                        }
                        void Print() {
                            cout << "\nAddress Details:\n"; 
                            cout << "----------------------------";
                            cout << "\nAddressLine1: " << _AddressLine1 << endl;
                            cout << "AddressLine2: " << _AddressLine2 << endl;
                            cout << "POBox : " << _POBox << endl;
                            cout << "ZipCode : " << _ZipCode << endl;
                        }
                    };
                    
                    int main() {
                         
                        clsAddress Address1("mansoura", "MitGamer", "b 330", "234w3");
                    
                        Address1.Print();
                       cout <<  Address1.POBox();
                       
                        return 0;
                    }

## 45 - static method 

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    class clsA {
                    public:
                    	static int fun1() {
                    		return 10;
                    	}
                    	int fun2() {
                    		return  20;
                    	}
                    
                    };
                    
                    int main() {
                       
                    	cout << clsA::fun1() << endl;
                    	//cout << clsA::fun2() << endl;     Error 
                    	
                    	clsA A1, A2; 
                    
                    	cout << A1.fun1() << endl;
                    	cout << A1.fun2() << endl;
                    
                    	return 0;
                    }

## 46 - 

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    class clsPerson {
                    private:
                    	int _ID ;
                    	string _FirstName, _LastName, _Email, _Phone;
                    
                    
                    public:
                    
                    	clsPerson(int ID , string FirstName ,string  LastName ,string  Email ,string Phone){
                    		_ID = ID; 
                    		_FirstName = FirstName; 
                    		_LastName = LastName; 
                    		_Email = Email; 
                    		_Phone = Phone; 
                    	}
                    	int ID() {
                    		return _ID;
                    	}
                    	void SetFirstName(string FirstName) {
                    		_FirstName = FirstName;
                    	}
                    	string FirstName() {
                    		return _FirstName;
                    	}
                    	void SetLastName(string LastName) {
                    		_LastName = LastName;
                    	}
                    	string LastName() {
                    		return _LastName;
                    	}
                    	void SetEmail(string Email) {
                    		_Email = Email;
                    	}
                    	string Email() {
                    		return _Email;
                    	}
                    	void SetPhone(string Phone) {
                    		_Phone = Phone;
                    	}
                    	string Phone() {
                    		return _Phone;
                    	}
                    
                    	void Print() {
                    		cout << "Info:" << endl;
                    		cout << "___________________________" << endl;
                    		cout << "ID		:" << _ID << endl;
                    		cout << "FirstName:" << _FirstName << endl;
                    		cout << "LastName:" << _LastName << endl;
                    		cout << "FullName:" <<  FirstName() + LastName() << endl;
                    		cout << "Email:" << _Email << endl;
                    		cout << "Phone:" << _Phone << endl;
                    		cout << "----------------------------" << endl;
                    
                    	}
                    	void SendEmail(string Subject , string Body) {
                    		cout << "The following message sent successfully to email : " << _Email << endl;
                    		cout << "Subject: " << Subject << endl;
                    		cout << "Body: " << Body <<  endl;
                    
                    
                    	}
                    	void SendSms(string Body) {
                    		cout << "The following sms sent successfully to phone: " << _Phone << endl;
                    		cout << Body << endl;
                    
                    	}
                    
                    };
                    
                    int main() {
                    	clsPerson Person1(10, "Mustafa", "Saad", "@yahoo.com", "0102439534");
                    	Person1.Print();
                    
                    	Person1.SendEmail("Hi", "How are you? ");
                    	Person1.SendSms("How are you?");
                    	return 0;
                    }
## 47- Third Principle/Concept of OOP: Inheritance 

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    class clsPerson {
                    private:
                    	int _ID ;
                    	string _FirstName, _LastName, _Email, _Phone;
                    
                    
                    public:
                    
                    	clsPerson(){
                    
                    	}
                    	clsPerson(int ID , string FirstName ,string  LastName ,string  Email ,string Phone){
                    		_ID = ID; 
                    		_FirstName = FirstName; 
                    		_LastName = LastName; 
                    		_Email = Email; 
                    		_Phone = Phone; 
                    	}
                    	int ID() {
                    		return _ID;
                    	}
                    	void SetFirstName(string FirstName) {
                    		_FirstName = FirstName;
                    	}
                    	string FirstName() {
                    		return _FirstName;
                    	}
                    	void SetLastName(string LastName) {
                    		_LastName = LastName;
                    	}
                    	string LastName() {
                    		return _LastName;
                    	}
                    	void SetEmail(string Email) {
                    		_Email = Email;
                    	}
                    	string Email() {
                    		return _Email;
                    	}
                    	void SetPhone(string Phone) {
                    		_Phone = Phone;
                    	}
                    	string Phone() {
                    		return _Phone;
                    	}
                    
                    	void Print() {
                    		cout << "Info:" << endl;
                    		cout << "___________________________" << endl;
                    		cout << "ID		:" << _ID << endl;
                    		cout << "FirstName:" << _FirstName << endl;
                    		cout << "LastName:" << _LastName << endl;
                    		cout << "FullName:" <<  FirstName() + LastName() << endl;
                    		cout << "Email:" << _Email << endl;
                    		cout << "Phone:" << _Phone << endl;
                    		cout << "----------------------------" << endl;
                    
                    	}
                    	void SendEmail(string Subject , string Body) {
                    		cout << "The following message sent successfully to email : " << _Email << endl;
                    		cout << "Subject: " << Subject << endl;
                    		cout << "Body: " << Body <<  endl;
                    
                    
                    	}
                    	void SendSms(string Body) {
                    		cout << "The following sms sent successfully to phone: " << _Phone << endl;
                    		cout << Body << endl;
                    
                    	}
                    
                    };
                    class clsEmployee : public clsPerson {
                    private:
                    	string _Title;
                    	float  _Salary;
                    	string _Department;
                    public:
                    	void SetTitle(string Title) {
                    		_Title = Title;
                    	}
                    	string Title() {
                    		return _Title;
                    	}	
                    	void SetDepartment(string Department) {
                    		_Department = Department;
                    	}
                    	string Department() {
                    		return _Department;
                    	}
                    	void SetSalary(float Salary) {
                    		_Salary = Salary;
                    	}
                    	float Salary() {
                    		return _Salary;
                    	}
                    };
                    int main() {
                    	clsPerson Person1(10, "Mustafa", "Saad", "@yahoo.com", "0102439534");
                    	Person1.Print();
                    
                    	Person1.SendEmail("Hi", "How are you? ");
                    	Person1.SendSms("How are you?");
                    	
                    
                    	clsEmployee Employee1;
                    
                    	Employee1.SendEmail("Hi", "How are you? ");
                    	Employee1.SendSms("How are you?");
                    
                    	Employee1.SetSalary(500);
                    	cout << endl << Employee1.Salary();
                    
                    	return 0;
                    }

## 48 -  Function Overriding 

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    class clsPerson {
                    private:
                    	int _ID ;
                    	string _FirstName, _LastName, _Email, _Phone;
                    
                    
                    public:
                    	
                    	clsPerson(int ID , string FirstName ,string  LastName ,string  Email ,string Phone){
                    		_ID = ID; 
                    		_FirstName = FirstName; 
                    		_LastName = LastName; 
                    		_Email = Email; 
                    		_Phone = Phone; 
                    	}
                    	int ID() {
                    		return _ID;
                    	}
                    	void SetFirstName(string FirstName) {
                    		_FirstName = FirstName;
                    	}
                    	string FirstName() {
                    		return _FirstName;
                    	}
                    	void SetLastName(string LastName) {
                    		_LastName = LastName;
                    	}
                    	string LastName() {
                    		return _LastName;
                    	}
                    	void SetEmail(string Email) {
                    		_Email = Email;
                    	}
                    	string Email() {
                    		return _Email;
                    	}
                    	void SetPhone(string Phone) {
                    		_Phone = Phone;
                    	}
                    	string Phone() {
                    		return _Phone;
                    	}
                    
                    	void Print() {
                    		cout << "Info:" << endl;
                    		cout << "___________________________" << endl;
                    		cout << "ID		:" << _ID << endl;
                    		cout << "FirstName:" << _FirstName << endl;
                    		cout << "LastName:" << _LastName << endl;
                    		cout << "FullName:" <<  FirstName() + LastName() << endl;
                    		cout << "Email:" << _Email << endl;
                    		cout << "Phone:" << _Phone << endl;
                    		cout << "----------------------------" << endl;
                    
                    	}
                    	void SendEmail(string Subject , string Body) {
                    		cout << "The following message sent successfully to email : " << _Email << endl;
                    		cout << "Subject: " << Subject << endl;
                    		cout << "Body: " << Body <<  endl;
                    
                    
                    	}
                    	void SendSms(string Body) {
                    		cout << "The following sms sent successfully to phone: " << _Phone << endl;
                    		cout << Body << endl;
                    
                    	}
                    
                    };
                    class clsEmployee : public clsPerson {
                    private:
                    	string _Title;
                    	float  _Salary;
                    	string _Department;
                    public:
                    
                    	clsEmployee(int ID , string FirstName, string  LastName, string  Email, string Phone , string Title , string Department , float Salary )
                    		:clsPerson(ID, FirstName , LastName , Email,Phone)
                    	{
                    		_Title = Title;
                    		_Salary = Salary;
                    		_Department = Department;
                    	}
                    	void SetTitle(string Title) {
                    		_Title = Title;
                    	}
                    	string Title() {
                    		return _Title;
                    	}	
                    	void SetDepartment(string Department) {
                    		_Department = Department;
                    	}
                    	string Department() {
                    		return _Department;
                    	}
                    	void SetSalary(float Salary) {
                    		_Salary = Salary;
                    	}
                    	float Salary() {
                    		return _Salary;
                    	}
                    
                    	//void Print() {
                    
                    	//	clsPerson::Print();   // overriding function 
                    	//	
                    	//	cout << "\n Title: " << _Title;
                    	//	cout << "\n Department: " << _Department;
                    	//	cout << "\n Salary : " << _Salary;
                    
                    	//}
                    
                    
                    	void Print() {
                    		cout << "Info:" << endl;
                    		cout << "___________________________" << endl;
                    		cout << "ID		:" << ID() << endl;
                    		cout << "FirstName:" << FirstName() << endl;
                    		cout << "LastName:" << LastName()<< endl;
                    		cout << "FullName:" << FirstName() + LastName() << endl;
                    		cout << "Email:" << Email() << endl;
                    		cout << "Phone:" << Phone() << endl;
                    		cout << "Title: " << _Title << endl;
                    		cout << "Department: " << _Department << endl;
                    		cout << "Salary : " << _Salary << endl;
                    		cout << "----------------------------" << endl;
                    
                    	}
                    
                    };
                    
                    
                    int main() {
                    
                    	clsEmployee Employee1(10, "Mustafa" , "Sad" , "Mustafa.com" , "012423232" , "Eng" , "iT" ,1000);
                    
                    	Employee1.Print();
                    
                    	return 0;
                    }
                     
## 49- Multi Level Inheritance :-

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    class clsPerson {
                    private:
                    	int _ID ;
                    	string _FirstName, _LastName, _Email, _Phone;
                    
                    
                    public:
                    	
                    	clsPerson(int ID , string FirstName ,string  LastName ,string  Email ,string Phone){
                    		_ID = ID; 
                    		_FirstName = FirstName; 
                    		_LastName = LastName; 
                    		_Email = Email; 
                    		_Phone = Phone; 
                    	}
                    	int ID() {
                    		return _ID;
                    	}
                    	void SetFirstName(string FirstName) {
                    		_FirstName = FirstName;
                    	}
                    	string FirstName() {
                    		return _FirstName;
                    	}
                    	void SetLastName(string LastName) {
                    		_LastName = LastName;
                    	}
                    	string LastName() {
                    		return _LastName;
                    	}
                    	void SetEmail(string Email) {
                    		_Email = Email;
                    	}
                    	string Email() {
                    		return _Email;
                    	}
                    	void SetPhone(string Phone) {
                    		_Phone = Phone;
                    	}
                    	string Phone() {
                    		return _Phone;
                    	}
                    
                    	void Print() {
                    		cout << "Info:" << endl;
                    		cout << "___________________________" << endl;
                    		cout << "ID		:" << _ID << endl;
                    		cout << "FirstName:" << _FirstName << endl;
                    		cout << "LastName:" << _LastName << endl;
                    		cout << "FullName:" <<  FirstName() + LastName() << endl;
                    		cout << "Email:" << _Email << endl;
                    		cout << "Phone:" << _Phone << endl;
                    		cout << "----------------------------" << endl;
                    
                    	}
                    	void SendEmail(string Subject , string Body) {
                    		cout << "The following message sent successfully to email : " << _Email << endl;
                    		cout << "Subject: " << Subject << endl;
                    		cout << "Body: " << Body <<  endl;
                    
                    
                    	}
                    	void SendSms(string Body) {
                    		cout << "The following sms sent successfully to phone: " << _Phone << endl;
                    		cout << Body << endl;
                    
                    	}
                    
                    };
                    class clsEmployee : public clsPerson {
                    private:
                    	string _Title;
                    	float  _Salary;
                    	string _Department;
                    public:
                    
                    	clsEmployee(int ID , string FirstName, string  LastName, string  Email, string Phone , string Title , string 
                        Department , float Salary )
                    		:clsPerson(ID, FirstName , LastName , Email,Phone)
                    	{
                    		_Title = Title;
                    		_Salary = Salary;
                    		_Department = Department;
                    	}
                    	void SetTitle(string Title) {
                    		_Title = Title;
                    	}
                    	string Title() {
                    		return _Title;
                    	}	
                    	void SetDepartment(string Department) {
                    		_Department = Department;
                    	}
                    	string Department() {
                    		return _Department;
                    	}
                    	void SetSalary(float Salary) {
                    		_Salary = Salary;
                    	}
                    	float Salary() {
                    		return _Salary;
                    	}
                    
                    	//void Print() {
                    
                    	//	clsPerson::Print();   // overriding function 
                    	//	
                    	//	cout << "\n Title: " << _Title;
                    	//	cout << "\n Department: " << _Department;
                    	//	cout << "\n Salary : " << _Salary;
                    
                    	//}
                    
                    
                    	void Print() {
                    		cout << "Info:" << endl;
                    		cout << "___________________________" << endl;
                    		cout << "ID		:" << ID() << endl;
                    		cout << "FirstName:" << FirstName() << endl;
                    		cout << "LastName:" << LastName()<< endl;
                    		cout << "FullName:" << FirstName() + LastName() << endl;
                    		cout << "Email:" << Email() << endl;
                    		cout << "Phone:" << Phone() << endl;
                    		cout << "Title: " << _Title << endl;
                    		cout << "Department: " << _Department << endl;
                    		cout << "Salary : " << _Salary << endl;
                    
                    	}
                    
                    };
                    class clsDeveloper  : public clsEmployee {
                    private:
                    	string _MainProgrammingLanguage; 
                    
                    public:
                    	clsDeveloper(int ID, string FirstName, string  LastName, string  Email, string Phone, string Title, string 
                      Department, float Salary , string Language):
                    	clsEmployee( ID,  FirstName,  LastName,   Email,  Phone,  Title,  Department,  Salary)
                    	{
                    		_MainProgrammingLanguage = Language;
                    	}
                    	void SetLanguage(string Language) {
                    		_MainProgrammingLanguage = Language;
                    	}
                    	string Language() {
                    		return _MainProgrammingLanguage;
                    	}
                    	void Print() {
                    		clsEmployee::Print();
                    		cout << "MianLanguage: " << _MainProgrammingLanguage;
                    
                    	}
                    
                    };
                    
                    int main() {
                    
                    	clsDeveloper Developer1(10, "Mustafa" , "Sad" , "Mustafa.com" , "012423232" , "Eng" , "iT" ,1000 , "C#");
                    
                    	Developer1.Print();
                    
                    	return 0;
                    }
                     
## 50 -  Access Specifiers/Modifiers Review [ private, protected, public] 

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    class clsA {
                    private:
                    	int var1;
                    	void Fun1() {
                    		cout << "Function1";
                    	}
                    protected:
                    	int var2;
                    	void Fun2() {
                    		cout << "Function2";
                    	}
                    public:
                    	int var3;
                    	void Fun3() {
                    		cout << "Function3";
                    	}
                    };
                    
                    class clsB :public clsA {
                    
                    public:
                    	void Fun4() {
                    		clsA::Fun2();
                    	}
                    };
                    int main() {
                    
                    	clsB B;
                    	B.Fun4();
                    	return 0;
                    }
 
## 51- Up Casting vs Down Casting 


                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    
                    class clsPerson {
                    public:
                    	string FullName = "Mustafa Sad";
                    };
                    
                    class clsEmployee : public clsPerson {
                    public:
                    	string Title = "CEO";
                    };
                    
                    int main() {
                     
                    	clsEmployee Employee1;
                    
                    
                    	cout << Employee1.FullName << endl;
                    
                    
                    	// UpCasting 
                    	clsPerson* Person1 = &Employee1;
                    	cout << Person1->FullName << endl;
                    	
                    	return 0;
                    }
 
## 52 -   Virtual Functions
                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    
                    class clsPerson {
                    public:
                    	//هنا بقول ليه ان فيه هنا دوال اخري هيعمل ليها اوفر رايت 
                    	virtual void Print() {
                    		cout << "Hi , I'm Person" << endl;
                    	}
                    };
                    
                    class clsEmployee : public clsPerson {
                    public:
                    	void Print() {
                    		cout << "Hi , I'm Employee" << endl;
                    	}
                    };
                    class clsStudent : public clsPerson {
                    public:
                    	void Print() {
                    		cout << "Hi , I'm Student" << endl;
                    	}
                    };
                    
                    int main() {
                     
                    	clsEmployee Employee1;
                    	clsStudent Student1;
                    
                    
                    	// هنا باشر علي العنوان اللي فيه القيم 
                    	clsPerson* Person1 = &Employee1;
                    	clsPerson* Person2 = &Student1;
                    
                    	 Person1->Print() ;
                    	 Person2->Print() ;
                    	
                    	return 0;
                    }
 
## 53 -  Static/Early Binding vs Dynamic/Late Binding


                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    
                    class clsPerson {
                    public:
                    	//هنا بقول ليه ان فيه هنا دوال اخري هيعمل ليها اوفر رايت 
                    	virtual void Print() {
                    		cout << "Hi , I'm Person" << endl;
                    	}
                    };
                    
                    class clsEmployee : public clsPerson {
                    public:
                    	void Print() {
                    		cout << "Hi , I'm Employee" << endl;
                    	}
                    };
                    class clsStudent : public clsPerson {
                    public:
                    	void Print() {
                    		cout << "Hi , I'm Student" << endl;
                    	}
                    };
                    
                    int main() {
                     
                    	clsEmployee Employee1;
                    	clsStudent Student1;
                    
                    	// Early or static Binding  Faster than late Binding 
                    	Employee1.Print();
                    	Student1.Print();
                    
                    	//  late or Dynamic Binding 
                        clsPerson* Person1 = &Employee1;
                    	clsPerson* Person2 = &Student1;
                    
                    	 Person1->Print() ;
                    	 Person2->Print() ;
                    	
                    	return 0;
                    }
 
## 54 -  Friend Class 

                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    
                    class clsA {
                    private:
                    	int _Var1;
                    protected:
                    	int var3;
                    public:
                    	int Var2;
                    	clsA() {
                    		_Var1 = 10;
                    		var3 = 20;
                    		Var2 = 30;
                    	}
                    	friend class clsB;
                    };
                    class clsB : public clsA {
                    
                    public:
                    	void display(clsA A) {
                    		cout << "\nThe value of var1 = " << A.Var2;
                    		cout << "\nThe value of var1 = " << A._Var1;
                    		cout << "\nThe value of var1 = " << A.var3;
                    	}
                    };
                    int main() {
                     
                    	clsA A;
                    	clsB B;
                    
                    	B.display(A);
                    	return 0;
                    }
                     
## 55 - friend Function

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    
                    class clsA {
                    private:
                    	int _Var1;
                    protected:
                    	int var3;
                    public:
                    	int Var2;
                    	clsA() {
                    		_Var1 = 10;
                    		var3 = 20;
                    		Var2 = 30;
                    	}
                    	friend int MySum(clsA A1);
                    };
                    
                    int MySum(clsA A1) {
                    	return A1.Var2 + A1._Var1 + A1.var3;
                    }
                    int main() {
                     
                    	clsA A1;
                        
                    	cout << "The Value = " << MySum(A1);
                    
                    	return 0;
                    }
 
## 56- structure inside class 


                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    
                    class clsPerson {
                    private:
                    	struct stAddress {
                    		string AddressLine1;
                    		string AddressLine2;
                    		string city;
                    		string Country;
                    	};
                    public:
                    	string FullName;
                    	stAddress Address1;
                    
                    	clsPerson() {
                    		FullName = "Mustafa Sad Mohammed";
                    		Address1.AddressLine1 = "MitGamer";
                    		Address1.AddressLine2 = "Simbo";
                    		Address1.Country = "Egypt";
                    		Address1.city = "Cairo";
                    	}
                    	void PrintAddress() {
                    		cout << "Your Name : " << FullName << endl;
                    		cout << "Address1 : " << Address1.AddressLine1 << endl;
                    		cout << "Address2 : " << Address1.AddressLine2 << endl;
                    		cout << "Your Country :" << Address1.Country << endl;
                    		cout << "Your City :" << Address1.city << endl;
                    	}
                    };
                    
                    int main() {
                     
                    	clsPerson Person1;
                    
                    	cout << Person1.Address1.AddressLine1 << endl;
                    	cout << Person1.Address1.AddressLine2 << endl;
                    	cout << Person1.Address1.city << endl;
                    	cout << Person1.Address1.Country << endl;
                    
                    	Person1.PrintAddress();
                    
                    	return 0;
                    }
 
## 57 - Nested Class 

                    
                    #include <iostream>
                    #include <string>
                    #include <iomanip>
                    #include <vector>
                    #include <fstream>
                    using namespace std;
                    
                    
                    class clsPerson {
                    
                    
                    	class clsAddress {
                    
                    	public:
                    		string AddressLine1;
                    		string AddressLine2;
                    		string City; 
                    		string Country; 
                    
                    		void Print() {
                    			cout << AddressLine1 << endl;
                    			cout << AddressLine2 << endl;
                    			cout << City << endl;
                    			cout << Country << endl;
                    		}
                      };
                    public:
                    	string FullName;
                    	clsAddress Address1;
                    
                    	clsPerson() {
                    		FullName = "Mustafa Sad Mohammed";
                    		Address1.AddressLine1 = "MitGamer";
                    		Address1.AddressLine2 = "Simbo";
                    		Address1.Country = "Egypt";
                    		Address1.City = "Cairo";
                    	}
                    	
                    };
                    
                    int main() {
                     
                    	clsPerson Person1;
                    
                    	Person1.Address1.Print();
                    
                    	return 0;
                    }
 
## 58 - Passing Objects to Functions (ByRef/ByVal)


                    #include <iostream>
                    using namespace std;
                    
                    class clsA {
                    public:
                    	int x;
                    
                    	void Print() {
                    		cout << "the value of x= " << x << endl;
                    	}
                    };
                    void Fun1(clsA A1) {
                    	A1.x = 100;
                    }
                    void Fun2(clsA &A1) {
                    	A1.x = 200;
                    }
                    
                    int main(void)
                    {
                    	clsA A1;
                    	A1.x = 50;
                    
                    	A1.Print();
                        
                    	Fun1(A1);
                    	A1.Print();
                    
                    	Fun2(A1);
                    	A1.Print();
                    	return 0;
                    }


## 59 - Adding Objects to Vector



                    #include<iostream>
                    #include<vector>
                    
                    using namespace std;
                    
                    class clsA {
                    public:
                    	clsA(int value) {
                    		x = value;
                    	}
                    	int x;
                    	void print() {
                    		cout << "The value of x = " << x << endl;
                    	}
                    };
                    int main() {
                    	vector <clsA>  V1;
                    	short NumberOfObject = 5;
                    	for (int i = 0; i < NumberOfObject; i++) {
                    		V1.push_back(clsA(i));
                    	}
                    	for (int i = 0; i < NumberOfObject; i++) {
                    		V1[i].print();
                    	}
                    
                    }

## 60 - Objects and Dynamic Array

                    #include<iostream>
                    using namespace std;
                    
                    class clsA {
                    public:
                        clsA(int value) {
                            x = value;
                        }
                        int x;
                        void print() {
                            cout << "The value of x = " << x << endl;
                        }
                    };
                    
                    int main() {
                        short NumberOfObject = 5;
                    
                        // إنشاء مصفوفة ديناميكية
                        clsA** Arr1 = new clsA * [NumberOfObject];
                    
                        // تهيئة الكائنات
                        for (int i = 0; i < NumberOfObject; i++) {
                            Arr1[i] = new clsA(i);
                        }
                    
                        // طباعة القيم
                        for (int i = 0; i < NumberOfObject; i++) {
                            Arr1[i]->print();
                        }
                    
                        // تحرير الذاكرة
                        for (int i = 0; i < NumberOfObject; i++) {
                            delete Arr1[i];
                        }
                        delete[] Arr1;
                    
                        return 0;
                    }

## 61 - Objects with Parameterized Constructor and Array

                              #include<iostream>
                              using namespace std;
                              
                              class clsA {
                              public:
                                  clsA(int value) {
                                      x = value;
                                  }
                                  int x;
                                  void print() {
                                      cout << "The value of x = " << x << endl;
                                  }
                              };
                              
                              int main() {
                                 
                                  clsA obj[] = { clsA{10} , clsA(20) , clsA(30) };
                              
                                  for (int i = 0; i < 3; i++) {
                                      obj[i].print();
                                  }
                                  return 0;
                              }

## 62 - stack 

                    #include<iostream> 
                    #include <stack>
                    using namespace std;
                    
                    
                    int main() {
                    
                        stack <int> stkNumbers;
                    
                        stkNumbers.push(10);
                        stkNumbers.push(20);
                        stkNumbers.push(30);
                        stkNumbers.push(40);
                        stkNumbers.push(50);
                    
                        cout << "Size : " << stkNumbers.size() << endl;
                    
                        while (!stkNumbers.empty())
                        {
                            cout << stkNumbers.top() << endl;
                    
                            stkNumbers.pop();
                        }
                        cout << "Size : " << stkNumbers.size() << endl;
                    
                        return 0;
                    }

## 63 - Swap Stack 


                    #include<iostream> 
                    #include <stack>
                    using namespace std;
                    
                    
                    int main() {
                    
                        stack <int> MyStack1;
                        stack <int> MyStack2;
                    
                        MyStack1.push(10);
                        MyStack1.push(20);
                        MyStack1.push(30);
                        MyStack1.push(40);
                        MyStack1.push(50);
                    
                        MyStack2.push(60);
                        MyStack2.push(70);
                        MyStack2.push(80);
                        MyStack2.push(90);
                        MyStack2.push(100);
                    
                        MyStack1.swap(MyStack2);
                    
                        cout << "MyStack1 = ";
                    
                        while (!MyStack1.empty()) {
                            cout << MyStack1.top() << " ";
                            MyStack1.pop();
                        }
                        cout << "MyStack2 = ";
                    
                        while (!MyStack2.empty()) {
                            cout << MyStack2.top() << " ";
                            MyStack2.pop();
                        }
                        return 0;
                    }


## 64 - swap queue 


                              #include<iostream> 
                              #include <queue>
                              using namespace std;
                              
                              
                              int main() {
                              
                                  queue <int> Myqueue1;
                                  queue <int> Myqueue2;
                              
                                  Myqueue1.push(10);
                                  Myqueue1.push(20);
                                  Myqueue1.push(30);
                                  Myqueue1.push(40);
                                  Myqueue1.push(50);
                              
                                  Myqueue2.push(60);
                                  Myqueue2.push(70);
                                  Myqueue2.push(80);
                                  Myqueue2.push(90);
                                  Myqueue2.push(100);
                              
                                  Myqueue1.swap(Myqueue2);
                                  
                                  cout << "coutnt" << Myqueue1.size() << endl;
                                  cout << "back  " << Myqueue1.back() << endl;
                                  cout << "Front " << Myqueue1.front() << endl;
                                  cout << "Myqueue1 = ";
                              
                                  while (!Myqueue1.empty()) {
                                      cout << Myqueue1.front() << " ";
                                      Myqueue1.pop();
                                  }
                                  
                                  cout << "coutnt" << Myqueue2.size() << endl;
                                  cout << "back  " << Myqueue2.back() << endl;
                                  cout << "Front " << Myqueue2.front() << endl;
                              
                                  cout << "Myqueue2 = ";
                              
                                  while (!Myqueue2.empty()) {
                                      cout << Myqueue2.front() << " ";
                                      Myqueue2.pop();
                                  }
                                  
                              
                                  return 0;
                              }


## 65 - Linked List Implementation


                    #include<iostream> 
                    #include <queue>
                    using namespace std;
                    
                    class node {
                    public:
                        int Value;
                        node* Next;
                    
                    };
                    int main() {
                    
                        node* head;
                    
                        node* Node1 = NULL;
                        node* Node2 = NULL;
                        node* Node3 = NULL;
                        
                        Node1 = new node();
                        Node2 = new node();
                        Node3 = new node();
                        
                        Node1->Value = 1;
                        Node2->Value = 2;
                        Node3->Value = 3;
                    
                        Node1->Next = Node2;
                        Node2->Next = Node3;
                        Node3->Next = NULL;
                    
                        head = Node1;
                    
                        while (head != NULL) {
                            cout << head->Value << endl;
                            head = head->Next;
                        }
                     
                        
                    
                        return 0;
                    }

## 66 - Singly  linked list 


                    #include<iostream> 
                    #include <queue>
                    using namespace std;
                    
                    class node {
                    public:
                        int Value;
                        node* Next;
                    
                    };
                    int main() {
                    
                        node* head;
                    
                        node* Node1 = NULL;
                        node* Node2 = NULL;
                        node* Node3 = NULL;
                        
                        Node1 = new node();
                        Node2 = new node();
                        Node3 = new node();
                        
                        Node1->Value = 1;
                        Node2->Value = 2;
                        Node3->Value = 3;
                    
                        Node1->Next = Node2;
                        Node2->Next = Node3;
                        Node3->Next = NULL;
                    
                        head = Node1;
                    
                        while (head != NULL) {
                            cout << head->Value << endl;
                            head = head->Next;
                        }
                     
                        
                    
                        return 0;
                    }

## 67 - liked list insert at the beginning 

                    
                    #include<iostream> 
                    #include <queue>
                    using namespace std;
                    
                    class node {
                    public:
                        int Value;
                        node* Next;
                    
                    };
                    void InsertAtList(node*& head, int Value) {
                        
                        node* new_node = new node();
                    
                        new_node->Value = Value;
                        new_node->Next = head;
                    
                        head = new_node;
                    }
                    void PrintNode(node* head) {
                        while (head != NULL)
                        {
                            cout << head->Value << " ";
                            head = head->Next;
                        }
                    }
                    int main() {
                    
                        node * head = NULL;
                    
                        InsertAtList(head, 1);
                        InsertAtList(head, 2);
                        InsertAtList(head, 3);
                        InsertAtList(head, 4);
                        InsertAtList(head, 5);
                        
                        PrintNode(head);
                        return 0;
                    }

## 68 - Find in linked list 


                    #include<iostream> 
                    #include <queue>
                    using namespace std;
                    
                    class node {
                    public:
                        int Value;
                        node* Next;
                    
                    };
                    void InsertAtList(node*& head, int Value) {
                        
                        node* new_node = new node();
                    
                        new_node->Value = Value;
                        new_node->Next = head;
                    
                        head = new_node;
                    }
                    void PrintNode(node* head) {
                        while (head != NULL)
                        {
                            cout << head->Value << " ";
                            head = head->Next;
                        }
                    }
                    node* Find(node* head, int Value) {
                        while (head != NULL) {
                            if (head->Value == Value) {
                                return head ;
                            }
                            head = head->Next;
                        }
                        return NULL;
                    }
                    int main() {
                    
                        node * head = NULL;
                    
                        InsertAtList(head, 1);
                        InsertAtList(head, 2);
                        InsertAtList(head, 3);
                        InsertAtList(head, 4);
                        InsertAtList(head, 5);
                        
                        PrintNode(head);
                    
                        node* N1 = Find(head , 2) ;
                    
                        if (N1 != NULL)
                            cout << "\n Value Found -:)" << endl;
                        else
                            cout << " \n Value not Found -:(" << endl;
                    
                        
                        return 0;
                    }
                    
## 69 - insert after 

                         #include<iostream> 
                    #include <queue>
                    using namespace std;
                    
                    class node {
                    public:
                        int Value;
                        node* Next;
                    
                    };
                    void InsertAtList(node*& head, int Value) {
                        
                        node* new_node = new node();
                    
                        new_node->Value = Value;
                        new_node->Next = head;
                    
                        head = new_node;
                    }
                    void PrintNode(node* head) {
                        while (head != NULL)
                        {
                            cout << head->Value << " ";
                            head = head->Next;
                        }
                    }
                    node* Find(node* head, int Value) {
                        while (head != NULL) {
                            if (head->Value == Value) {
                                return head ;
                            }
                            head = head->Next;
                        }
                        return NULL;
                    }
                    void InsertAfter(node * prev_node ,int Value ) {
                    
                        if (prev_node == NULL) {
                            cout << "the given previous node cnnot be null";
                            return;
                        }
                        node* new_node = new node();
                    
                        new_node->Value = Value;
                        new_node->Next = prev_node->Next;
                        prev_node->Next = new_node;
                        
                    }
                    int main() {
                    
                        node * head = NULL;
                    
                        InsertAtList(head, 1);
                        InsertAtList(head, 2);
                        InsertAtList(head, 3);
                        InsertAtList(head, 4);
                        InsertAtList(head, 5);
                        
                    
                        node* N1 = Find(head , 2) ;
                    
                        InsertAfter(N1, 500);
                    
                        PrintNode(head);
                    
                        if (N1 != NULL)
                            cout << "\n Value Found -:)" << endl;
                        else
                            cout << " \n Value not Found -:(" << endl;
                    
                        
                    
                        return 0;
                    }

## 70 - Insert After 


                    #include<iostream> 
                    #include <queue>
                    using namespace std;
                    
                    class node {
                    public:
                        int Value;
                        node* Next;
                    
                    };
                    void InsertAtList(node*& head, int Value) {
                        
                        node* new_node = new node();
                    
                        new_node->Value = Value;
                        new_node->Next = head;
                    
                        head = new_node;
                    }
                    void PrintNode(node* head) {
                        while (head != NULL)
                        {
                            cout << head->Value << " ";
                            head = head->Next;
                        }
                    }
                    node* Find(node* head, int Value) {
                        while (head != NULL) {
                            if (head->Value == Value) {
                                return head ;
                            }
                            head = head->Next;
                        }
                        return NULL;
                    }
                    void InsertAfter(node * prev_node ,int Value ) {
                    
                        if (prev_node == NULL) {
                            cout << "the given previous node cnnot be null";
                            return;
                        }
                        node* new_node = new node();
                    
                        new_node->Value = Value;
                        new_node->Next = prev_node->Next;
                        prev_node->Next = new_node;
                        
                    }
                    int main() {
                    
                        node * head = NULL;
                    
                        InsertAtList(head, 1);
                        InsertAtList(head, 2);
                        InsertAtList(head, 3);
                        InsertAtList(head, 4);
                        InsertAtList(head, 5);
                        
                    
                        node* N1 = Find(head , 2) ;
                    
                        InsertAfter(N1, 500);
                    
                        PrintNode(head);
                    
                        if (N1 != NULL)
                            cout << "\n Value Found -:)" << endl;
                        else
                            cout << " \n Value not Found -:(" << endl;
                    
                        
                    
                        return 0;
                    }

## 71 - insert at end 

                              #include<iostream> 
                              #include <queue>
                              using namespace std;
                              
                              class node {
                              public:
                                  int Value;
                                  node* Next;
                              
                              };
                              void InsertAtList(node*& head, int Value) {
                                  
                                  node* new_node = new node();
                              
                                  new_node->Value = Value;
                                  new_node->Next = head;
                              
                                  head = new_node;i
                              }
                              void PrintNode(node* head) {
                                  while (head != NULL)
                                  {
                                      cout << head->Value << " ";
                                      head = head->Next;
                                  }
                              }
                              node* Find(node* head, int Value) {
                                  while (head != NULL) {
                                      if (head->Value == Value) {
                                          return head ;
                                      }
                                      head = head->Next;
                                  }
                                  return NULL;
                              }
                              void InsertAfter(node * prev_node ,int Value ) {
                              
                                  if (prev_node == NULL) {
                                      cout << "the given previous node cnnot be null";
                                      return;
                                  }
                                  node* new_node = new node();
                              
                                  new_node->Value = Value;
                                  new_node->Next = prev_node->Next;
                                  prev_node->Next = new_node;
                                  
                              }
                              void InserAtEnd(node* &head, int Value) {
                              
                                  node* new_node = new node();
                                  
                                  new_node->Value = Value;
                                  new_node->Next = NULL;
                                  
                                  if (head == NULL) {
                                      head = new_node;
                                      return;
                                  }
                                  node* LastNode = head;
                                  while (LastNode->Next != NULL) {
                                      LastNode = LastNode->Next;
                                  }
                                  LastNode->Next = new_node;
                                  return;
                              }
                              
                              
                              int main() {
                              
                                  node * head = NULL;
                              
                                  InserAtEnd(head, 1);
                                  InserAtEnd(head, 2);
                                  InserAtEnd(head, 3);
                                  InserAtEnd(head, 4);
                                  InserAtEnd(head, 5);
                                  
                              
                                  PrintNode(head);
                              
                                  return 0;
                              }
                              

## 72 - Delete Node 

                    
                    #include<iostream> 
                    #include <queue>
                    using namespace std;
                    
                    class node {
                    public:
                        int Value;
                        node* Next;
                    
                    };
                    void InsertAtList(node*& head, int Value) {
                        
                        node* new_node = new node();
                    
                        new_node->Value = Value;
                        new_node->Next = head;
                    
                        head = new_node;
                    }
                    void PrintNode(node* head) {
                        while (head != NULL)
                        {
                            cout << head->Value << " ";
                            head = head->Next;
                        }
                    }
                    node* Find(node* head, int Value) {
                        while (head != NULL) {
                            if (head->Value == Value) {
                                return head ;
                            }
                            head = head->Next;
                        }
                        return NULL;
                    }
                    void InsertAfter(node * prev_node ,int Value ) {
                    
                        if (prev_node == NULL) {
                            cout << "the given previous node cnnot be null";
                            return;
                        }
                        node* new_node = new node();
                    
                        new_node->Value = Value;
                        new_node->Next = prev_node->Next;
                        prev_node->Next = new_node;
                        
                    }
                    void InserAtEnd(node* &head, int Value) {
                    
                        node* new_node = new node();
                        
                        new_node->Value = Value;
                        new_node->Next = NULL;
                        
                        if (head == NULL) {
                            head = new_node;
                            return;
                        }
                        node* LastNode = head;
                        while (LastNode->Next != NULL) {
                            LastNode = LastNode->Next;
                        }
                        LastNode->Next = new_node;
                        return;
                    }
                    void DeleteNode(node * &head , int value) {
                        node* Current = head , * Prev = head;
                    
                        if (Current == NULL) {
                            return;
                        }
                        if (Current->Value == value) {
                            head = Current->Next;
                            delete Current;
                        }
                    
                        while (Current != NULL && Current->Value != value) {
                            Prev = Current;
                            Current = Current->Next;
                        }
                    
                        Prev->Next = Current->Next;
                        delete Current; 
                    }
                    
                    int main() {
                    
                        node * head = NULL;
                    
                        InserAtEnd(head, 1);
                        InserAtEnd(head, 2);
                        InserAtEnd(head, 3);
                        InserAtEnd(head, 4);
                        InserAtEnd(head, 5);
                        
                        DeleteNode(head, 4);
                    
                        PrintNode(head);
                    
                        return 0;
                    }

## 73 -  Map


                    #include <iostream>
                    #include <map>
                    using namespace std;
                    
                    int main()
                    {
                        map<string, int > StudentGrad;
                    
                        StudentGrad["ali"] = 44;
                        StudentGrad["Ahmed"] = 87;
                        StudentGrad["fadi"] = 90;
                    
                        for (const auto& pair : StudentGrad) {
                            cout << "student name : " << pair.first << "Grade: " << pair.second << endl;
                        }
                    
                        // finding the grade for a specific student 
                        string studentName = "omar";
                        if (StudentGrad.find(studentName) != StudentGrad.end()) {
                            cout << "studentName" << studentName << "Grade:" << StudentGrad[studentName] << endl;
                        }
                        else {
                            cout << "Grade not found for " << studentName << endl;
                        }
                        system("pause>0");
                    
                    }

## 75 - Union 


                    
                    #include <iostream>
                    using namespace std;
                    
                    union MyUnion
                    {
                        int intValue;
                        float flaotValue;
                        char charValue;
                    
                    };
                    int main()
                    {
                        MyUnion  Union1;
                    
                        Union1.intValue = 23;
                        cout << "int value :" << Union1.intValue << endl;
                    
                        Union1.flaotValue = 23.34;
                        cout << "float value :" << Union1.flaotValue << endl;
                    
                        Union1.charValue = 'c';
                        cout << "char value :" << Union1.charValue << endl;
                    
                    
                        system("pause>0");
                    
                    }


## 76 - 




                    
