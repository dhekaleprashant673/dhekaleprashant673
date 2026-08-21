class Solution {
    public boolean isPalindrome(ListNode head) {  
        //  if(head==null||head.next==null){
        //     return true;
        //  }
        ListNode start=head;
        ListNode end=head;

        while(end !=null&& end.next!=null){
            start=start.next;
            end=end.next.next;

        }
           ListNode prev=null;

        while(start!=null)  {
            ListNode next=start.next;
            start.next=prev;
            prev=start;
            start=prev;
        }    
        ListNode frist=head;
        ListNode second=prev;
        while(second!=null){
          if(frist.val!=second.val)
        {
            return false;
        }
        frist=frist.next;
        second=second.next;
        }
    
        
    return true;
        
    }
}
