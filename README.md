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
                    
## 63 - 




