# datastructure


     data
      1.Write a C++ program to implement singly linked list
     #include<iostream> 
     #include<cstdlib> 
     using namespace std; 
     struct node 
     { 
     int info; 
     struct node *next; 
     }*start; 
     class single_llist 
     {  
     public: 
     node* create_node(int); 
     void insert_begin(); 
    void insert_last(); 
        void insert_pos(); 
    void delete_begin(); 
    void delete_last(); 
    void delete_pos(); 
    void update_begin(); 
    void update_last(); 
    void update_pos(); 
    void sort(); 
    void reverse(); 
    void search(); 
     void display(); 
     single_llist() 
     { 
     start = NULL; 
     } 
    }; 
    int main() 
    { 
     int choice; 
     single_llist sl,s2; 
      start = NULL; 
     do 
     { 
    cout<<"---------------------------------"<<endl; 
    cout<<"Operations on singly linked list"<<endl; 
    cout<<"---------------------------------"<<endl; 
     cout<<"1.Insert at first"<<endl; 
    cout<<"2.Insert at last"<<endl; 
    cout<<"3.Insert at position"<<endl; 
    cout<<"4.Delete at first"<<endl; 
    cout<<"5.Delete at Last"<<endl; 
    cout<<"6.Delete at position"<<endl; 
    cout<<"7.Update at first"<<endl; 
    cout<<"8.Update at last"<<endl; 
    cout<<"9.Update at position"<<endl; 
    cout<<"10.Ascending order"<<endl; 
    cout<<"11.Descending order"<<endl; 
    cout<<"12.Search"<<endl; 
    cout<<"13.Display"<<endl; 
    cout<<"14.Exit "<<endl; 
    cout<<"Enter your choice :"; 
    cin>>choice; 
        switch(choice) 
     { 
    case 1: sl.insert_begin(); 
    sl.display(); 
    break; 
    case 2: sl.insert_last(); 
     sl.display(); 
     break; 
    case 3: sl.insert_pos(); 
     sl.display(); 
     break; 
    case 4: s2.delete_begin(); 
     sl.display(); 
      break; 
     case 5: s2.delete_last(); 
      sl.display(); 
    break; 
    case 6: sl.delete_pos(); 
    sl.display(); 
    break; 
    case 7: sl.update_begin(); 
    sl.display(); 
    break; 
    case 8: sl.update_last(); 
    sl.display(); 
    break; 
    case 9: sl.update_pos(); 
    sl.display(); 
    break; 
    case 10:sl.sort(); 
    sl.display(); 
    break; 
    case 11:sl.reverse(); 
    sl.display(); 
    break; 
    case 12:sl.search(); 
    sl.display(); 
    break; 
    case 13:sl.display(); 
    break; 
    case 14:exit(0); 
    break; 
    default:cout<<"Wrong choice...???"<<endl; 
    break; 
    } 
    } 
    while(choice != 14); 
    } 
    node *single_llist::create_node(int value) 
    { 
    struct node *temp, *s; 
    temp = new(struct node); 
    if (temp == NULL) 
    { 
    cout<<"Memory not allocated"<<endl; 
    return 0; 
    } 
    else 
     { 
    temp->info = value; 
    temp->next = NULL; 
    return temp; 
    } 
    } 
    void single_llist::insert_begin() 
    { 
    int value; 
     cout<<"Enter the value to be inserted : "; 
     cin>>value; 
     struct node *temp, *s; 
    temp = create_node(value); 
    if (start == NULL) 
    { 
    start = temp; 
    start->next = NULL; 
    cout<<temp->info<<" is inserted at first in the empty list"<<endl; 
    } 
    else 
    { 
     s = start; 
    start = temp; 
    start->next = s; 
    cout<<temp->info<<" is inserted at first"<<endl; 
    } 
    } 
     void single_llist::insert_last() 
    { 
    int value; 
    cout<<"Enter the value to be inserted : "; 
    cin>>value; 
     struct node *temp, *s; 
     temp = create_node(value); 
    if (start == NULL) 
     { 
     start = temp; 
    start->next = NULL; 
     cout<<temp->info<<" is inserted at last in the empty list"<<endl; 
    } 
     else 
    { 
    s = start; 
    while (s->next != NULL) 
    { 
    s = s->next; 
     } 
    temp->next = NULL; 
     s->next = temp; 
     cout<<temp->info<<" is inserted at last"<<endl; 
     } 
     } 
     void single_llist::insert_pos() 
     { 
          int value, pos, counter = 0, loc = 1; 
         struct node *temp, *s, *ptr; 
       s = start; 
     while (s != NULL) 
      { 
    s = s->next; 
      counter++; 
         } 
     if (counter == 0){} 
      else 
    { 
    cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; 
     cin>>pos; 
     s = start; 
     if(pos == 1) 
      { 
       cout<<"Enter the value to be inserted : "; 
     cin>>value; 
         temp = create_node(value); 
       start = temp; 
         start->next = s; 
       cout<<temp->info<<" is inserted at first"<<endl; 
       } 
         else if (pos > 1 && pos <= counter) 
       { 
          cout<<"Enter the value to be inserted : "; 
      cin>>value; 
      temp = create_node(value); 
     for (int i = 1; i < pos; i++) 
     { 
     ptr = s; 
     s = s->next; 
     } 
       ptr->next = temp; 
       temp->next = s; 
     cout<<temp->info<<" is inserted at position "<<pos<<endl; 
          } 
       else if (pos == counter+1) 
      { 
     cout<<"Enter the value to be inserted : "; 
      cin>>value; 
      temp = create_node(value); 
         while (s->next != NULL) 
           { 
         s = s->next; 
          } 
        temp->next = NULL; 
     s->next = temp; 
     cout<<temp->info<<" is inserted at last"<<endl; 
     } 
    else 
     { 
     cout<<"Positon out of range...!!!"<<endl; 
      } 
     }  else 

     { 

      s = start; 

     while (s->next != NULL) 

     { 

     s = s->next; 

    } 

    temp->next = NULL; 

     s->next = temp; 

       cout<<temp->info<<" is inserted at last"<<endl; 

      } 

     } 

      void single_llist::insert_pos() 

     { 

      int value, pos, counter = 0, loc = 1; 

      struct node *temp, *s, *ptr; 

       s = start; 

        while (s != NULL) 

        { 

     s = s->next; 

     counter++; 

     } 

     if (counter == 0){} 

     else 

     { 

        cout<<"Enter the postion from "<<loc<<" to "<<counter+1<<" : "; 

    cin>>pos; 

     s = start; 

     if(pos == 1) 

     { 

      cout<<"Enter the value to be inserted : "; 

    cin>>value; 

     temp = create_node(value); 

     start = temp; 

      start->next = s; 

     cout<<temp->info<<" is inserted at first"<<endl; 

      } 

         else if (pos > 1 && pos <= counter) 

     { 

     cout<<"Enter the value to be inserted : "; 

     cin>>value; 

     temp = create_node(value); 

    for (int i = 1; i < pos; i++) 

     { 

      ptr = s; 

      s = s->next; 

       } 

      ptr->next = temp; 

      temp->next 
      } 
       void single_llist::delete_begin() 
     { 
      if (start == NULL){} 
      else 
     { 
    struct node *s, *ptr; 
    s = start; 
    start = s->next; 
    cout<<s->info<<" deleted from first"<<endl; 
    free(s); 
     } 
    } 
    void single_llist::delete_last() 
    { 
    int i, counter = 0; 
    struct node *s, *ptr; 
    if (start == NULL){} 
    else 
    { 
    s = start; 
    while (s != NULL) 
    { 
    s = s->next; 
    counter++; 
    } 
    s = start; 
    if (counter == 1) 
    { 
    start = s->next; 
    cout<<s->info<<" deleted from last"<<endl; 
    free(s); 
    } 
    else 
    { 
    for (i = 1;i < counter;i++) 
    { 
    ptr = s; 
    s = s->next; 
    } 
    ptr->next = s->next; 
    cout<<s->info<<" deleted from last"<<endl; 
    free(s); 
    } 
      } 
    } 
    void single_llist::delete_pos() 
    { 
     int pos, i, counter = 0, loc = 1; 
    struct node *s, *ptr; 
    s = start; 
    while (s != NULL) 
    { 
      s = s->next; 
     counter++; 
    } 
    if (counter == 0){} 
    else 
    { 
     if (counter == 1) 
    { 
     cout<<"Enter the postion [ SAY "<<loc<<" ] : "; 
     cin>>pos; 
    s = start; 
     if (pos == 1) 
     { 
     start = s->next; 
     cout<<s->info<<" deleted from first"<<endl; 
     free(s); 
      } 
     else 
     cout<<"Position out of range...!!!"<<endl; 
     } 
     else 
    { 
     cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; 
     cin>>pos; 
     s = start; 
     if (pos == 1) 
    { 
     start = s->next; 
    cout<<s->info<<" deleted from first"<<endl; 
    free(s); 
    } 
    else if (pos > 1 && pos <= counter) 
    { 
      for (i = 1;i < pos;i++) 
      { 
     ptr = s; 
    s = s->next; 
     } 
      ptr->next = s->next; 
    if(pos == counter) 
    {cout<<s->info<<" deleted from last"<<endl; 
    free(s);} 
    else 
    {cout<<s->info<<" deleted from postion "<<pos<<endl; 
    free(s);} 
     } 
    else 
     cout<<"Position out of range...!!!"<<endl; 
    } 
    } 
     } 
     void single_llist::update_begin() 
    { 
    int value, pos=1, i,counter = 0; 
    struct node *s, *ptr; 
    s = start; 
    while (s != NULL) 
    { 
    s = s->next; 
    counter++; 
    } 
    if (counter == 0){} 
     else if (pos == 1) 
    { 
     cout<<"Enter the new node : "; 
    cin>>value; 
    start->info = value; 
    cout<<"Node updated at first position : "<<pos<<" = "<<start->info<<endl; 
     } 
    } 
    void single_llist::update_last() 
    { 
     int value, pos, i,counter = 0; 
     struct node *s, *ptr; 
    s = start; 
           while (s != NULL) 
       { 
       s = s->next; 
     counter++; 
    } 
     s=start; 
     if (counter == 0){} 
     else 
     { 
     cout<<"Enter the new node : "; 
     cin>>value; 
     for (i = 1; i < counter ; i++) 
     { 
     s = s->next; 
     } 
     s->info = value; 
     cout<<"Node updated at last position : "<<counter<<" = "<<s->info<<endl; 
    } 
    } 
    void single_llist::update_pos() 
    { 
    int value, pos, i,counter = 0, loc = 1; 
    struct node *s, *ptr; 
    s = start; 
    while (s != NULL) 
    { 
    s = s->next; 
    counter++; 
    } 
    if (counter == 0){} 
    else 
    { 
    if (counter == 1) 
    { 
    cout<<"Enter the postion [ SAY "<<loc<<" ] : "; 
    cin>>pos; 
    s = start; 
    if (pos == 1) 
    { 
    cout<<"Enter the new node : "; 
    cin>>value; 
    start->info = value; 
    cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; 
    } 
    else 
    cout<<"Position out of range...!!!"<<endl; 
    } 
    else 
    { 
    cout<<"Enter the postion from "<<loc<<" to "<<counter<<" : "; 
    cin>>pos; 
    s = start; 
    if (pos == 1) 
    { 
    cout<<"Enter the new node : "; 
    cin>>value; 
    start->info = value; 
    cout<<"Node updated at position : "<<pos<<" = "<<start->info<<endl; 
    } 
    else if (pos > 1 && pos <= counter) 
    { 
    cout<<"Enter the new node : "; 
    cin>>value; 
    for (i = 1; i < pos ; i++) 
    { 
    s = s->next; 
    } 
    s->info = value; 
    cout<<"Node updated at position : "<<pos<<" = "<<s->info<<endl; 
     } 
    else 
    cout<<"Position out of range...!!!"<<endl; 
    } 
    } 
    } 
     void single_llist::sort() 
    { 
    struct node *ptr, *s; 
    int value; 
    if (start == NULL){} 
    else 
    { 
     ptr = start; 
    while (ptr != NULL) 
    { 
     for (s = ptr->next;s !=NULL;s = s->next) 
     { 
    if (ptr->info > s->info) 
    { 
     value = ptr->info; 
    ptr->info = s->info; 
    s->info = value; 
    } 
    } 
    ptr = ptr->next; 
    } 
     } 
    } 
    void single_llist::reverse() 
    { 
     struct node *ptr, *s; 
    int value; 
    if (start == NULL){} 
     else 
    { 
     ptr = start; 
     while (ptr != NULL) 
    { 
    for (s = ptr->next;s !=NULL;s = s->next) 
    { 
    if (ptr->info < s->info) 
    { 
     value = ptr->info; 
    ptr->info = s->info; 
    s->info = value; 
    } 
    } 
    ptr = ptr->next; 
    } 
    } 
    } 
    void single_llist::search() 
    { 
     int value, loc = 0, pos = 0, counter = 0; 
    struct node *s; 
     s = start; 
    while (s != NULL) 
     { 
    s = s->next; 
    counter++; 
     } 
    if (start == NULL){} 
    else 
    { 
    cout<<"Enter the value to be searched : "; 
    cin>>value; 
    struct node *s; 
    s = start; 
    while (s != NULL) 
    { 
    pos++; 
     if (s->info == value) 
    { 
     loc++; 
     if(loc == 1) 
     cout<<"Element "<<value<<" is found at position "<<pos; 
     else if(loc <= counter) 
    cout<<" , "<<pos; 
    } 
    s = s->next; 
    } 
    cout<<endl; 
    if (loc == 0) 
    cout<<"Element "<<value<<" not found in the list"<<endl; 
    } 
    } 
    void single_llist::display() 
    { 
    struct node *temp; 
     if (start == NULL) 
    cout<<"Linked list is empty...!!!"<<endl; 
    else 
    { 
    cout<<"Linked list contains : "; 
    temp = start; 
    while (temp != NULL) 
    { 
    cout<<temp->info<<" "; 
    temp = temp->next; 
    } 
    cout<<endl; 
     } 
     }
		 
		        
	program 2:
     
			#include<iostream>
			using namespace std;
			struct Node{
			int value;
			struct Node *next;
			};
			struct Node* head = NULL;
			struct Node* sHead = NULL;
			struct Node* temp = NULL;
			void insert(int new_data){
			struct Node* new_node = new Node(); //(struct Node*)malloc(sizeof(struct Node));
			new_node->value = new_data;
			new_node->next = head;
			head = new_node;
			}
			int n;
			int ele;
			int splitIndex;
			int main(){
			int i;
			cout<<"Enter number of elements you want in the list\t";
			cin>>n;
			cout<<"Enter elements :" <<endl;
			for(i=0;i<n;i++){
			cin>>ele;
			insert(ele);
			}
			cout<<"\nList of elements : "<<endl;
			Node *t;
			t = head;
			while(t != NULL){
			cout<<t->value<<"\t";
			t = t->next;
			}
			cout<<"\n\nEnter the position you want the list to split ";
			cin>>splitIndex;
			while(splitIndex < 0 || splitIndex > n-1){
			cout<<"Invalid position. Try again."<<endl;
			cin>>splitIndex;
			}
			temp = head;
			for(i=0;i<=splitIndex;i++){
			if(i==splitIndex-1){
			Node *tN;
			tN = temp->next;
			sHead = tN;
			temp->next = NULL;
			break;
			}
			temp = temp->next;
			}
			temp = head;
			if(temp == NULL){
			cout<<"\nFirst list is empty"<<endl;
			}else{
			cout<<"\n\nFirst list element "<<endl;
			while(temp != NULL){
			cout<<temp->value<<"\t";
			temp = temp->next;
			}
			}
			temp = sHead;
			if(temp == NULL){
			cout<<"\nSecond list is empty"<<endl;
			}else{
			cout<<"\n\nSecond list elements "<<endl;
			while(temp != NULL){
			cout<<temp->value<<"\t";
			temp = temp->next;
			}
			}
			return 0;
			}

  
     
    program 3:
   
   
   			#include<iostream.h>
			#include<conio.h>
			#include<iomanip.h>
			#include<stdio.h>
			#include<stdlib.h>
			struct node
			{
				int info;
				struct node *next;
			}*first, *last;
			int count = 0;
			class singly
			{
				public:
					node* create_node(int);
					void insert_begin();
					void insert_end();
					void insert_pos();
					void display();
					void search();
					singly()
					{
						first = NULL;
						last = NULL;
					}
			};
			void main()
			{
				int choice;
				clrscr();
				singly sl,s2;
				do
				{
					cout<<"\t\t\t--------------------------------"<<endl;
					cout<<"\t\t\tOperations on singly linked list"<<endl;
					cout<<"\t\t\t--------------------------------"<<endl;
					cout<<"1.Insert at first\t";
					cout<<"2.Insert at Last\t";
					cout<<"3.Insert at Position"<<endl;
					cout<<"4.Search\t\t";
					cout<<"5.Display\t\t";
					cout<<"6.Exit\t\t\t"<<endl;
					cout<<"Enter your choice : ";
					cin>>choice;
					switch(choice)
					{
						case 1:	sl.insert_begin();
							s2.display();
							break;
						case 2:	sl.insert_end();
							s2.display();
							break;
						case 3:	sl.insert_pos();
							s2.display();
							break;
						case 4:sl.search();
							s2.display();
							break;
						case 5:s2.display();
							break;
						case 6:cout<<"Successfully Exited"<<endl;
							s2.display();
							exit(0);
							break;
						default:cout<<"Wrong Choice...???"<<endl;
							s2.display();
							break;
					}
				}
				while(choice != 20);
				getch();
			}
			node* singly :: create_node(int num)
			{
				struct node *nn;
				nn = new(struct node);
				if (nn == NULL)
				{
					cout<<"Memory not allocated"<<endl;
					return 0;
				}
				else
				{
					nn->info = num;
					nn->next = NULL;
					return nn;
				}
			}
			void singly :: insert_begin()
			{
				int value;
				struct node *temp;
				cout<<"Enter the element to be inserted : ";
				cin>>value;
				temp = create_node(value);
				if ( first == last && first == NULL )
				{
					count++;
					first = last = temp;
					first->next = last->next = temp->next;
					cout<<first->info<<" inserted at first in the empty list"<<endl;
				}
				else
				{
					count++;
					temp->next = first;
					first = temp;
					cout<<first->info<<" inserted at first"<<endl;
				}
			}
			void singly :: insert_end()
			{
				int value;
				struct node *temp;
				cout<<"Enter the element to be inserted : ";
				cin>>value;
				temp = create_node(value);
				if ( first == last && first == NULL )
				{
					count++;
					first = last = temp;
					first->next = last->next = temp->next;
					cout<<last->info<<" inserted at first in the empty list"<<endl;
				}
				else
				{
					count++;
					last->next = temp;
					last = temp;
					cout<<last->info<<" inserted at last"<<endl;
				}
			}
			void singly :: insert_pos()
			{
				int value, pos;
				struct node *temp, *f, *l;
				cout<<"Enter the element to be inserted : ";
				cin>>value;
				temp = create_node(value);
				if ( first == NULL && last == NULL )
				{
					cout<<"The list is empty, Pls enter the position [ SAY 1 ] : ";
					cin>>pos;
					if ( pos == 1 )
					{
						count++;
						first = last = temp;
						first->next = last->next = temp->next;
						cout<<temp->info<<" inserted at first in the empty list"<<endl;
					}
					else
						cout<<"Invalid Position"<<endl;
				}
				else
				{
					cout<<"Enter the position from 1 to "<<count + 1<<" : ";
					cin>>pos;
					if ( pos == 1 )
					{
						count++;
						temp->next = first;
						first = temp;
						cout<<first->info<<" inserted at first"<<endl;
					}
					else if ( pos == count + 1 )
					{
						count++;
						last->next = temp;
						last = temp;
						cout<<last->info<<" inserted at last"<<endl;
					}
					else if (pos > 1  && pos <= count)
					{
						f = first;
						for ( int i = 1 ; i <= pos - 1 ; i++ )
						{
							l = f;
							f = f->next;
						}
						count++;
						l->next = temp;
						temp->next = f;
						cout<<temp->info<<" inserted at position "<<pos<<endl;
					}
					else
						cout<<"Position out of range"<<endl;
				}
			}
			void singly :: display()
			{
				struct node *temp;
				if ( first == NULL && last == NULL )
				{cout<<"The list is empty...!!!"<<endl;}
				else
				{
					temp = first;
					cout<<"Linked list of "<<count<<" elements : ";
					for ( int i = 1 ; i < count ; i++ )
					{
						cout<<temp->info<<"->";
						temp = temp->next;
					}
					cout<<temp->info<<endl;
				}
			}
			void singly :: search()
			{
				int pos = 0, flag = 0, value;
				struct node *f;
				if ( first == NULL && last == NULL ) {}
				else
				{
					cout<<"Enter the value to be searched : ";
					cin>>value;
					f = first;
					for (int i = 0; i < count; i++)
					{
						pos++;
						if (f->info == value)
						{
							flag++;
							if (flag == 1)
								cout<<"Element "<<value<<" found at position : "<<pos;
							else if (flag > 1 && flag <= count)
								cout<<" , "<<pos;
						}
						f = f->next;
					}
					if (flag == 0)
						cout<<"Element "<<value<<" not found in the list"<<endl;
					else if (flag == 1)
						cout<<endl<<"Element "<<value<<" entered "<<flag<<" time"<<endl;
					else
						cout<<endl<<"Element "<<value<<" entered "<<flag<<" times"<<endl;
				}
			}
			



    program 4
    
    			#include <iostream.h>
			#include <stdio.h>
			#include <stdlib.h>
			#include <conio.h>
			void findMinAndMax(int arr[], int low, int high, int &min, int &max)
			{
			if (low == high)	
			{
			if (max < arr[low])
			{
			max = arr[low];
			}
			
			if (min > arr[high])
			{
			min = arr[high];
			}
			return;
			}
			if (high - low == 1)	
			{
			if (arr[low] < arr[high])	
			{
			if (min > arr[low])
			 {
			min = arr[low];
			}
			
			if (max < arr[high])
			{
			max = arr[high];
			}
			}
			else {
			if (min > arr[high])
			{
			min = arr[high];
			}
			
			if (max < arr[low])
			{
			max = arr[low];
			}
			}
			return;
			}
			int mid = (low + high) / 2;
			findMinAndMax(arr, low, mid, min, max);
			findMinAndMax(arr, mid + 1, high, min, max);
			}
			int main()
			{
			clrscr();
			int arr[] = { 7, 2, 9, 3, 6, 7, 8, 4 };
			int n = sizeof(arr) / sizeof(arr[0]);
			int max = arr[0], min = arr[0];
			
			findMinAndMax(arr, 0, n - 1, min, max);
			
			cout << "The minimum array element is " << min << endl;
			cout << "The maximum array element is " << max;
			
			return 0;
			}
			

    
    
    
    
    program 5
    
    #include<iostream> 
			using namespace std; 
			int unsorted_array[10]; 
			int ele; 
			int ith_large = 0; 
			int n = 10; 
			int * sortarr(int arr[], int sizeofarr){ 
			 for(int i=0;i<sizeofarr;i++){ 
			 for(int j=i+1;j<sizeofarr;j++){ 
			 if(arr[j] < arr[i]){ 
			 int tmp = arr[i]; 
			 arr[i] = arr[j]; 
			 arr[j] = tmp; 
			 } 
			 } 
			 } 
			 return arr; 
			} 
			int findIthLargest(int ith_large, int arr[], int sizeofarr){ 
			 arr = sortarr(arr, sizeofarr); 
			
			return arr[sizeofarr-ith_large-1];
			} 
			int main(){ 
			 cout<<"Enter array elements "<<endl; 
			 int sizeofarr = n; 
			 for(int i=0;i<sizeofarr;i++){ 
			 cin>>ele; 
			 unsorted_array[i] = ele; 
			 } 
			 cout<<"Enter the position of ith largest element you want to find \t"; 
			 cin>>ith_large; 
			 ith_large = ith_large-1; 
			 if(ith_large < 0){ 
			 cout<<"Position has to be greater than 0"; 
			 }else if(ith_large > sizeofarr){ 
			 cout<<"Position doesn't exist"; 
			 }else{ 
			 int ith_largest = findIthLargest(ith_large, unsorted_array, sizeofarr); 
			 cout<<"Array elements "<<endl; 
			 for(int i=0;i<sizeofarr;i++){ 
			 cout<<unsorted_array[i]<<"\t"; 
			 } 
			 cout<<"\n"<<ith_large+1<<"th largest element in the array is " << ith_largest; 
			 } 
			 return 0; 
			} 

        
    program 6
   			#include <bits/stdc++.h>
			using namespace std;
			struct Node
			{
			int data;
			struct Node* left, *right;
			Node(int data)
			{
			this->data = data;
			left = right = NULL;
			}
			};
			bool isBSTUtil(struct Node* root, Node *&prev)
			{
			if (root)
			{
			if (!isBSTUtil(root->left, prev))
			return false;
			if (prev != NULL && root->data <= prev->data)
			return false;
			prev = root;
			return isBSTUtil(root->right, prev);
			}
			return true;
			}
			bool isBST(Node *root)
			{
			Node *prev = NULL;
			return isBSTUtil(root, prev);
			}
			int main()
			{
			struct Node *root = new Node(7);
			root->left = new Node(5);
			root->right = new Node(8);
			root->left->left = new Node(3);
			root->left->right = new Node(6);
			if (isBST(root))
			cout << "Is BST";
			else
			cout << "Not a BST";
			return 0;
			}
			


      program 7:
      
      		#include <iostream>
			using namespace std;
			void MaxHeapify (int a[], int i, int n)
			{
				int j, temp;
				temp = a[i];
				j = 2*i;
				while (j <= n)
				{
					if (j < n && a[j+1] > a[j])
					j = j+1;
					if (temp > a[j])
						break;
					else if (temp <= a[j])
					{
						a[j/2] = a[j];
						j = 2*j;
					}
				}
				a[j/2] = temp;
				return;
			}
			void HeapSort(int a[], int n)
			{
				int i, temp;
				for (i = n; i >= 2; i--)
				{
					temp = a[i];
					a[i] = a[1];
					a[1] = temp;
					MaxHeapify(a, 1, i - 1);
				}
			}
			void Build_MaxHeap(int a[], int n)
			{
				int i;
				for(i = n/2; i >= 1; i--)
					MaxHeapify(a, i, n);
			}
			int main()
			{
			int n, i,arr[100];
				cout<<"\nEnter the number of data element to be sorted: ";
				cin>>n;
				n++;
				for(i=1;i<n;i++)
				 {
				 cout<<"Enter element"<<i<<":";
				 cin>>arr[i];
				 }
				Build_MaxHeap(arr, n-1);
				HeapSort(arr, n-1);
				cout<<"\nSorted Data ";
				for (i = 1; i < n; i++)
					cout<<" "<<arr[i];
				return 0;
			}



    2) Write a C++ program to split the linked list into two halves such that the element ‘e’ should be the first element of second list.
    
    #include<iostream>
		using namespace std;
		struct Node{
		int value;
		struct Node *next;
		};
		struct Node* head = NULL;
		struct Node* sHead = NULL;
		struct Node* temp = NULL;
		
		void insert(int new_data) 
		{
		struct Node* new_node = new Node(); 
		new_node->value = new_data;
		new_node->next = head;
		head = new_node;
		}
			int n;
			int ele;
			int splitIndex;
			int main()
		 {
			int i;
			cout<<"Enter number of elements you want in the list\t";
			cin>>n;
			cout<<"Enter elements :" <<endl;
			for(i=0;i<n;i++)
			{
			   cin>>ele;
			   insert(ele);
		    }
			  cout<<"\nList of elements : "<<endl;
			   Node *t;
			   t = head;
			   while(t != NULL)
			{
			   cout<<t->value<<"\t";
			    t = t->next;
		    }
			   cout<<"\n\nEnter the position you want the list to split ";
			    cin>>splitIndex;
			
		    	while(splitIndex < 0 || splitIndex > n-1)
		    	
			{
			    cout<<"Invalid position. Try again."<<endl;
			
			 cin>>splitIndex;
		
		    }
			   temp = head; 
			  for(i=0;i<=splitIndex;i++){
		
			if(i==splitIndex-1)
			  if(i==n-1)
		     {
			   Node *tN;
			   tN = temp->next;
			    sHead = tN;
			    temp->next = NULL;
			    break;
		    }
		     temp = temp->next;
		}
				temp = head;
				if(temp == NULL)
				{
				  cout<<"\nFirst list is empty"<<endl;
				}
				else
				{
				   cout<<"\n\nFirst list element "<<endl;
				    while(temp != NULL)
				   {
				      cout<<temp->value<<"\t";
				       temp = temp->next;
				   }
				}
			      temp = sHead;
				  if(temp == NULL)
				{
				   cout<<"\nSecond list is empty"<<endl;
				}
				else
				{
				   cout<<"\n\nSecond list elements "<<endl;
				while(temp != NULL)
				{
				   cout<<temp->value<<"\t";
				   temp = temp->next;
		        }
		 }
		   return 0;
		}
		
![image](https://user-images.githubusercontent.com/19484531/155066070-c6f79bef-defe-4e09-8db4-c023bb2c1d75.png)


     3)
     14. Write a C++ program to implement BST to support the following operations
     Assume no duplicate elements while constructing the BST
    1.Given a key perform a search in the BST, if the key is found then display “key found”
    2.Insert an element into a BST
    3.Delete an element from a BST
     Display the tree using Inorder,Preorder and Postorder traversal methods

                               # include <iostream> 
			# include <cstdlib> 
			using namespace std; 
			struct node 
			{ 
			 int info; 
			 struct node *left; 
			 struct node *right; 
			}*root; 
			class BST 
			{ 
			 public: 
			 void find(int, node **, node **); 
			 void insert(node *, node *); 
			 void del(int); 
			 void case_a(node *,node *); 
			 void case_b(node *,node *); 
			 void case_c(node *,node *); 
			 void preorder(node *); 
			 void inorder(node *); 
			 void postorder(node *); 
			 void display(node *, int); 
			 BST() 
			 { 
			 root = NULL; 
			 } 
			}; 
			int main() 
			{ 
			 int choice, num; 
			 BST bst; 
			 node *temp; 
			 while (1) 
			 { 
			 cout<<"-----------------"<<endl; 
			 cout<<"Operations on BST"<<endl; 
			 cout<<"-----------------"<<endl; 
			 cout<<"1.Insert Element "<<endl; 
			 cout<<"2.Delete Element "<<endl; 
			 cout<<"3.Inorder Traversal"<<endl; 
			 cout<<"4.Preorder Traversal"<<endl; 
			 cout<<"5.Postorder Traversal"<<endl; 
			 cout<<"6.Display"<<endl; 
			 cout<<"7.Quit"<<endl; 
			 cout<<"Enter your choice : "; 
			 cin>>choice; 
			 switch(choice) 
			 { 
			 case 1: 
			 temp = new node; 
			 cout<<"Enter the number to be inserted : "; 
			 cin>>temp->info; 
			 bst.insert(root, temp); 
			 break; 
			 case 2: 
			 if (root == NULL) 
			 { 
			 cout<<"Tree is empty, nothing to delete"<<endl; 
			 continue; 
			 } 
			 cout<<"Enter the number to be deleted : "; 
			 cin>>num; 
			 bst.del(num); 
			 break; 
			 case 3: 
			 cout<<"Inorder Traversal of BST:"<<endl; 
			 bst.inorder(root); 
			 cout<<endl; 
			 break; 
			 case 4: 
			 cout<<"Preorder Traversal of BST:"<<endl; 
			 bst.preorder(root); 
			 cout<<endl; 
			 break; 
			 case 5: 
			 cout<<"Postorder Traversal of BST:"<<endl; 
			 bst.postorder(root); 
			 cout<<endl; 
			 break; 
			 case 6: 
			 cout<<"Display BST:"<<endl; 
			 bst.display(root,1); 
			 cout<<endl; 
			 break; 
			 case 7: 
			 exit(1); 
			 default: 
			 cout<<"Wrong choice"<<endl; 
			 } 
			 } 
			} 
			void BST::find(int item, node **par, node **loc) 
			{ 
			 node *ptr, *ptrsave; 
			 if (root == NULL) 
			 { 
			 *loc = NULL; 
			 *par = NULL; 
			 return; 
			 } 
			 if (item == root->info) 
			 { 
			 *loc = root; 
			 *par = NULL; 
			 return; 
			 } 
			 if (item < root->info) 
			 ptr = root->left; 
			 else 
			 ptr = root->right; 
			 ptrsave = root; 
			 while (ptr != NULL) 
			 { 
			 if (item == ptr->info) 
			 { 
			 *loc = ptr; 
			 *par = ptrsave; 
			 return; 
			 } 
			 ptrsave = ptr; 
			 if (item < ptr->info) 
			 ptr = ptr->left; 
			 else 
			 ptr = ptr->right; 
			 } 
			 *loc = NULL; 
			 *par = ptrsave; 
			} 
			
			void BST::insert(node *tree, node *newnode) 
			{ 
			 if (root == NULL) 
			 { 
			 root = new node; 
			 root->info = newnode->info; 
			 root->left = NULL; 
			 root->right = NULL; 
			 cout<<"Root Node is Added"<<endl; 
			 return; 
			 } 
			 if (tree->info == newnode->info) 
			 { 
			 cout<<"Element already in the tree"<<endl; 
			 return; 
			 } 
			 if (tree->info > newnode->info) 
			 { 
			 if (tree->left != NULL) 
			 { 
			 insert(tree->left, newnode); 
			 } 
			 else 
			 { 
			 tree->left = newnode; 
			 (tree->left)->left = NULL; 
			 (tree->left)->right = NULL; 
			 cout<<"Node Added To Left"<<endl; 
			 return; 
			 } 
			 } 
			 else 
			 { 
			 if (tree->right != NULL) 
			 { 
			 insert(tree->right, newnode); 
			 } 
			 else 
			 { 
			 tree->right = newnode; 
			 (tree->right)->left = NULL; 
			 (tree->right)->right = NULL; 
			 cout<<"Node Added To Right"<<endl; 
			 return; 
			 } 
			 } 
			} 
			
			void BST::del(int item) 
			{ 
			 node *parent, *location; 
			 if (root == NULL) 
			 { 
			 cout<<"Tree empty"<<endl; 
			 return; 
			 } 
			 find(item, &parent, &location); 
			 if (location == NULL) 
			 { 
			 cout<<"Item not present in tree"<<endl; 
			 return; 
			 } 
			 if (location->left == NULL && location->right == NULL) 
			 case_a(parent, location); 
			 if (location->left != NULL && location->right == NULL) 
			 case_b(parent, location); 
			 if (location->left == NULL && location->right != NULL) 
			 case_b(parent, location); 
			 if (location->left != NULL && location->right != NULL) 
			 case_c(parent, location); 
			 free(location); 
			} 
			 
			
			void BST::case_a(node *par, node *loc ) 
			{ 
			 if (par == NULL) 
			 { 
			 root = NULL; 
			 } 
			 else 
			 { 
			 if (loc == par->left) 
			 par->left = NULL; 
			 else 
			 par->right = NULL; 
			 } 
			} 
			 
			
			void BST::case_b(node *par, node *loc) 
			{ 
			 node *child; 
			 if (loc->left != NULL) 
			 child = loc->left; 
			 else 
			 child = loc->right; 
			 if (par == NULL) 
			 { 
			 root = child; 
			 } 
			 else 
			 { 
			 if (loc == par->left) 
			 par->left = child; 
			 else 
			 par->right = child; 
			 } 
			} 
			 
			
			void BST::case_c(node *par, node *loc) 
			{ 
			 node *ptr, *ptrsave, *suc, *parsuc; 
			 ptrsave = loc; 
			 ptr = loc->right; 
			 while (ptr->left != NULL) 
			 { 
			 ptrsave = ptr; 
			 ptr = ptr->left; 
			 } 
			 suc = ptr; 
			 parsuc = ptrsave; 
			 if (suc->left == NULL && suc->right == NULL) 
			 case_a(parsuc, suc); 
			 else 
			 case_b(parsuc, suc); 
			 if (par == NULL) 
			 { 
			 root = suc; 
			 } 
			 else 
			 { 
			 if (loc == par->left) 
			 par->left = suc; 
			 else 
			 par->right = suc; 
			 } 
			 suc->left = loc->left; 
			 suc->right = loc->right; 
			} 
			 
			 
			void BST::preorder(node *ptr) 
			{ 
			 if (root == NULL) 
			 { 
			 cout<<"Tree is empty"<<endl; 
			 return; 
			 } 
			 if (ptr != NULL) 
			 { 
			 cout<<ptr->info<<" "; 
			 preorder(ptr->left); 
			 preorder(ptr->right); 
			 } 
			} 
			
			void BST::inorder(node *ptr) 
			{ 
			 if (root == NULL) 
			 { 
			 cout<<"Tree is empty"<<endl; 
			 return; 
			 } 
			 if (ptr != NULL) 
			 { 
			 inorder(ptr->left); 
			 cout<<ptr->info<<" "; 
			 inorder(ptr->right); 
			 } 
			} 
			 
			void BST::postorder(node *ptr) 
			{ 
			 if (root == NULL) 
			 { 
			 cout<<"Tree is empty"<<endl; 
			 return; 
			 } 
			 if (ptr != NULL) 
			 { 
			 postorder(ptr->left); 
			 postorder(ptr->right); 
			 cout<<ptr->info<<" "; 
			 } 
			} 
			 
			void BST::display(node *ptr, int level) 
			{ 
			 int i; 
			 if (ptr != NULL) 
			 { 
			 display(ptr->right, level+1); 
			 cout<<endl; 
			 if (ptr == root) 
			 cout<<"Root->: "; 
			 else 
			 { 
			 for (i = 0;i < level;i++) 
			 cout<<" "; 
			 } 
			 cout<<ptr->info; 
			 display(ptr->left, level+1); 
			 } 
			}
![image](https://user-images.githubusercontent.com/19484531/155075633-7ae150c3-46d4-4373-bad0-ac72b8961e54.png)
![image](https://user-images.githubusercontent.com/19484531/155075706-315dba38-8851-4bdf-a3c8-e599d3e3a8ba.png)
![image](https://user-images.githubusercontent.com/19484531/155075756-721cd99f-333b-4e5a-9c73-ed33c625e987.png)

