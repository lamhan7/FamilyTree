package familytree;

import java.util.*;

class Person {
    String name;
    String gender;
    Person parent;
    TreeSet<Person> children;

    Person(String name, String gender) {
        this.name = name;
        this.gender = gender;
        this.children = new TreeSet<>(Comparator.comparing(p -> p.name));
    }
}

public class FamilyTreeDemo {

    private static Map<String, Person> members = new HashMap<>();

    static void addPerson(String name, String gender, String parentName) {
        Person p = new Person(name, gender);
        members.put(name, p);

        if (parentName != null) {
            Person parent = members.get(parentName);
            p.parent = parent;
            parent.children.add(p);
        }
    }

    static void printLineage(String name) {
        Person p = members.get(name);
        while (p != null) {
            System.out.println(p.name);
            p = p.parent;
        }
    }

    public static void main(String[] args) {
        addPerson("John", "M", null);
        addPerson("Alice", "F", "John");
        addPerson("Bob", "M", "John");
        addPerson("Charlie", "M", "Alice");

        System.out.println("Lineage of Charlie:");
        printLineage("Charlie");
    }
}
