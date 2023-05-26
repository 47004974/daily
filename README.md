//# daily
//快速排序
#include<iostream>
#include<string>
#include<cstdlib>
#include<ctime>
using namespace std;
void show(int a[],int first,int end) {
	int temp = a[first];
	int temp_first = first;
	int temp_end=end;
	while (temp_first != temp_end) {
		while (a[temp_first] <= temp && temp_first < temp_end) {
			temp_first++;
		}
		while (a[temp_end] >= temp && temp_end > temp_first) {
			temp_end--;
		}
		if (temp_end > temp_first) {
			int t = a[temp_first];
			a[temp_first] = a[temp_end];
			a[temp_end] = t;
		}
		
	}
	a[first] = a[temp_first];
	temp_first = temp;
	show(a, first, temp_first - 1);
	show(a, temp_first + 1, end);
}
int main() {
	int a[9] = {1,3,5,6,7,8,10,9,2,4};
	int first=0;
	int end = 10;
	show(a, first, end);
	return 0;
}
