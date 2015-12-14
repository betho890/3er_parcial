#include <iostream>






using namespace std;





typedef char DATA_TYPE;



struct nodo {

DATA_TYPE data;

nodo *next;

};



class StackDin {





int ITEMS; 

int ITEMSIZE;

nodo *SP; 



public:



StackDin() : SP(NULL), ITEMS(0), ITEMSIZE(sizeof(DATA_TYPE)) {}





~StackDin() {}





DATA_TYPE put(DATA_TYPE valor)

{

nodo *temp;



temp = new nodo;

if (temp == NULL) return -1;



temp->data = valor;

temp->next = SP;

SP = temp;

ITEMS ++;

return valor;

}



int empty() { return ITEMS == 0; }







DATA_TYPE get()

{

nodo *temp;

DATA_TYPE d;



if ( empty() ) return -1;



d = SP->data;

temp = SP->next;

if (SP) delete SP;

SP = temp;

ITEMS --;

return d;

}



};







int main()

{





StackDin s;

DATA_TYPE d;



for (d='A'; d<='Z'; d++) s.put(d);



while ( ! s.empty() )

cout << (DATA_TYPE)s.get() << " ";



cout << "\nPara terminar presione <Enter>...";

cin.get();

return 0;

}

