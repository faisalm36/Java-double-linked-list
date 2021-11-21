# Java-double-linked-list
import java.util.*;
public class doublyLinkedList {
	static class Node{
	int data;
	Node p;
	Node n;
	public Node next;
		}
	static Node Head;
	static void addElement(int num) {
		
	if (Head == null) {
		Node n = new Node();
		n.data =num;
		n.next = n.p = n;
		Head = n;
		return;
	}
	Node lastNODE = (Head).p;
	Node n = new Node();
	n.data = num;
	n.next = Head;
	(Head).p = n;
	lastNODE.next = n;
}
	static void getElement() {
		Node temp = Head;
		while(temp.next!=Head) {
			System.out.printf("%d", temp.data);
			temp = temp.next;
		}
		System.out.printf("%d", temp.data);
	}
	static int size() {
		Node temp = Head;
		int i = 1;
		while (temp.next != Head) {
			temp = temp.next;
			i+=1;
		}
		return i;
	}
	static void update(int x,int y) {
		Node temp = Head;
	    if(size() == 1)
        {
            if(temp.data == x){
                temp.data=y;
                return;
            }
        }
        while (temp.next != Head)	{   
            if(temp.data == x){
                temp.data=y;
                return;
            }
            temp = temp.next;  
        		}	  
			}  
	public static void main(String[] args) {
        Node list = null;        
        Scanner sc=new Scanner(System.in);            
        System.out.printf("Enter size of doubly Circular linked list: "); 
        int no= sc.nextInt();
        while(no>0)	{
            int x=sc.nextInt();
            addElement(x); 
            no-=1;
        }
        System.out.println(" Get elements: ");
        getElement();
        System.out.println("\nSize of circular doubly linked list: "+ size());
        System.out.println("Enter the element to be updated : ");
        int x=sc.nextInt();
        System.out.println("Enter the new element to update : ");
        int y=sc.nextInt();
        update(x,y);
        System.out.println("\nElements after updating ");
        getElement();
    }  
}
