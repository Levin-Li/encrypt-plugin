
###spring boot 应用类加密插件。

####   1、在根POM文件中添加插件配置。

               <plugin> 
                   <groupId>com.levin.commons.plugins</groupId>
                   <artifactId>encrypt-plugin</artifactId>
                   <version>1.1.2-SNAPSHOT</version>
                   <configuration>
                       <skip>${simple-dao-codegen.skip}</skip>
 
                       <!-- 包含的类，默认包含所有 -->
                       <includeClasses>
                       </includeClasses>
   
                       <!-- 排除的类，默认不排除 -->
                       <excludeClasses>
                           <excludeClass>**.entities.**</excludeClass>
                           <excludeClass>**.req.**</excludeClass>
                           <excludeClass>**.info.**</excludeClass>
                       <!--  <excludeClass>*.*Controller</excludeClass> -->
                       </excludeClasses>
   
                   </configuration>
   
                   <executions>
                       <execution>
                           <id>encrypt-repackage</id>
                           <goals>
                               <goal>encrypt-class</goal>
                           </goals>
                       </execution>
                   </executions> 
                   
               </plugin>
               
               
#### 2、添加密码文件

   在项目路径下添加密码文件[.java_agent/.pwdFile.txt] ，密码文件不建议提交到版本库。      
   
 
#### 3、执行Maven打包任务
   
   mvn package

#### 4、启动程序

   执行 startup.sh 启动程序。
   
           