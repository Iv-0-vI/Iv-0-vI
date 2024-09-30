import java.io.*;
import java.util.ArrayList;
import java.util.List;

// 定义个人信息类
class PersonInfo {
    String name;
    int age;
    String job;

    PersonInfo(String name, int age, String job) {
        this.name = name;
        this.age = age;
        this.job = job;
    }

    @Override
    public String toString() {
        return name + "," + age + "," + job;
    }
}

public class PersonInfoSystem {
    private List<PersonInfo> personInfoList;

    public PersonInfoSystem() {
        personInfoList = new ArrayList<>();
    }

    // 添加个人信息
    public void addPersonInfo(String name, int age, String job) {
        personInfoList.add(new PersonInfo(name, age, job));
    }

    // 将个人信息写入文件
    public void writeToFile(String fileName) throws IOException {
        try (BufferedWriter writer = new BufferedWriter(new FileWriter(fileName))) {
            for (PersonInfo person : personInfoList) {
                writer.write(person.toString());
                writer.newLine();
            }
        }
    }

    // 从文件读取个人信息
    public void readFromFile(String fileName) throws IOException {
        try (BufferedReader reader = new BufferedReader(new FileReader(fileName))) {
            String line;
            while ((line = reader.readLine()) != null) {
                String[] parts = line.split(",");
                if (parts.length >= 3) {
                    addPersonInfo(parts[0], Integer.parseInt(parts[1]), parts[2]);
                }
            }
        }
    }

    public static void main(String[] args) {
        PersonInfoSystem system = new PersonInfoSystem();

        // 添加个人信息
        system.addPersonInfo("Alice", 30, "Engineer");
        system.addPersonInfo("Bob", 25, "Designer");
        system.addPersonInfo("Charlie", 35, "Manager");

        // 写入文件
        try {
            system.writeToFile("people.txt");
            System.out.println("Information written to file successfully.");

            // 清空列表，模拟从文件读取
            system.personInfoList.clear();
            System.out.println("Reading information from file...");
            system.readFromFile("people.txt");

            // 打印读取的信息
            for (PersonInfo person : system.personInfoList) {
                System.out.println(person);
            }
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}