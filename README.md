# pairwiseswap-streek1//cpp
class Solution
{
    public:
    Node* pairWiseSwap(struct Node* head) 
    {
        // The task is to complete this method
          if(head->next == NULL)
            return head;
            
        Node *start = head;
        Node *last = new Node(0);
        Node *ans = last;
        
        while(start != NULL &&  start->next != NULL){
            Node *tmp = start->next;
            start->next = tmp->next;
            tmp->next = start;
            last->next =tmp;
            last = start;
            start = start->next;
        }
        return ans->next;
    }
};
