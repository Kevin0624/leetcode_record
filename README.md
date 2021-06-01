# LeetCode Record

## Linked List

### 1290. Convert Binary Number in a Linked list to Integer

my solution
* time complexity: O(n)
* space complexity: O(1)
```c=
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */

// 想法 : 先 reverse 在 traverse
int getDecimalValue(struct ListNode* head){
    
    struct ListNode *ptr = head;
    struct ListNode *current = head;
    struct ListNode *previous = NULL;
    struct ListNode *preceding = NULL;
    int temp=0;
    int counter=0;
    
    // linked list reverse
    while(current !=NULL){
        //temp = temp + current->val*pow(2, counter);
        preceding = current->next;
        current->next = previous;
        previous = current;
        current = preceding;
    }
    
    while(previous!=NULL){
        temp = temp + previous->val*pow(2, counter);
        previous = previous->next;
        counter++;
    }
    
    return temp;
}
```
### 876. Middle of the Linked List
```c=
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     struct ListNode *next;
 * };
 */


struct ListNode* middleNode(struct ListNode* head){
    
    struct ListNode *ptr = head;
    struct ListNode *ptr2 = head;
    int counter = 0;
    int counter_2 = 0;
    int target = 0;
    
    while(ptr!=NULL){
        counter++;
        ptr = ptr->next;
    }
    
    target = (counter/2);
    
    while(counter_2 <= target){
        
        if (counter_2 == target){
            break;
        }
        ptr2 = ptr2->next;
        counter_2++;
    }
    
    return ptr2;

}
```
