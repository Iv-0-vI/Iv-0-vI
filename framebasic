import javax.swing.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class ActionListenerExample {
    public static void main(String[] args) {
        // 创建 JFrame 窗口
        JFrame frame = new JFrame("Action Listener Example");
        frame.setSize(300, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // 创建按钮
        JButton button = new JButton("Click Me!");

        // 创建 ActionListener
        ActionListener actionListener = new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                System.out.println("Button was clicked!");
            }
        };

        // 为按钮添加事件监听器
        button.addActionListener(actionListener);

        // 将按钮添加到窗口
        frame.getContentPane().add(button);

        // 显示窗口
        frame.setVisible(true);
    }
}