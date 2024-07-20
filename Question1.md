
## Question 1

For a student records system with different roles, one can apply encapsulation and role-based access control. With encapsulation the internal state of the object is protected with making the fields private and giving controlled access with methods. Usage is such that different users get different access (read only / read and write).

There should be a 'Student' class that has private fields and methods to read / manipulate those fields. There would be two different views:

'StudentView' that is for students, read only.
<br>
'AdminView' that is for staff, with read and write abilities.

The class designs:

- 'Student' Class, private fields.
- 'StudentView', with read-only methods.
- 'AdminView', extends 'StudentView', has methods to update student info.

Class invariant: Integrity of 'Student' object is kept by control of access through interfaces.

Implementation is best way to describe the mechanisms:

```Java
import java.util.List;

class Student {
    private String name;
    private int enrollmentYear;
    private String major;
    
     // Construvtor for creating new student
     // @param name Name of student
     // @param enrollmentYear Year student enrolled
     // @param major Major of student
    public Student(String name, int enrollmentYear, String major) {
        this.name = name;
        this.enrollmentYear = enrollmentYear;
        this.major = major;
    }
    
    public String getName() {
        return name;
    }
    
    public int getEnrollmentYear() {
        return enrollmentYear;
    }
    
    public String getMajor() {
        return major;
    }
    
     // Set name of the student
     // @param name Name of the student
     // @pre name is not null and not empty
     // @post Name of the student is updated
    protected void setName(String name) {
        if (name == null || name.isEmpty()) {
            throw new IllegalArgumentException("Name can't be null or empty");
        }
        this.name = name;
    }
    
     // Sets major of the student
     // @param major Major of the student
     // @pre major is not null and not empty
     // @post Major of the student is updated
    protected void setMajor(String major) {
        if (major == null || major.isEmpty()) {
            throw new IllegalArgumentException("Major cant be null or empty");
        }
        this.major = major;
    }
}

// Interface for read only access to a Student
interface StudentView {
    
    String getName();
    
    int getEnrollmentYear();
    
    String getMajor();
}

 // Interface for read & write access to Student.
interface AdminView extends StudentView {
    
     // @param name Name of the student.
     // @pre name is not null and not empty
     // @post Name of the student is updated
    void setName(String name);
    
    
     // * @param major Major of the student.
     // * @pre major is not null and not empty.
     // * @post Major of the student is updated
    void setMajor(String major);
}

// Implemntation of AdminView fo r both read and write access.
class StudentImplement implements AdminView {
    private Student student;
    
    
     // Constructor for creating a StudentImplement.
     // @param student The student object to be wrapped.
    public StudentImplement(Student student) {
        this.student = student;
    }
    
    // Implementing read-only methods from StudentView
    @Override
    public String getName() {
        return student.getName();
    }
    
    @Override
    public int getEnrollmentYear() {
        return student.getEnrollmentYear();
    }
    
    @Override
    public String getMajor() {
        return student.getMajor();
    }
    
    // Implementing update methods from AdminView
    @Override
    public void setName(String name) {
        student.setName(name);
    }
    
    @Override
    public void setMajor(String major) {
        student.setMajor(major);
    }
}
```



