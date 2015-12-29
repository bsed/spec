从工作开始，经历了几个项目的开发，现在的项目一般都是一个团队共同开发，而每个人都有自己的编码习惯，为了统一格式，项目组在项目开发之前都会制定一系列的规范。俗话说约定优于配置，但是在执行过程中往往发现效果不是很好（主要是指编码规范这一方面）。所以我们不得不采取一些措施来协助我们统一项目开发人员的编码风格。主要包括三个方面：设置`Code Templates`、`Eclipse formatter`、`Checkstyle`，本篇主要介绍如何设置`Code Templates`，具体步骤如下：

打开Window->Preferences->Java->Code Style->Code Templates
![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Fjava_codestyle_code_template.jpg](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Fjava_codestyle_code_template.jpg)

点击"Import"，导入模板codetemplates.xml文件。
codetemplates.xml内容是我们自己预先定义好的，在这里先不详细描述，我们可以看到Eclipse Code Templates界面中间Configure generated code and comments区域包含了两个菜单树：Comment、Code，如下图所示：


![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_codetemplates_xml_comment_code.jpg](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse_codetemplates_xml_comment_code.jpg)
Comments代表注释模板，Code代表代码模板，其中每一个子菜单代表子项的模板。
我们只要点击某一个子项，就会在界面下方的Pattern区域看到该项我们所定义的模板内容和格式，如下图所示：
![http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse__configure_generated_code_and_comments.jpg](http://7xl7jf.com1.z0.glb.clouddn.com/spec%2Fjava%2Feclipse__configure_generated_code_and_comments.jpg)

如上图所示，当我们点击Comments下的Files子菜单时，下面的Pattern会显示Java文件的头部注释。
下面详细列出每一个子项的模板格式：

Comments-->Files（Java文件注释）

```xml
/**
 * @Project Name: ${project_name}
 * @File Name: ${file_name}
 * @Package: ${package_name}
 * @Description: ${todo}(用一句话描述该文件做什么)
 * @date: ${date}${time}
 * @author: wasabeef@gnux.cn
 * Copyright (c) ${year}, wasabeef@gnux.cn All Rights Reserved.
 *
 */
```

Comments-->Types（Java类注释）

```xml
/**
 * @ClassName: ${type_name} <br/>
 * @Description: ${todo}(这里用一句话描述这个类的作用) <br/>
 * @Function: ${todo} ADD FUNCTION. <br/>
 * @Reason: ${todo} ADD REASON(可选). <br/>
 * @date: ${date} ${time} <br/>
 * @author: ${user}
 * @version: ${enclosing_type}${tags}
 * @since: JDK 1.6
 */
```

Comments-->Fields（类字段注释）

```xml
/**
 * @Fields: ${field}:${todo}(用一句话描述这个变量表示什么).
 * @since: JDK 1.6
 */
```

Comments-->Constructors（构造函数注释）

```xml
/**
 * Creates a new instance of ${enclosing_type}.
 * <p>Title:</p>
 * <p>Description:</p>
 * ${tags}
 */
```

Comments-->Methods（Java方法注释）

```xml
/**
 * @Title: ${enclosing_method}:(这里用一句话描述这个方法的作用). <br/>
 * @Description: ${todo}(这里描述这个方法适用条件 – 可选).<br/>
 * @Description: ${todo}(这里描述这个方法的执行流程 – 可选).<br/>
 * @Description: ${todo}(这里描述这个方法的使用方法 – 可选).<br/>
 * @Description: ${todo}(这里描述这个方法的注意事项 – 可选).<br/>
 * @param: ${tags}    设定文件 
 * @return: ${return_type}    返回类型
 * @throws: 
 * @author: ${user}
 * ${tags}
 * @since JDK 1.6
 */
```

Comments-->Overriding methods（重写方法注释）

```xml
/**
 * (非 Javadoc)
 * <p>Title: ${enclosing_method}</p> 
 * <p>Description: ${todo} 简单描述该方法的实现功能（可选）.</p>
 * ${tags} 
 * ${see_to_overridden} 
 */
```

Comments-->Delegate methods（代理方法注释）

```xml
/**
 * ${tags}
 * ${see_to_target}
 */
```

Comments-->Getters（Java Getter方法注释）
```xml
/**
 * ${bare_field_name}.
 *
 * @return  the ${bare_field_name}
 * @since   JDK 1.6
 */
```

Comments-->Setters（Java Setters方法注释）
```xml
/**
 * ${param}.
 *
 * @param   ${param}    the ${bare_field_name} to set
 * @since   JDK 1.6
 */
```

Code-->New Java files（新建java文件代码模板）
```xml
/**
 * Project Name:${project_name}
 * File Name:${file_name}
 * Package Name:${package_name}
 * Date:${date}${time}
 * Copyright (c) ${year}, kelvin@gnux.cn All Rights Reserved.
 *
*/
${filecomment}

${package_declaration}
/**
 * ClassName:${type_name} <br/>
 * Function: ${todo} ADD FUNCTION. <br/>
 * Reason:   ${todo} ADD REASON. <br/>
 * Date:     ${date} ${time} <br/>
 * @author   ${user}
 * @version  
 * @since    JDK 1.6
 * @see      
 */
${typecomment}
${type_declaration}
```

Code-->Method body（方法体模板）

```xml
// ${todo} Auto-generated method stub
${body_statement}
```

Code-->Constructor body（构造函数模板）

```xml
${body_statement}
// ${todo} Auto-generated constructor stub
```

Code-->Getter body（字段Getter方法模板）

```xml
return ${field}; 
```

Code-->Setter body（字段Setter方法模板）

```xml
${field} = ${param};
```

Code-->Catch block body（异常catch代码块模板）
```xml
// ${todo} Auto-generated catch block
${exception_var}.printStackTrace();
```

其中codetemplates.xml内容如下：
```xml
<?xml version="1.0" encoding="UTF-8" standalone="no"?><templates><template autoinsert="false" context="gettercomment_context" deleted="false" description="Comment for getter method" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.gettercomment" name="gettercomment">/**
 * ${bare_field_name}.
 *
 * @return  the ${bare_field_name}
 * @since   JDK 1.6
 */</template><template autoinsert="false" context="settercomment_context" deleted="false" description="Comment for setter method" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.settercomment" name="settercomment">/**
 * ${param}.
 *
 * @param   ${param}    the ${bare_field_name} to set
 * @since   JDK 1.6
 */</template><template autoinsert="false" context="constructorcomment_context" deleted="false" description="Comment for created constructors" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.constructorcomment" name="constructorcomment">/**
 * Creates a new instance of ${enclosing_type}.
 *
 * ${tags}
 */
</template><template autoinsert="false" context="filecomment_context" deleted="false" description="Comment for created Java files" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.filecomment" name="filecomment">/**
 * Project Name:${project_name}
 * File Name:${file_name}
 * Package Name:${package_name}
 * Date:${date}${time}
 * Copyright (c) ${year}, kelvin@gnux.cn All Rights Reserved.
 *
 */</template><template autoinsert="false" context="typecomment_context" deleted="false" description="Comment for created types" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.typecomment" name="typecomment">/**
 * ClassName: ${type_name} &lt;br/&gt;
 * Function: ${todo} ADD FUNCTION. &lt;br/&gt;
 * Reason: ${todo} ADD REASON(可选). &lt;br/&gt;
 * date: ${date} ${time} &lt;br/&gt;
 *
 * @author ${user}
 * @version ${enclosing_type}${tags}
 * @since JDK 1.6
 */</template><template autoinsert="false" context="fieldcomment_context" deleted="false" description="Comment for fields" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.fieldcomment" name="fieldcomment">/**
 * ${field}:${todo}(用一句话描述这个变量表示什么).
 * @since JDK 1.6
 */</template><template autoinsert="false" context="methodcomment_context" deleted="false" description="Comment for non-overriding methods" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.methodcomment" name="methodcomment">/**
 * ${enclosing_method}:(这里用一句话描述这个方法的作用). &lt;br/&gt;
 * ${todo}(这里描述这个方法适用条件 – 可选).&lt;br/&gt;
 * ${todo}(这里描述这个方法的执行流程 – 可选).&lt;br/&gt;
 * ${todo}(这里描述这个方法的使用方法 – 可选).&lt;br/&gt;
 * ${todo}(这里描述这个方法的注意事项 – 可选).&lt;br/&gt;
 *
 * @author ${user}
 * ${tags}
 * @since JDK 1.6
 */</template><template autoinsert="false" context="overridecomment_context" deleted="false" description="Comment for overriding methods" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.overridecomment" name="overridecomment">/**
 * ${todo} 简单描述该方法的实现功能（可选）.
 * ${see_to_overridden}
 */</template><template autoinsert="true" context="delegatecomment_context" deleted="false" description="Comment for delegate methods" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.delegatecomment" name="delegatecomment">/**
 * ${tags}
 * ${see_to_target}
 */</template><template autoinsert="false" context="newtype_context" deleted="false" description="Newly created files" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.newtype" name="newtype">/**
 * Project Name:${project_name}
 * File Name:${file_name}
 * Package Name:${package_name}
 * Date:${date}${time}
 * Copyright (c) ${year}, kelvin@gnux.cn All Rights Reserved.
 *
*/
${filecomment}

${package_declaration}
/**
 * ClassName:${type_name} &lt;br/&gt;
 * Function: ${todo} ADD FUNCTION. &lt;br/&gt;
 * Reason:   ${todo} ADD REASON. &lt;br/&gt;
 * Date:     ${date} ${time} &lt;br/&gt;
 * @author   ${user}
 * @version  
 * @since    JDK 1.6
 * @see      
 */
${typecomment}
${type_declaration}
</template><template autoinsert="true" context="classbody_context" deleted="false" description="Code in new class type bodies" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.classbody" name="classbody">
</template><template autoinsert="true" context="interfacebody_context" deleted="false" description="Code in new interface type bodies" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.interfacebody" name="interfacebody">
</template><template autoinsert="true" context="enumbody_context" deleted="false" description="Code in new enum type bodies" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.enumbody" name="enumbody">
</template><template autoinsert="true" context="annotationbody_context" deleted="false" description="Code in new annotation type bodies" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.annotationbody" name="annotationbody">
</template><template autoinsert="true" context="catchblock_context" deleted="false" description="Code in new catch blocks" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.catchblock" name="catchblock">
// ${todo} Auto-generated catch block
${exception_var}.printStackTrace();
</template><template autoinsert="false" context="methodbody_context" deleted="false" description="Code in created method stubs" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.methodbody" name="methodbody">
// ${todo} Auto-generated method stub
${body_statement}</template><template autoinsert="true" context="constructorbody_context" deleted="false" description="Code in created constructor stubs" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.constructorbody" name="constructorbody">
${body_statement}
// ${todo} Auto-generated constructor stub
</template><template autoinsert="true" context="getterbody_context" deleted="false" description="Code in created getters" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.getterbody" name="getterbody">return ${field};</template><template autoinsert="true" context="setterbody_context" deleted="false" description="Code in created setters" enabled="true" id="org.eclipse.jdt.ui.text.codetemplates.setterbody" name="setterbody">${field} = ${param};</template></templates>
```

设置Code Templates的目的主要是为了统一各种注释的格式以及代码的模板，只要设定好Code Templates之后利用Eclipse就可以方便地生成我们自定义的注释，开发人员也容易接受！

{over:}