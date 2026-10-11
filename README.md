# stack-push
#include <iostream>
using namespace std;

#define MAX 5
int stackArr[MAX];
int top = -1;

// Push operation
void push(int val) {
    if(top == MAX-1) {
        cout << "Stack Overflow!\n";
    } else {
        top++;
        stackArr[top] = val;
        cout << val << " pushed\n";
    }
}

// Pop operation
void pop() {
    if(top == -1) {
        cout << "Stack Underflow!\n";
    } else {
        cout << stackArr[top] << " popped\n";
        top--;
    }
}

// Display
void display() {
    if(top == -1) {
        cout << "Stack is empty\n";
    } else {
        cout << "Stack: ";
        for(int i=top; i>=0; i--) {
            cout << stackArr[i] << " ";
        }
        cout << endl;
    }
}

int main() {
    int choice, val;
    do {
        cout << "\n1.Push 2.Pop 3.Display 4.Exit\nEnter choice: ";
        cin >> choice;
        switch(choice) {
            case 1:
                cout << "Enter value: ";
                cin >> val;
                push(val);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
        }
    } while(choice!= 4);
    return 0;
}
