// inserting-at-the-last
//inserting new node at the last of linked list, c++
//creating linked list.
#include<iostream>
using namespace std;

class Node{
	public:
	//creating linked list structure.
		int value;
		Node*Next;
};
  void printlist(Node*n){
  	while(n!=NULL){
  	cout<<n->value<<endl;
  	n=n->Next;
	  }
  	 }
  
 void insert_At_The_last(Node**Head, int newValue){
 	//1. preparing new node.
 	Node*newNode=new Node();
 	newNode->value=newValue;
 	newNode->Next=NULL;
 	//2. if linked list is empty then new node will b the head noode.
 	if(*Head==NULL){//pointer of head is equal to NULL 
 		*Head=newNode;
 		return;
     }
    //3. find the last node.
	Node*last=*Head; //last node pointer that has the same value as head fo travers it.
	while(last->Next!=NULL){
		last=last->Next;
    }
	 
 	//4.insert new node at the last
 	last->Next=newNode;
 	
 }

int main(){
	//creating 3 new nodes.
	Node*Head=new Node();
	Node*second=new Node();
	Node*third=new Node();
   //giving values to Head, second and third nodes.
   Head->value=1;
   second->value=2;
   third->value=3;
   //giving pointers to each nodes.
   Head->Next=second;
   second->Next=third;
   third->Next=NULL;
   
   
   insert_At_The_last(&Head,4);
   //Printing values of each nodes of linked list.
   printlist(Head);
	return 0;
}
