## ライブラリ作成

bootJarタスクを実行

## 呼び出し方

jarファイルを持ち出した上で、`Main.java`を

```java
import org.example.Example;

public class Main {
    public static void main(String args[]) {
        System.out.println("Hello Main !");
        var e = new Example();
        var s = e.example();
        System.out.println(s);
    }
}
```

のように作成して、

### クラスパスに直接追加

```bash
> ls
Main.class  Main.java  java-library-study-1.0-SNAPSHOT.jar
> javac -cp java-library-study-1.0-SNAPSHOT.jar Main.java
> java -cp java-library-study-1.0-SNAPSHOT.jar:. Main
Hello Main !
this is from example
```

のように実行できる。

### Gradle

Jarファイルをコピーした上で、

```groovy
implementation files('libs/java-library-study-1.0-SNAPSHOT.jar')
```

を`build.gradle`に追加し、実行する。
