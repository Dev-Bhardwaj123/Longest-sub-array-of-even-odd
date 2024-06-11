# Longest-sub-array-of-even-odd
Find the longest sub array in a given array which has the maximum sequence of even and odd numbers
//Longest sub-array of even odds
#include<iostream>
using namespace std;

int main(){
	int n;
	cout<<"Enter size of array: ";
	cin>>n;
	int arr[n];
	for(int i=0;i<n;i++){
		cin>>arr[i];
	}
	//TC:O(n^2)
	int res=1;
	for(int i=0;i<n;i++){
		int count=1;
		for(int j=i+1;j<n;j++){
			if((arr[j]%2==0 && arr[j-1]%2!=0) || (arr[j]%2!=0 && arr[j-1]%2==0)){
				count++;
			}
			else{
				break;
			}
		}
		res=max(count,res);
	}
	cout<<"Max sub array is: "<<res;
	
	//TC:O(n)
//	int res=1,curr=1;
//	for(int i=1;i<n;i++){
//		if((arr[i]%2==0 && arr[i-1]%2!=0) || (arr[i]%2!=0 && arr[i-1]%2==0)){
//			curr++;
//			res=max(res,curr);
//		}
//		else{
//			curr=1;
//		}
//	}
//	cout<<"Max sub array is: "<<res;
}
