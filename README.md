6.
==

Program to create a two dimensional matrix.  Then write an algorithm such that if an element in an MxN matrix is 0, its entire row and column is set to 0.


Matrix is created using two dimensional array.
We declared a two dimensional array of size [4][3]. Here 4 indicates number of arrays i.e 4 and 3 indicates length of each individual array. So using For loop for each array and then another For loop to fill each individual array. 
import java.util.Scanner;

class MatrixExample {
  public static void main(String[] args) {
		Scanner in = new Scanner(System.in);
		int anArray[][] = new int[4][3];
		System.out.println("Row size= " + anArray.length);
		System.out.println("Column size = " + anArray[2].length);

		for (int i = 0; i < anArray.length; i++) {
			for (int j = 0; j < anArray[1].length; j++) {
				System.out.println("Enter a number");
				anArray[i][j] = in.nextInt();
			}
		}
		outputArray(anArray);
	}

public static void outputArray(int[][] array) {
  	int rowSize = array.length;
		int columnSize = array[1].length;
		for (int i = 0; i < rowSize; i++) {
			System.out.print("[");
			for (int j = 0; j < columnSize; j++) {
				System.out.print(" " + array[i][j]);
			}
			System.out.println(" ]");
		}
		System.out.println();
	}

}



-=-=-=-==-=-=-==-=-=-=-=-=-=-==-=-=-=-=-=-=-=-=-=-=-==-=-=-==-=-=-=-=-=-=-==-=-=-=-=-=-=-=-=-=-=-==-=-=-==-=-=-=-=-=-=-==-=-=-=-=-=-=-=
                                  Second Part
-=-=-=-==-=-=-==-=-=-=-=-=-=-==-=-=-=-=-=-=-=-=-=-=-==-=-=-==-=-=-=-=-=-=-==-=-=-=-=-=-=-=-=-=-=-==-=-=-==-=-=-=-=-=-=-==-=-=-=-=-=-=-=

import java.util.Scanner;

class MatrixExample {
  static int[] rowArray;
	static int[] colArray;

	public static void main(String[] args) {
		Scanner in = new Scanner(System.in);
		int anArray[][] = new int[3][3];
		System.out.println("Row size= " + anArray.length);
		System.out.println("Column size = " + anArray[2].length);
// This for loop for making a matrix by asking user to enter numbers.
		for (int i = 0; i < anArray.length; i++) {
			for (int j = 0; j < anArray[1].length; j++) {
				System.out.println("Enter a number");
				anArray[i][j] = in.nextInt();
			}
		}
		outputArray(anArray);
		checkingZeroInMatrix(anArray);
		finalOutputArray(anArray);

	}
// This function uses for loop for printing the matrix which is filled with user entered numbers.

	public static void outputArray(int[][] array) {
		int rowSize = array.length;
		int columnSize = array[1].length;
		for (int i = 0; i < rowSize; i++) {
			System.out.print("[");
			for (int j = 0; j < columnSize; j++) {
				System.out.print(" " + array[i][j]);
			}
			System.out.println(" ]");
		}
		System.out.println();
	}

/* This function creates two arrays named rowArray and colArray whose sizes are equal to number of rows and number of columns respectively.Then it scans entire matrix to check presence of zero. For each zero found, rowArray and colArray are set to 1.
*/
	public static void checkingZeroInMatrix(int[][] array1) {
		rowArray = new int[array1.length];
		colArray = new int[array1[1].length];
		for (int i = 0; i < array1.length; i++) {
			for (int j = 0; j < array1[1].length; j++) {
				if (array1[i][j] == 0) {
					rowArray[i] = 1;
					colArray[j] = 1;
				}
			}
		}
	}
IN this function,for each ‘1’ in rowArray or colArray, matrix value is set to “0”. Then finally matrix is printed out with corresponding row and column set to zero. 
	public static void finalOutputArray(int[][] array2) {
		for (int i = 0; i < array2.length; i++) {
			for (int j = 0; j < array2[1].length; j++) {
                if(rowArray[i]==1 || colArray[j]==1){
                	array2[i][j]=0;
                }
			}
		}

		int rowSize = array2.length;
		int columnSize = array2[1].length;
		for (int i = 0; i < rowSize; i++) {
			System.out.print("[");
			for (int j = 0; j < columnSize; j++) {
				System.out.print(" " + array2[i][j]);
			}
			System.out.println(" ]");
		}
		System.out.println();
	
	}

}


