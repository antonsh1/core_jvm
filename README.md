# Задача "Понимание JVM"

```java
public class JvmComprehension {
    public static void main(String[] args) {
        int i = 1;                      // 1
        Object o = new Object();        // 2
        Integer ii = 2;                 // 3
        printAll(o, i, ii);             // 4
        System.out.println("finished"); // 7
    }
    private static void printAll(Object o, int i, Integer ii) {
        Integer uselessVar = 700;                   // 5
        System.out.println(o.toString() + i + ii);  // 6
    }
}
```

<img src="Задача Понимание JVM.jpg" alt= “” width="60%" height="60%">

# Задача "Исследование JVM через VisualVM"

* На картинке указаны все тайм фреймы.  
* Перед выполнением программы произведен ручной запуск GC.  
* При загрузке классов видно увеличение размера Metaspace  
(единственное, не совсем понятна задержка при загрузке классов org.springfraмework, 
увеличение размера произошло на 2 секунды позже выведенного сообщения в консоль, 
как и продолжающий рост участок при загрузке io.netty, после выведенного сообщения.)    
* При первом создании 5млн объектов и последнем, размер кучи был увеличен.


![Рисунок по заданию](./Исследование%20JVM%20через%20VisualVM.jpg)

<img src="Исследование%20JVM%20через%20VisualVM.jpg" alt= “” width="80%" height="80%">
