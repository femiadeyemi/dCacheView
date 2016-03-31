# dCacheView
User Inteface for dCache with Implementation of dCache RESTful API

##Instruction for Integrated Deployment
1. Create a Folder called `dCacheView` inside `skel/share/` and copy the content of this repository into the folder.
2. Add the following into the `webdav.xml` file below the rest api handler
  ```xml
  
  <bean class="org.eclipse.jetty.server.handler.ContextHandler">
    <property name="contextPath" value="/"/>
    <property name="handler">
      <bean class="org.eclipse.jetty.server.handler.ResourceHandler">
        <property name="directoriesListed" value="true"/>
        <property name="resourceBase" value="${dCacheView.content.dir}"/>
      </bean>
    </property>
  </bean>
  
  ```
3. add below to the `webdav.properties` file
  ```INI

  webdav.static-content.dir.default=${dcache.paths.share}/webdav
  dCacheView.content.dir=${dcache.paths.share}/dCacheView
  
  ```
