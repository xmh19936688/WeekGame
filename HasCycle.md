#����
����һ�����������ж������Ƿ��л����������������ʽ��
A -> B -> C -> D -> E -> F -> G -> H -> I -> D(ָ��ǰ���D�����л�)
�����㶨�壺
struct ListNode
{
    ListNode* next;
}
����ԭ�ͣ�
bool hasCycle( const ListNode* head )
{
}

#˼·
����Ϊ�ٳ��ܲ���һ�����ܵĿ죬һ�����ܵ���������ǻ��Σ���Ļᳬ������

#����
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
    //p->next=0;//�޻�
    p->next=back;//�л�
    
	int result=hasCycle(H);
	printf("%d\n",result);
}

int hasCycle(const Node *p)  
{  
    Node * slow = p; // �������� ÿ��ǰ��һ���ڵ�  
    Node * fast = p; // �����Ŀ죬ÿ��ǰ�������ڵ�  
    if(fast != NULL)  
    {  
        fast = fast ->next; //��fast����һ��  
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