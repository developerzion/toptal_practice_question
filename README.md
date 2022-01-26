## **Toptal Practice question using Javascript**

<p>Write a function:

    function solution(A);

that, given an array A of N integers, returns the smallest positive integer (greater than 0) that does not occur in A.

For example, given A = [1, 3, 6, 4, 1, 2], the function should return 5.

Given A = [1, 2, 3], the function should return 4.

Given A = [−1, −3], the function should return 1.

Write an efficient algorithm for the following assumptions:

        N is an integer within the range [1..100,000];
        each element of array A is an integer within the range [−1,000,000..1,000,000].


```javascript
	//Generate an array ranging from 0 - largest elemnt found in array "A"
	let largestArray = []

	//Find the smallest element in the array
	function findSmallest(array){                
		Array.min = function( array ){
			return Math.min.apply( Math, array );
		};
		var minimum = Array.min(array);
		return minimum;
	}

	//Create new array from the largest element in the test array
	function createNewArray(largest){
		let count = 1;
		for (let index = 0; index < largest; index++) {                    
			largestArray.push(count++)                    
		}                 
	}

	//Get the difference between the test array and the array generated 
	//from the largest element in the test array
	function getDifference(A, largest){
		createNewArray(largest)
		let difference = largestArray.filter(x => !A.includes(x));    

		// return difference;
		if(difference.length > 0) return findSmallest(difference)   
		else return largest + 1; 
	}

	function solution(A){
		let largest = 0                
		for (let i = 0; i < A.length; i++) {
			const element = A[i];
			if (element > largest){
				largest = element;
			}                    
		}
		return getDifference(A, largest)
		// console.log(getDifference(A, largest))                
	}

	let A = [1, 3, 6, 4, 1, 2,7, 10,9];
	// let A = [1, 2, 3];
	// let A = [-1, -3];

	solution(A);
```
