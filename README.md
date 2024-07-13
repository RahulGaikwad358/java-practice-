# java-practice-
Coding question

// OOPS
public class oopshoga {
    public static void main(String args[]) {
        Pen p1 = new Pen();
        p1.setcolor("blue");
        System.out.println(p1.getcolor());
        p1.settip(5);
        System.out.println(p1.gettip());
        p1.setcolor("yelloe");
        System.out.println(p1.getcolor());

        Bankaccount myacc = new Bankaccount();
        myacc.username = "rahul";
        myacc.setpassword("dadad");
          
        vidyarti v1 = new vidyarti();
      //  System.out.println(v1.name);
      v1.name = "rahul";
      v1.roll = 55;
      v1.password = "cuaghf";
      v1.marks[0] = 100;
      v1.marks[1] = 87;
      v1.marks[2] = 99;


      vidyarti v2 = new vidyarti(v1);
      v2.password = "ggjjj";
      v1.marks[1] = 66;

      for(int i = 0; i<3; i++) {
        System.out.println(v2.marks[i]);
      }

      
    

        
    }
}
class vidyarti {

    String name;
    int roll;
    String password;
    int marks[];

    // shallow copy constructor
    //vidyarti(vidyarti v1) {
      //  marks = new int[3];
      //  this.name = v1.name;
      //  this.roll = v1.roll;
      //  this.marks = v1.marks;
   // }

    // depp copy constructor
    vidyarti(vidyarti v1) {
        marks = new int[3];
        this.name = name;
        this.roll = roll;
        for(int i = 0; i<3; i++){
            this.marks[i] = v1.marks[i];
        }
    }


    vidyarti() {
          marks = new int[3];
        System.out.println("connstructor is  called");
    }
    vidyarti(int roll) {
        marks = new int[3];
        this.roll = roll;
    }
    vidyarti(String name) {
        marks =  new int[3];
        this.name = name;
    }
}

class Bankaccount {
    public String username;
    private String password;

    public void setpassword(String pwd) {
        password = pwd;
    }
}

class Pen {
   private String color;
   private int tip;
    
    String getcolor() {
        return this.color;
    }

    int gettip(){
        return this.tip;
    }

    void setcolor(String newcolour) {
        color = newcolour;
    }

    void settip(int newtip){
        tip = newtip;
    }

}

class Student {
    String name;
    int age;
    float percentage;

    void calpercentage(int phy, int math, int hist) {
        percentage = (phy + math + hist)/3;
    }
}

// basic Question
public class hazar {
    

    public static boolean ispalindrome(int arr[]) {
        int n = arr.length;
          for(int i = 0; i<n/2; i++) {
            if(arr[i] != arr[n-i-1]){
                return false;
            }
          }
          return true;
        
    }

   public static boolean pali(String str){

    for(int i = 0; i<str.length()/2; i++) {
        int n = str.length();
        if(str.charAt(i) != str.charAt(n-i-1)) {
            return false;
        }
    }

    return true;
   }

   public static  void reverse(int arr[]) {
     int  i = 0;
     int n = arr.length-1;
     while(i < n) {
        int temp = arr[n];
        arr[n] =  arr[i];
        arr[i] = temp; 
        i++;
        n--;
        
     }
   }
    public static void main(String args[]) {
       
        /* 
       int n;
       System.out.println("enter rhe number");
       Scanner sc = new Scanner(System.in);
       int num =  sc.nextInt();
       int original = num;
       int cube = 0;

       while (num > 0) {
        int reminder = num % 10; // 3
        cube = cube +(reminder*reminder*reminder);
        num = num /10; // 15
       }
       if( original == cube) {
        System.out.println("it is armstrng number");
       }

       else{
        System.out.println(" it is not armstromg number15");
       } 


       // fizz buzz
       int n;
       Scanner sc = new Scanner(System.in);
       System.out.println("enter he number");
       int num = sc.nextInt();

       for(int i = 0; i<=num; i++) {

        if(i % 3 == 0) {
            System.out.println("fizz");
        }
         if(i % 5 == 0)  {
            System.out.println("fuzz");
        }
        if(i % 3 == 0 && i % 5 == 0 ){
            System.out.println("fzz buzz");
        }
        else{
            System.out.println("no"+ i);
        }
          


       } 

       // prime number = is greater than 1  and number which should not be divisible by others numbers other  than 1 and itself.

       for(int i = 0; i< 100; i++) {
        boolean isprime = true;

        if(i > 1) {

            for(int j = 2; j<i; j++) {
                if(i%j == 0){
                 isprime = false;
                }
            }

        } else{
            isprime = false;
        }

        if(isprime) {
            System.out.println(i);
        } 

        int n;
        Scanner sc = new Scanner(System.in) ;
        n = sc.nextInt();
        boolean isprime = true;

        for(int i = 2; i<=n/2; i++) {
            System.out.println(i);
            if(n % i == 0) {
              isprime = false;
            }
        }
        if(isprime) {
            System.out.println("isprime");
        } else{
            System.out.println("not prime");
        } */
      //  int arr[] = {1,2,2,1};
      //  System.out.println(ispalindrome(arr));

     // String str = "noon";
      // System.out.println(pali(str));
       int arr[] = {1,2,3,4};
         reverse(arr);
         for(int i= 0; i<arr.length; i++){
            System.out.print(arr[i]);
         }
         System.out.println();
       }
      


    }



