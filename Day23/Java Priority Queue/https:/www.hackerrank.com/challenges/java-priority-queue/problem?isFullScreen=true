import java.util.ArrayList;
import java.util.List;
import java.util.Scanner;
import java.util.*;
import java.util.stream.Collectors;

class Priorities {
    
    public List<Student> getStudents(List<String> events) {
        PriorityQueue<Student> q = new PriorityQueue<>();

        for (String event : events) {
            if (event.contains("ENTER")) {
                String[] student = event.split(" ");
                Student s = new Student(
                        student[1],
                        Double.parseDouble(student[2]),
                        Integer.parseInt(student[3]));
                q.add(s);
            }

            if (event.contains("SERVED")) {
                if (q.size() > 0) {
                    q.poll();
                }
            }
        }
        
        return q.stream().sorted().collect(Collectors.toList());
    }
}

class Student implements Comparable<Student>{
    
    private String name;
    private double cgpa;
    private int id;
    
    public Student(){}
    
    public Student(String name, double cgpa, int id) {
        this.id = id;
        this.name = name;
        this.cgpa = cgpa;
    }
    
    public int getId() {
        return this.id;
    }
    
    public String getName() {
        return this.name;
    }
    
    public double getCGPA() {
        return this.cgpa;
    }
    
    @Override
    public int compareTo(Student o) {
        if(this.cgpa == o.cgpa) {
            if(this.name.equals(o.name)) {
                return this.id - o.id;
            }else {
                return this.name.compareTo(o.name);
            }
        }else {
            return this.cgpa < o.cgpa ? 1 : -1;
        }
    }
    
}


public class Solution {
    private final static Scanner scan = new Scanner(System.in);
    private final static Priorities priorities = new Priorities();
    
    public static void main(String[] args) {
        int totalEvents = Integer.parseInt(scan.nextLine());    
        List<String> events = new ArrayList<>();
        
        while (totalEvents-- != 0) {
            String event = scan.nextLine();
            events.add(event);
        }
        
        List<Student> students = priorities.getStudents(events);
        
        if (students.isEmpty()) {
            System.out.println("EMPTY");
        } else {
            for (Student st: students) {
                System.out.println(st.getName());
            }
        }
    }
}
