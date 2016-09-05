#问题
给定一个单向链表，判断其中是否有环，即类似下面的形式：
A -> B -> C -> D -> E -> F -> G -> H -> I -> D(指向前面的D，即有环)
链表结点定义：
struct ListNode
{
    ListNode* next;
}
函数原型：
bool hasCycle( const ListNode* head )
{
}

#思路
抽象为操场跑步，一个人跑的快，一个人跑的慢，如果是环形，快的会超过慢的

#代码
```
#include<stdio.h>
#include<string.h>

typedef struct ListNode
{
    struct ListNode* next;
}Node;

int hasCycle(const Node * a);
int true=1,false=-1;

void main(){
    Node*H=(Node*)malloc(sizeof(Node));
    H->next=(Node*)malloc(sizeof(Node));
    Node*p=H->next;
    Node * back=H->next;
    for(int i=0;i<5;i++){
        p->next=(Node*)malloc(sizeof(Node));
        p=p->next;
    }
    //p->next=0;//无环
    p->next=back;//有环
    
	int result=hasCycle(H);
	printf("%d\n",result);
}

int hasCycle(const Node *p)  
{  
    Node * slow = p; // 遍历的慢 每次前进一个节点  
    Node * fast = p; // 遍历的快，每次前进二个节点  
    if(fast != NULL)  
    {  
        fast = fast ->next; //让fast先走一步  
    }  
    while (fast&& fast->next)  
    {  
        if (fast == slow || fast->next == slow)  
        {  
            break;  
        }  
        slow = slow->next;  
        fast = fast->next->next;  
    }  
    if(fast == NULL || fast->next == NULL){
        return false;
    }else{
        return true;
    }
}
```