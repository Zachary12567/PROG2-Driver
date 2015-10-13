# PROG2-Driver
Driver file for LinearList implements LinearListADT
/* Grading program for prog1, 
 * CS310 Fall 2015
 * @author Zachary12567
 */


import data_structures.*;

public class p2d {
    private LinearListADT<Integer> list;
    private static final int MAX_SIZE = 100;
    
    public p2d() {
        list = new LinearList();
        runTests();
        }
        
    private void runTests() {
try{    
        print();
        for(int i=100; i > 0; i--) 
            list.addFirst(i);
        print("1 Should print 1 .. 100");
        print();
        System.out.println("front: " + list.peekFirst() + " tail: " + list.peekLast() + " size: " + list.size());
        for(int i=101; i <= 200; i++)
            list.addLast(i);
        print("2 Should print 1 .. 200");
        print();

        for(int i = 1; i <= 100; i++)
           if(list.removeFirst() != i)
                print("3 ERROR in removeFirst at" + i);
        print("3 Should print 101 ..200");
        print();

        for(int i=200; i > 102; i--)                                            // leave two elements
            if(list.removeLast() != i)
                print("4 ERROR in removeFirst at" + i);
        print("Should print 101 102");
        print();   

        for(int i=0; i < MAX_SIZE-2; i++)
            list.addFirst(-i);   
        print("\n5 Size is now: " + list.size());
        print("\n5a Should print -97, -96, ... 0, 101, 102.\n");
        print();
        print("Should print -97+25 (-72) through (-22)");
        
        for(int i=0; i < MAX_SIZE >> 2; i++) {                                  //for 25 times:
            list.removeFirst();
            list.removeLast();
            }  
        print();
        print("6 Size should be 50: " + list.size());

        list.clear();
        list.addLast(2);
        for (int i = 0; i > list.size(); i++) {                                 // for size times:
                System.out.println(i);
        }
        list.addFirst(1);
        print("front and tail should be 1: " + list.peekFirst() + " " + list.peekLast() + " size is 1: " + list.size());
        print();
        list.clear();
        print();
}
catch(Exception e) {
    System.out.println("In first catch block");
    e.printStackTrace();
    }

try {    
        list.clear();
        print();
        print("Above should print nothing..");

        list.addLast(5);
        if(list.peekFirst() != 5) print("7 ERROR in peekFirst");
        print("peekFirst should be 5: " + list.peekFirst());
        print("peekLast should also be 5: " + list.peekLast());
        list.addLast(6);
        list.addFirst(4);
        print("Should print 4, 5, 6");
        print();
        if(list.remove(5) != 5) print("8 ERROR in remove");
        print("head should be 4: " + list.peekFirst() + ". tail should be 6: " + list.peekLast() + ". size is 2: " + list.size());
        print("Should print 4, 6");
        print();

        print("contain 4? " + list.contains(4));
        print("contains 5? " + list.contains(5));
        if(list.contains(5)) print("9 ERROR in contains");

        if(list.find(5) != null) print("10 ERROR in find");
        if(list.isEmpty()) print("11 ERROR in isEmpty");
/*      list.clear
        print();
        print("contains 3? " + list.contains(3) + "\ncontains 6? " + list.contains(6));
        print("find 5: " + list.find(5) + "\nfind 4: " + list.find(4));
/*

        list.addFirst(15);
        if(list.peekLast() != 15) print("12 ERROR in peekLast");
        if(list.remove(15) != 15) print("13 ERROR in remove");
        if(list.contains(15)) print("14 ERROR in contains");        
        if(list.find(15) != null) print("15 ERROR in find");
*/
           }
catch(Exception e) {
    System.out.println("16 In second catch block");
    e.printStackTrace();
    } 
/*
try {
    list.clear();
    for(int i=0; i < MAX_SIZE; i++)
        list.addFirst(i);
    for(int j=0; j < 20; j++) {
        for(int i=0; i < 1000; i++)
            if(list.removeFirst() == null) print("17 ERROR in removeFirst");
        for(int i=0; i < 1000; i++)
            if(!list.addLast(i)) print("18 ERROR in addLast");
            }
            
    for(int j=0; j < 20; j++) {
        for(int i=0; i < 1000; i++)
            if(list.removeLast() == null) print("19 ERROR in removeLast");
        for(int i=0; i < 1000; i++)
            if(!list.addFirst(i)) print("20 ERROR in addFirst");
            }            
            
    if(!list.isFull()) print("21 ERROR in isFull");
    if(list.addFirst(5)) print("22 ERROR in addFirst, beyond max size");
    if(list.addLast(5)) print("23 ERROR in addFirst, beyond max size");    
    list.clear();
    }
catch(Exception e) {
    System.out.println("24 In third catch block");
    e.printStackTrace();
    } 
        
try {    
    if(list.find(50) != null) print("24 ERROR in unsuccessful search");
    }
catch(Exception e) {}    
try {
    if(list.peekFirst() != null) print("25 ERROR in peekFirst");
    }
catch(Exception e) {} 
try {
    if(list.peekLast() != null) print("26 ERROR in peekLast");
    }
catch(Exception e) {}    
*/
}
                           

       
    private void print(String s) {
        System.out.println(s);
        }
       
    private void print() {
        for(Integer i : list)
            System.out.print(i + " ");
        System.out.println();
        }
        
    public static void main(String [] args) {
        new p2d();
        }
    }
