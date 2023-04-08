common config for checkstyle & pmd ruleset config
usage for example

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-pmd-plugin</artifactId>
    <configuration>
        <includeTests>true</includeTests>
        <rulesets>build-resources/pmd-rulesets.xml</rulesets>
        <failOnViolation>false</failOnViolation>
        <printFailingErrors>true</printFailingErrors>
        <format>net.sourceforge.pmd.renderers.SummaryHTMLRenderer</format>
    </configuration>
    <executions>
        <execution>
            <id>pmd-check-verify</id>
            <phase>compile</phase>
            <goals>
                <goal>check</goal>
            </goals>
            <configuration>
                <failOnViolation>false</failOnViolation>
            </configuration>
        </execution>
                    
        <execution>
            <id>pmd-pmd-site</id>
            <phase>site</phase>
            <goals>
                <goal>pmd</goal>
            </goals>
        </execution>
    </executions>
    <!-- add dependency for plugin -->
    <dependencies>
        <dependency>
            <groupId>io.github.devsong</groupId>
            <artifactId>build-tools</artifactId>
            <version>${build-tools.version}</version>
        </dependency>
    </dependencies>
</plugin>
```

for checkstyle plugin

```xml
<plugin>
    <groupId>org.apache.maven.plugins</groupId>
    <artifactId>maven-checkstyle-plugin</artifactId>
    <configuration>
        <consoleOutput>true</consoleOutput>
        <configLocation>build-resources/checkstyle.xml</configLocation>
    </configuration>
    <executions>
        <execution>
            <id>checkstyle</id>
            <phase>validate</phase>
            <goals>
                <goal>check</goal>
            </goals>
            <configuration>
                <failOnViolation>false</failOnViolation>
            </configuration>
        </execution>
    </executions>
    <!-- add dependency for plugin -->
    <dependencies>
        <dependency>
            <groupId>io.github.devsong</groupId>
            <artifactId>build-tools</artifactId>
            <version>${build-tools.version}</version>
        </dependency>
    </dependencies>
</plugin>
```

replace ```build-tools.version``` for specify version,for example current version is ```1.0.0```