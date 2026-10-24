import java.util.Scanner;

public class Main {

    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    // Detect and remove cycle
    static void removeCycle(Node head) {
        if (head == null || head.next == null) {
            return;
        }

        Node slow = head;
        Node fast = head;

        // Detect cycle
        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;

            if (slow == fast) {
                break;
            }
        }

        // No cycle
        if (fast == null || fast.next == null) {
            return;
        }

        // Find starting point of cycle
        slow = head;

        while (slow != fast) {
            slow = slow.next;
            fast = fast.next;
        }

        // Find last node of cycle
        Node cycleStart = slow;
        Node temp = cycleStart;

        while (temp.next != cycleStart) {
            temp = temp.next;
        }

        // Remove cycle
        temp.next = null;
    }

    // Reverse nodes in groups of K
    static Node reverseKGroup(Node head, int k) {
        if (head == null || k <= 1) {
            return head;
        }

        Node current = head;
        Node prev = null;
        Node next = null;

        int count = 0;

        // Check whether K nodes are available
        Node temp = head;
        while (temp != null && count < k) {
            temp = temp.next;
            count++;
        }

        // Reverse remaining nodes also
        if (count > 0) {
            current = head;
            prev = null;

            for (int i = 0; i < count; i++) {
                next = current.next;
                current.next = prev;
                prev = current;
                current = next;
            }

            head.next = reverseKGroup(current, k);

            return prev;
        }

        return head;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in)
