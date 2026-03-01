
# Chapter 1: Tutorial Intro
- hello world
  ```c
  #include <stdio.h>
  main(){
	  printf("hello world!!!\n");
  }
  ```
- farenheit to celsius convertor
  ```c
  #include <stdio.h>
  main(){
	  int fahr, celsius;
	  int lower, upper, step;
	  
	  lower = 0;
	  upper = 300;
	  step = 20;
	  
	  fahr = lower;
	  while ( fahr <= upper){
		  celsius = 5 * ( fahr - 32 ) / 9;
		  printf("%d\t%d\n", fahr, celsius);
		  fahr = fahr + step;
	  }
  }
  ```
- copy file from input
  ```c
  #include <stdio.h>
  main(){
	  int c;
	  c = getchar();
	  while ((c = getchar()) c != EOF){
		  putcahr(c);
	  }
  }
  ```
- counting line
  ```c
  #include <stdio.h>
  main(){
	  int c, n1;
	  n1 = 0;
	  while ((c = getchar()) c != EOF){
		  if ( c == '/n')
			  ++n1;
		  printf("%d\n",n1);
	  }
  }
  ```
- word counting
```c
  #include <stdio.h>
  #define IN 1
  #define OUT 0
  main(){
	  int c, n1, nw, nc, state;
	  state = OUT;
	  n1 = nw = nc = 0;
	  while ((c = getchar()) != EOF){
		  ++nc;
		  if ( c == '/n')
			  ++n1;
		  if ( c == ' ' || c == '\n' || c == '\t')
			  state = OUT;
		  else if ( state == OUT){
			  state = IN;
			  ++nw;
		  }
	  }
	  printf("%d %d %d\n",n1, nw, nc)
  }
```
- number of occurence of each digit
```c
  #include <stdio.h>
  main(){
	  int c, i, nwhite, nother;
	  int ndigit[10];
	  nwhite = nother = 0;
	  n1 = nw = nc = 0;
	 
	  
	  while ((c = getchar()) != EOF){
		  ++nc;
		  if ( c >= '0' && c <= '9')
			  ++ndigits[c-'0'];
		  else if ( c == ' ' || c == '\n' || c == '\t')
			  ++nwhite;
		  else
			  ++nother;
	  }
	  printf("digits = ")
	  for ( i = 0; i < 10; i++)
		  printf("%d", ndigit[i]);
	  printf(",white space = %d, other = %d\n",
		  nwhite, nother)
  }
```
- function
```c
#include <stdio.h>
int power(int m, int n);
  main(){
	  int i;
	  for ( i = 0; i < 10; i++)
		  printf("%d %d %d",i , power(2,i), power(-3,i));
  }
int power(int base, int n){
	int i,p;
	p = 1;
	for ( i = 1; i < n; ++i)
		p *= base;
	return p;
	
}
```
- arguments call by value
```c
int power(int base, int n){
	int p;
	p = 1;
	for ( p = 1; n > 0; --n)
		p *= base;
	return p;
	
}
```
- character arrays ( program that reads sets of text lines and prints the longest)
```c
#include <stdio.h>
#define MAXLINE 1000

int getline(char line[], int maxline);
void copy (char to[], char from[]);

main(){
int len, max;
char line[MAXLINE], longest[MAXLINE];
max = 0;
while ((len = getline(line, MAXLINE)) > 0 )
	if (len > max){
		max = len;
		copy(longest, line);
	}
	if (max > 0)
		printf("%s", longest);
}

int getline(char s[], int lim){
	int c,i;
	for (i=0;i<lim-1 && (c=getchar())!=EOF &&c!='\n';++1)
		s[i] = c;
	if (c == '\n'){
		s[i] = c;
	    ++i;
	}
	s[i] = '\0';
	return i;
}

void copy(char to[], char from[]){
	int i = 0;
	while((to[i] = from[i])!='\0')
		++i;	
}
```
- external variables and scopes
```c
#include <stdio.h>
#define MAXLINE 1000

int max;
char line[MAXLINE];
char longest[MAXLINE];

int getline(char line[], int maxline);
void copy (char to[], char from[]);

main(){
int len;
extern int max;
extern char longest[MAXLINE];
max = 0;
while ((len = getline()) > 0 )
	if (len > max){
		max = len;
		copy();
	}
	if (max > 0)
		printf("%s", longest);
}

int getline(){
	int c,i;
	extern char line[];
	for (i=0;i<MAXLINE-1 && (c=getchar())!=EOF && c!='\n';++1)
		line[i] = c;
	if (c == '\n'){
		line[i] = c;
	    ++i;
	}
	line[i] = '\0';
	return i;
}

void copy(){
	int i = 0;
	extern char line[], longest[];
	while((longest[i] = line[i])!='\0')
		++i;	
}
```

