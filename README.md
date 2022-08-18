# GitTest

#include <stdio.h>
#include <math.h>

//Find the all the prime number between 1 and 10,000. 


int checkingPrime(int);
int RcheckingPrime(int, int);
int MAX = 10000;

int main()
{
	int isPrime = 1;\\hello

	printf("Here are the prime numbers between 1 and %d using interation. \n", MAX);
	printf("----------------------------------------------------------------------------------------------------------------------------------\n");

	for (int i = 2; i <= MAX; i++){
		isPrime = checkingPrime(i);
	
		if (isPrime == 1){
			printf("%d, ", i);
		}
	}

	printf("\n\nHere are the prime numbers between 1 and %d using recursion. \n", MAX);
	printf("----------------------------------------------------------------------------------------------------------------------------------\n");

	for (int i = 2; i <= MAX; i++) {
		isPrime = RcheckingPrime(i, (int)sqrt(i));

		if (isPrime == 0) {
			printf("%d, ", i);
		}
	}



}

int checkingPrime(int number){
	
	int marker = 1;

	for (int i = 2; i <= sqrt(number); i++) {

		if (number % i == 0) {
			marker = 0;
			break;
		}
	}

	if (number <= 1) {
		marker = 0;
	}
	else if (number == 2) {
		marker = 1;
	}

	return marker;
	

}

int RcheckingPrime(int i, int sqrtNumber){
	
	if (sqrtNumber <= 1){	
		return 0;
	}

	if ( i == 2) {
		return 1;
	}

	if (i % sqrtNumber == 0) {
		return 1;
	}

	else if (RcheckingPrime(i, sqrtNumber - 1 ) == 0)

		return 0;
}
