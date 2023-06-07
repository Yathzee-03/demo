# demo

#include <iostream>
#include <string>

using namespace std;

int main(){
	int arrSize;
	int arrNumbers[100];
	int i;
	
	cout<<"Size of Array: ";
	cin>>arrSize;
	cout<<"Enter "<<arrSize<<" Elements: ";
		
	for (i = 0; i<arrSize;i++)
		cin>>arrNumbers[i];
		
	cout<<"The original Array:"<<endl;
	for(i = 0; i < arrSize; i++)
		cout<<arrNumbers[i]<<" "<<endl;
		
	for(i = 0; i < arrSize; i++)
	cout<<"["<<i<<"]"" = "<<arrNumbers[i]<<" "<<endl;
	
	cout << "Array Functions" << endl;
	cout << "1: Insert Array" << endl;
	cout << "2: Delete Array" << endl;
	cout << "3: Search for Array" << endl;
	cout << "4: Update Array" << endl;
	cout << "5: Show all Array" << endl;
	cout << "6: Quit" << endl;
	
	int arrayFunction; 
	string repeatFunction;
	do{
		
		cout <<"Choose a function:";
		cin >> arrayFunction;
		
		int numPosition;
		switch(arrayFunction){
			case 1:
				int insertedNumber;
    
    			cout<<"\nEnter element to Insert: ";
    			cin>>insertedNumber;
    			
    			cout<<"Insert at position: ";
    			cin>>numPosition;
	 
    			numPosition = numPosition - 1;
	 
    			for(i = arrSize; i > numPosition; i--)
	    			arrNumbers[i]=arrNumbers[i-1];
	    
				arrNumbers[numPosition]= insertedNumber;
				arrSize++;
	
				cout<<"Array elements after insertion: \n";
	
				for(i = 0; i<arrSize;i++)
	    			cout<<"["<<i<<"]"" = "<<arrNumbers[i]<<" "<<endl;
				
				cout << "Choose another function?(Yes/No)";
				cin >> repeatFunction;
				
				break;
			
			case 2:
    			int deleteElement;
    
    			cout << "\nEnter the element to delete:";
    			cin >> deleteElement;
    
    			for(i=0; i<arrSize; i++){
    			    if(arrNumbers[i]==deleteElement){
    	 		       numPosition=i + 1;
    			    }
    			}
    
    			while(numPosition<=arrSize){
    	    		arrNumbers[numPosition-1] = arrNumbers[numPosition];
    	    		numPosition = numPosition + 1;
   				}
    
    			arrSize = arrSize - 1;
    
    			for(i=0; i<arrSize; i++){
        			cout << arrNumbers[i] << " ";
    			}	
				
				cout << "Choose another function?(Yes/No)";
				cin >> repeatFunction;
				
				break;
			case 4:
				int updateElement, newElement;
    
    			cout << "Enter element to update:";
    			cin >> updateElement;
    
    			cout << "Enter new element:";
    			cin >> newElement;
    
    			for(i = 0; i < arrSize; i++){
    	    		if(arrNumbers[i] == updateElement){
        	    		arrNumbers[i] = newElement;
        			}
    			}

    			// Output the updated array
    			cout << "Updated array: ";
    			for (i = 0; i < arrSize; i++) {
    	    		cout << arrNumbers[i] << " ";
   				}
    			cout << endl;
    			
    			cout << "Choose another function?(Yes/No)";
				cin >> repeatFunction;
				
    			break;
    	
    		default:
    			cout << "Invalid choice" << endl;
    			cout << "Choose another function?(Yes/No)";
				cin >> repeatFunction;
				
		}
	}while((repeatFunction == "Yes") || (repeatFunction == "yes") || (repeatFunction == "YES"));
		
	return 0;
}
