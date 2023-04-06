// StackLinkedlist
//Implementing a stack with the use of a Linkedlist

#include <iostream>
#define SIZE 10
#include <chrono>
using namespace std;
using namespace std::chrono;


struct Node
{
int data;

Node *link;
};
Node *top = NULL;


bool isEmpty()
{
 if(top == NULL){
    return true;
 }

 else{
    return false;
 }


}

bool isFull(int StackSize) {
   struct Node* ptr = top;
    int count = 0;
    while (ptr != NULL) {
        count++;
        ptr = ptr->link;
    }
    if (count >= StackSize) {
        return true;
    }
}



void Push (int value)
{

    //if isFull(SIZE){
      //  cout<<"Stack overflow";
       // exit(1);
   // }
    //else{
        Node *ptr = new Node();
  ptr->data = value;
  ptr->link = top;
  top = ptr;
    }

//}

//Function to delete an element from the stack
void Pop ( )
{


 if ( isEmpty() )
  cout<<"Stack underflow";
else
 {
  Node *ptr = top;
  top = top -> link;
  delete(ptr);
 }
}

// Function to show the element at the top of the stack
void StackTop()
{
 if ( isEmpty() )
  cout<<"Stack is Empty";
 else
  cout<<"Element at top is : "<< top->data;
}

// Function to Display the stack
void Display()
{
 if ( isEmpty() )
  cout<<"Stack is Empty";
 else
 {
  Node *temp=top;
  while(temp!=NULL)
  {   cout<<temp->data<<" ";
   temp=temp->link;
  }
  cout<<"\n";
 }
 }

// Main function
int main()
{

 auto start = high_resolution_clock::now();

 Push(8);
Push(10);
Push(5);
Push(11);
Push(15);
Push(23);
Push(6);
Push(18);
Push(20);
Push(17);
Display();
Pop();
Pop();
Pop();
Pop();
Pop();
Display();
Push(4);
Push(30);
Push(3);
Push(1);
Display();

auto stop = high_resolution_clock::now();

auto duration = duration_cast<microseconds>(stop - start);

    cout << "Time taken by function: "
         << duration.count() << " microseconds" << endl;

return 0;
}
