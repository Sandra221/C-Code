using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Diagnostics; // for the delegate

namespace Algorithms
{
    //dll file

    public class Algoritmer1
    {
        //SWAP METHOD TO BE USED IN BUBBLESORT & SELECTION SORT
        public static void Swap(int[] array, int x, int y)
        {
            {
                int temp;
                temp = array[x];
                array[x] = array[y];
                array[y] = temp;
            }
        }

        // PREPARE METHOD
        // takes int input and create an array
        // sends it to the randimize method 
        public static int[] Prepare(int arraySize) 
        {
            int[] array = new int[arraySize];
            Randomize(array);
            return array;
        }

        //RANDOMIZE METHOD
        // takes array and create random values * 10 the array
        public static void Randomize(int[] array)
        {
            Random rnd = new Random();

            for (int i = 0; i < array.Length; i++)
            {
                array[i] = rnd.Next(0, 10 * array.Length); 
            }

        }

        //ALG1 INSERTION SORT
        public static void InsertionSort(int[] array)
        {
            int j, temp;
            for (int i = 1; i <= array.Length - 1; i++)
            {
                temp = array[i];
                j = i - 1;
                while (j >= 0 && array[j] > temp)
                {
                    array[j + 1] = array[j];
                    j--;
                }
                array[j + 1] = temp;
            }
        }

        //ALG2 SELECTION SORT
        public static void Sort(int[] array)
        {
            int i, j, min;
            for (i = 0; i < array.Length; i++)
            {
                min = i;
                for (j = 0; j < array.Length; j++)
                {
                    if (array[j] > array[min])
                    {
                        min = j;
                        Swap(array,i,min);
                    }
                }
            }
        }

        //ALG3 BUBBLESORT
        public static void BubbleSort(int[] array)
        {
            for (int i = 0; i < array.Length; i++)
            {
                for (int j = 0; j< array.Length - 1; j++)
                {
                    if (array[j] > array[j + 1])
                    {
                        Swap(array, j + 1, j);
                    }
                }
            }
        }

        //ALG4 MERGE SORT
        public static void Merge(int[] input, int left, int middle, int right)
        {
            int[] leftArray = new int[middle - left + 1];
            int[] rightArray = new int[right - middle];

            Array.Copy(input, left, leftArray, 0, middle - left + 1);
            Array.Copy(input, middle + 1, rightArray, 0, right - middle);

            int i = 0;
            int j = 0;
            for (int k = left; k < right + 1; k++)
            {
                if (i == leftArray.Length)
                {
                    input[k] = rightArray[j];
                    j++;
                }
                else if (j == rightArray.Length)
                {
                    input[k] = leftArray[i];
                    i++;
                }
                else if (leftArray[i] <= rightArray[j])
                {
                    input[k] = leftArray[i];
                    i++;
                }
                else
                {
                    input[k] = rightArray[j];
                    j++;
                }
            }
        }

        public static void MergeSort(int[] input, int left, int right)
        {
            if (left < right)
            {
                int middle = (left + right) / 2;

                MergeSort(input, left, middle);
                MergeSort(input, middle + 1, right);

                Merge(input, left, middle, right);
            }
        }

        //ALG5 QUICK SORT
        public static void QuickSort(int[] arr, int start, int end)
        {
            int i;
            if (start < end)
            {
                i = Partition(arr, start, end);

                QuickSort(arr, start, i - 1);
                QuickSort(arr, i + 1, end);
            }
        }

        public static int Partition(int[] arr, int start, int end)
        {
            int temp;
            int p = arr[end];
            int i = start - 1;

            for (int j = start; j <= end - 1; j++)
            {
                if (arr[j] <= p)
                {
                    i++;
                    temp = arr[i];
                    arr[i] = arr[j];
                    arr[j] = temp;
                }
            }

            temp = arr[i + 1];
            arr[i + 1] = arr[end];
            arr[end] = temp;
            return i + 1;
        }

        // USING LAMBDA METHOD
        public static void LambdaSort(int[] array) 
        {
            var result = array.OrderBy(x => x);
        }

        //DELEGATE METHODS
        public delegate void DelegateOne(int[] array);
        public delegate void DelegateTwo(int[] array, int left, int right);

        //DISPLAYRUNNINGTIME INSERT; BUBBEL; SORT;
        public static void DisplayRunningTime(DelegateOne p, int [] myarray)
        {
            Stopwatch StopWatch1 = new Stopwatch();
            StopWatch1.Start();
            p(myarray);
            StopWatch1.Stop();
            TimeSpan Ts = StopWatch1.Elapsed;
            //Console.WriteLine(string.Format("Sorted Array: [{0}].", string.Join(", ", myarray)));
            Console.WriteLine("Time; {0:00}:{1:00}:{2:00}.{3}" + "\n",
                Ts.Hours, Ts.Minutes, Ts.Seconds, Ts.Milliseconds);
        }

        //DISPLAYRUNNINGTIME QUICK; MERGE
        public static void DisplayRunningTime(DelegateTwo x, int[] myarray)
        {
            Stopwatch StopWatch1 = new Stopwatch();
            StopWatch1.Start();
            x(myarray, 0, myarray.Length - 1);
            StopWatch1.Stop();
            TimeSpan Ts = StopWatch1.Elapsed;
            //Console.WriteLine(string.Format("Sorted Array: [{0}].", string.Join(", ", myarray)));
            Console.WriteLine("Time; {0:00}:{1:00}:{2:00}.{3}" + "\n",
                Ts.Hours, Ts.Minutes, Ts.Seconds, Ts.Milliseconds);

        }
    }
}
