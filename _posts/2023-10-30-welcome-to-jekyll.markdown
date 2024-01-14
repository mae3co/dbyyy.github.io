---
layout: post
title: 백준 queue
date: '2023-10-30 20:55:26 +0900'
categories: jekyll update
published: true
---
~~~java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Deque;
import java.util.LinkedList;
import java.util.Queue;
import java.util.StringTokenizer;

public class Main {
    static Deque<Integer> queue = new LinkedList<>();
    static StringBuilder sb;

    public static void main(String[] args) throws IOException {
        BufferedReader br = new BufferedReader(new InputStreamReader(System.in));
        int n = Integer.parseInt(br.readLine());
        queue = new LinkedList<>();
        StringTokenizer st;
        sb = new StringBuilder();
        String s;
        for (int i = 0; i < n; i++) {
            st = new StringTokenizer(br.readLine());
            s = st.nextToken();
            if (s.equals("push")) add(Integer.parseInt(st.nextToken()));
            if (s.equals("pop")) poll();
            if (s.equals("size")) size();
            if (s.equals("empty")) empty();
            if (s.equals("front")) peek();
            if (s.equals("back")) lastPeek();
        }
        System.out.print(sb);
    }
        public static void add(int o) {
            queue.add(o);
        }

        public static void poll() {
            if(queue.isEmpty()) {
                sb.append(-1 +System.lineSeparator());
            } else {
                sb.append(queue.poll()+System.lineSeparator());
            }
        }

        public static void peek() {
            if(queue.isEmpty()) {
                sb.append(-1 +System.lineSeparator());
            } else {
                sb.append(queue.peek()+System.lineSeparator());
            }
        }

        public static void size() {
            sb.append(queue.size() +System.lineSeparator());
        }

        public static void empty() {
            if(queue.isEmpty()) {
                sb.append(1 +System.lineSeparator());
            }else {
                sb.append(0 +System.lineSeparator());
            }
        }

    public static void lastPeek() {
        if(queue.isEmpty()) {
            sb.append(-1 +System.lineSeparator());
        } else {
            sb.append(queue.peekLast() +System.lineSeparator());
        }
    }

}
~~~