/// linked list

    public class linklist {
    
     public static class Node {
        int data;
        Node next;

        public Node(int data) {
            this.data = data;
            this.next = null;
        }
     }

     public static Node head;
     public static Node tail;
     public static int size;

       
     public void addfirst(int data) {// tc - o(1)
        // step1 = create new node
        Node newnode = new Node(data);
        size++;
        if(head == null) {
            head = tail = newnode;
            return;
        }

        // step 2 = newnode next = head
        newnode.next = head; // link

        //step3 - head = newnode
        head = newnode;
     }

     public void print() { //  tc o(n)

        //base case
        if(head == null){
            System.out.println("ll is empty");
            return;
        }
        Node temp = head;

        while(temp != null ){
            System.out.print(temp.data);
            temp = temp.next;
        }

        System.out.println("null");
     }

     public void addlast(int data) { // tc - o(1)

        // step 1 - create new node
        Node newnode = new Node(data);
        size++;
        if(head == null){
            head = tail = newnode;
        }
        tail.next = newnode;
        tail = newnode;

     }

     public void add(int idx, int data){

        if(idx == 0){
            addfirst(data);
            return;
        }
        Node newnode = new Node(data);
        size++;
        Node temp = head;
        int i = 0;

        while(i < idx-1){
            temp = temp.next;
            i++;
        }

        // i = idx - 1; temp = prev
        newnode.next = temp.next;
        temp.next = newnode;

     }

     public int removefirst(){

        if(size == 0){
            System.out.println("empty");
            return Integer.MIN_VALUE;
        }
        else if(size == 1){
            int val = head.data;
            head = tail = null;
            size = 0;
            return val;
        }
        int val = head.data;
        head = head.next;
        size--;
        return val;
     }

     public int removelast(){
        if(size == 0){
            System.out.println("lll is mpety");
            return Integer.MIN_VALUE;
        } else if(size == 1){

            int val = head.data;
            head = tail = null;
            size = 0;
            return val;

        }

        // prev = i = size - 2;
        Node prev = head;
        for(int i = 0; i<size-2; i++){
            prev = prev.next;
        }

        int val = prev.next.data;// tail ka datat
        prev.next = null;
        tail = prev;
        size--;

        return val;
     }

     // for iterative search
     public int itersearch(int key) {
        Node temp = head;
        int i = 0;

        while(temp != null){
            if(temp.data == key){
                return i;
            }

            temp = temp.next;
            i++;
        }

        return -1;
     }

     public void reverse() { // tc = o(n)
        Node prev = null;
        Node curr  = tail = head;
        Node next;

        while(curr != null) {
            next =  curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;

        }


        head = prev;
        
     }

     //  Q. delete nthnode from end
     public void deletenhfromnode(int n) {
        // calaculate size
        int sizee = 0;
        Node temp = head;
        while(temp != null){
            temp = temp.next;
            sizee++;
        }

        if(n == size) {
            head = head.next; //removefirst
            return;
        }

        //size - n
        int i = 1;
        int itofind = sizee - n;
        Node prev = head;
        while(i < itofind) {
            prev = prev.next;
            i++;
        }

        prev.next = prev.next.next;
        return;

     }

     /// find middle  slow fast approach
     public Node findmid(Node head){

        Node slow = head;
        Node fast = head;

        while(fast != null && fast.next != null){
            slow = slow.next;
            fast = fast.next.next;
        }

        return slow;
     }

     // palindrome
     public boolean checkpalindromee() {
        if(head == null || head.next == null){
            return true;
        }

        // step 1 = find mid
        Node midnode = findmid(head);

        // reverse second half
        Node prev = null;
        Node curr = head;
        Node next;

        while(curr != null){
            next = curr.next;
            curr.next = prev;
            prev = curr;
            curr = next;
        }

        Node right = prev ; // right half head
        Node left = head; 

        //step 3 - check left half & right half
        while(right != null){
            if(left.data != right.data){
                return false;
            }

            left = left.next;
            right = right.next;
        }

          return true;
     }

     // detect cycle
     public static boolean iscycle() {
        Node slow =  head;
        Node fast = head;

        while(fast != null  && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;

            if(slow == fast) {
                return true; 
            }
        }

        return false;
     }

     // remove cycle loop

     public static void removecycle() {
        //detect cycle
        Node slow = head;
        Node fast = head;

        boolean cycle = false;
        while(fast != null && fast.next != null){
            slow = slow.next;
            fast = fast.next.next;
            if(fast == slow){
                cycle = true;
                break;
            }

        }

        if(cycle == false) {
            return;
        }

        //find meeting point
        slow = head;
        Node prev = null;// last node

        while( slow != fast){
            prev = fast;
            slow = slow.next;
            fast = fast.next;

        }
        // remove cycle -> last.next = null
        prev.next = null;
     }

     
     public Node getmid(Node head){
        Node slow = head;
        Node fast = head.next;

        while(fast != null && fast.next !=  null){
            slow = slow.next;
            fast = fast.next.next;
        }

        return slow;

     }

     private Node merge(Node head1, Node head2){
    
        Node mergell = new Node(-1);
        Node temp = mergell;

        while(head1 != null && head2 != null){
            if(head1.data <= head2.data) {
                temp.next = head1;
                head1 = head1.next;
                temp = temp.next;
            } else{
                temp.next = head2;
                head2 = head2.next;
                temp = temp.next;           
            }
        }

        // for remainning elemnets
        while(head1 != null){
            temp.next = head1;
            head1 = head1.next;
            temp = temp.next;

        }

        while(head2 != null){
            temp.next = head2;
            head2 = head2.next;
            temp = temp.next;
        }

        return mergell.next;
     }

     // mersort in ll
    public Node mergesort(Node head) {

        if(head == null ||  head.next == null){
            return head;
        }

        // find mid
        Node mid = getmid(head);

        // left & right ms
        Node righthead = mid.next;
        mid.next = null;
        Node newleft = mergesort(head);
        Node newright = mergesort(righthead);

        //merge
        return merge(newleft, newright);
        
    }

    //for zigzag linkedlist
    public void zigzag()  {

   //find mid
   Node slow = head;
   Node fast = head.next;

   while(fast != null && fast.next != null){
    slow = slow.next;
    fast = fast.next.next;
   }

   Node mid = slow;


    // reverse 2nd half

    Node curr = mid.next;
    mid.next = null;
    Node prev = null;
    Node next;

    while(curr != null){
        next = curr.next;
        curr.next = prev;

        prev = curr;
        curr = next;
    }

    Node left = head;
    Node right = prev;
    Node nextL, nextR;

    // alt merge - zig zag merge
    while(left != null && right != null) {
        nextL = left.next;
        left.next = right;
        nextR = right.next;
        right.next = nextL;

        left = nextL;
        right = nextR;
    }
    }

    // Mergesort
    public class Mergesort {

    public static void print(int arr[]) {

        for(int i = 0; i< arr.length; i++) {
            System.out.print(arr[i] + " ");
        }
    
        System.out.println();
     }
    
    

    public static void  meergesort(int arr[], int s, int e) {


        // base case
        if(s >= e) {
            return;
        }
        // kaam
        int mid = s + (e -s)/2;
        meergesort(arr, s, mid-1);// left part
        meergesort(arr, mid + 1, e); // for right part

        merge(arr, s, mid, e);
    }

    public  static void merge(int arr[], int s, int mid, int e) {

        int temp[] = new int[e-s+1];
   
        int i = s;
        int j = mid + 1;
        int k = 0 ;

        while ( i <= mid && j <= e) {
            if( arr[i] < arr[j]) {
                temp[k] = arr[i];
                i++;
            }
             else {
                temp[k] = arr[j];
                j++;
             }

             k++;
        }

        // remiannig part

        while (i <= mid) {
            temp[k++] = arr[i++];
        }

        // 
        while ( j <= e) {
            temp[k++] = arr[j++];  
        }


        //n copy temp   to original array
        for( k = 0, i = s ; k< temp.length;k++, i++ ) {
             arr[i] = temp[k];
        }


    }
public static void main(String args[]) {

    int arr[] = {1,5,3,6,8};
    //print(arr);
    meergesort(arr, 0, arr.length - 1); 
    //
  print(arr);
    
    
}

}

// RECURSION
public class phrecursion {
    
    // print in decreasing order 
    public static void printdec(int n) {
        // base case
        if(n == 1){
            System.out.println(n);
            return;
        }

        System.out.println(n + " ");
        printdec(n-1);
    }

    // print in increasing order
    // base case
    public static void printinc(int n) {
        // base case
        if(n == 1){
            System.out.println(n);
            return;
        }
        printinc(n-1);
        System.out.println(n);
    }

    // print factorial
    public static int fact(int n) {
        // base case
        if( n == 0) {
            return 1;
        }

        int m = fact(n-1);
        int fn = n * fact(n-1);
        return fn;
    }

    // calculated sum
    public static int sum(int n) {
        // base case
        if(n == 1) {
            return 1;
        }

        int snm = sum(n-1);
        int calsum  = n + snm;
        return calsum;
    }

    public static int fib(int n) {

        if(n == 0 || n == 1 ) {
            return n;
        }

        return fib(n-1) + fib(n-2);
    }

    
      // check if sorted array or not
      public static boolean sorted(int arr[], int i) {

        // base case
        if(i == arr.length-1) {
            return true;
        }

        if(arr[i] > arr[i+1]) {
            return false ;
        }

         return sorted(arr, i+1);
      }

      public static int firstocc( int arr[],int  key,  int i) {

        // base case 
        if( i == arr.length - 1) {
            return -1;
        }
        if(arr[i] == key) {
            return i;
        }

        return firstocc(arr, key, i+1);
      }

      // for last occurence
      
        public static int lastocccurence(int arr[], int key, int i) {

            // base case 
            if(i == arr.length){
                return -1;
            }
            int isfound = lastocccurence(arr, key, i+1); //first check forwar thenn check backward.
            if(isfound == -1 && arr[i] == key){
                return i;
            }

            return isfound;
        }

        // find power x^n // complexity o7u(n)
        public static int power(int x , int n) {

            // base case
            if(n == 0) {
                return 1;
            }

            int xmn = power(x, n-1);
            int xn =  x * xmn;
            return xn;
        }

        // ootized solution powerx^n // complexity o(logn)
        public static int optimizedpower(int x, int n) {
            // base case
            if(n == 0) {
                return 1;
            }

            // for even number
            int halfpower = optimizedpower(x, n/2);
             int halpowrrsq = halfpower * halfpower;
            // for odd number
            if(n %2 != 0) {
                halpowrrsq = x * halpowrrsq;
            }

            return halpowrrsq;
        }

       public static void removeduplicastes(String str, int i, StringBuilder newstr, boolean map[]) {

        // base case
        if(i == str.length()){
           System.out.println(newstr);
        }

        // kaam
        char currchar = str.charAt(i);
        if(map[currchar - 'a'] == true)  {
            // duplicate
            removeduplicastes(str, i+1, newstr, map);
        } 
        else {
            map[currchar - 'a'] = true;
            removeduplicastes(str, i, newstr.append(str), map);
        }
       }

       public static void main(String[] args) {
       // int n = 58;
        int arr[] = {1,2,3,4,3,5, 5};
       // printdec(n);
      // printinc(n);

   // System.out.println(fib(n));
    
   //System.out.println(sorted(arr, 0));
    // System.out.println(lastocccurence(arr, 3, 0));
   // System.out.println(power(2, 10));
   // System.out.println(optimizedpower(2, 10));
   String str = "appnacooleg";

 removeduplicastes(str, 0, new StringBuilder(""), new boolean[26]);


        


    }
}

   

