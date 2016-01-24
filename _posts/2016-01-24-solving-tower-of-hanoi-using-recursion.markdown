---
published: true
title: Solving Tower of Hanoi using recursion
layout: post
tags: [Tower, of, hanoi, java, recursion, stack]
categories: [Puzzles, Java, programming]
---
The Tower of Hanoi (also called the Tower of Brahma or Lucas' Tower,[1] and sometimes pluralized) is a mathematical game or puzzle. It consists of three rods, and a number of disks of different sizes which can slide onto any rod. The puzzle starts with the disks in a neat stack in ascending order of size on one rod, the smallest at the top, thus making a conical shape.

The objective of the puzzle is to move the entire stack to another rod, obeying the following simple rules:

Only one disk can be moved at a time.
Each move consists of taking the upper disk from one of the stacks and placing it on top of another stack i.e. a disk can only be moved if it is the uppermost disk on a stack.
No disk may be placed on top of a smaller disk.
With three disks, the puzzle can be solved in seven moves. The minimum number of moves required to solve a Tower of Hanoi puzzle is 2n - 1, where n is the number of disks.


I have taken 3 stacks, 1st is called as source where n number of disks are placed. 2nd stack is an auxilary stack and third stack is a destination where disks have to be moved.


package com.ganesh.tower;

import java.util.Stack;

public class TowerOfHanoi {

	Stack source = new Stack<Integer>();
	Stack aux = new Stack<Integer>();
	Stack dest = new Stack<Integer>();

	public void shiftDisks(int n, Stack source, Stack aux, Stack dest) {
		if (n > 0) {

			shiftDisks(n - 1, source, dest, aux);
			dest.push(source.pop());
			shiftDisks(n - 1, aux, source, dest);
		}
	}

	public static void main(String[] args) {
		TowerOfHanoi x = new TowerOfHanoi();
		x.source.push(1);
		x.source.push(2);
		x.source.push(3);

		x.shiftDisks(x.source.size(), x.source, x.aux, x.dest);
		System.out.println("Done");
	}

}
