//maxElement in Stack

#include <iostream>
#include <fstream>
#include <ostream>
#include <string>
#include <stdlib.h>
#include <stack>
using namespace std;

int maxElement(stack<int> stack_1, stack<int> stack_2) {
	int current_max = stack_1.top();

		stack_2.push(stack_1.top());
	stack_1.pop();

	while (!stack_1.empty()) {
		if (stack_1.top() < current_max) {
			current_max = stack_1.top();
		}

		stack_2.push(stack_1.top());
		stack_1.pop();
		}

	while(!stack_2.empty()) {
		stack_1.push(stack_2.top());
		stack_2.pop();
	}

	return current_max;
}

  int main() {
    /* Enter your code here. Read input from STDIN. Print output to STDOUT */
    stack <int> s;
    int n,x,t;
    cin>>n;
    while(n--){
        cin>>t;
        if(t==1){
            cin>>x;
            if(s.empty())
              s.push(x);
             else
              s.push(max(x,s.top()));
        }
        else if(t==2){
                 if (!s.empty())
                     s.pop();
        }
         if(t==3){
             cout<<s.top()<<endl;

        }

    }
    return 0;
}
