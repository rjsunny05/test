| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Rajeev Ranjan    | 15-04-25    | version 1  | Rajeev Ranjan        |        |



<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  
</head>
<body>
  <h1>Maven Commands & Debugging</h1>

  <h2>Table of Contents</h2>
  <ul class="toc">
    <li><a href="#intro">Introduction</a></li>
    <li><a href="#basic">Basic Maven Commands</a>
      <ul class="toc">
        <li><a href="#clean-build">Clean & Build</a></li>
        <li><a href="#dependency">Dependency Management</a></li>
        <li><a href="#project-gen">Project Generation</a></li>
        <li><a href="#running">Running Applications</a></li>
        <li><a href="#site">Site & Reports</a></li>
      </ul>
    </li>
    <li><a href="#debugging">Debugging & Troubleshooting</a>
      <ul class="toc">
        <li><a href="#failures">Debugging Build Failures</a></li>
        <li><a href="#skip-tests">Skipping Tests</a></li>
        <li><a href="#surefire">Debugging Surefire</a></li>
        <li><a href="#plugins">Debugging Maven Plugins</a></li>
        <li><a href="#profiles">Profiles & Properties</a></li>
      </ul>
    </li>
    <li><a href="#issues">Common Issues & Fixes</a></li>
    <li><a href="#Contact Information">Contact Information</a></li>
    <li><a href="#References">References</a></li>
  </ul>

  <h2 id="intro">Introduction</h2>
  <p>Maven is a popular build automation tool used primarily for Java projects. Below are commonly used Maven commands and debugging options, organized into tables for clarity.</p>

  <h2 id="basic">Basic Maven Commands</h2>

  <h3 id="clean-build">Clean & Build</h3>
  <table>
    <tr><th>Command</th><th>Description</th></tr>
    <tr><td><code>mvn clean</code></td><td>Deletes the <code>target</code> directory</td></tr>
    <tr><td><code>mvn compile</code></td><td>Compiles the source code</td></tr>
    <tr><td><code>mvn test</code></td><td>Runs unit tests</td></tr>
    <tr><td><code>mvn package</code></td><td>Packages the compiled code into a JAR/WAR file</td></tr>
    <tr><td><code>mvn install</code></td><td>Installs the built artifact into the local Maven repository</td></tr>
    <tr><td><code>mvn verify</code></td><td>Runs integration tests and checks if the package is valid</td></tr>
    <tr><td><code>mvn deploy</code></td><td>Deploys the artifact to a remote repository</td></tr>
  </table>

  <h3 id="dependency">Dependency Management</h3>
  <table>
    <tr><th>Command</th><th>Description</th></tr>
    <tr><td><code>mvn dependency:tree</code></td><td>Displays the dependency tree</td></tr>
    <tr><td><code>mvn dependency:resolve</code></td><td>Resolves dependencies</td></tr>
    <tr><td><code>mvn dependency:purge-local-repository</code></td><td>Clears local dependencies and re-downloads them</td></tr>
  </table>

  <h3 id="project-gen">Project Generation</h3>
  <table>
    <tr><th>Command</th><th>Description</th></tr>
    <tr><td><code>mvn archetype:generate</code></td><td>Creates a new Maven project from an archetype</td></tr>
  </table>

  <h3 id="running">Running Applications</h3>
  <table>
    <tr><th>Command</th><th>Description</th></tr>
    <tr><td><code>mvn exec:java -Dexec.mainClass="com.example.Main"</code></td><td>Runs a Java main class</td></tr>
    <tr><td><code>mvn spring-boot:run</code></td><td>Runs a Spring Boot application</td></tr>
  </table>

  <h3 id="site">Site & Reports</h3>
  <table>
    <tr><th>Command</th><th>Description</th></tr>
    <tr><td><code>mvn site</code></td><td>Generates a project site</td></tr>
    <tr><td><code>mvn surefire-report:report</code></td><td>Generates test reports</td></tr>
  </table>

  <h2 id="debugging">Debugging & Troubleshooting</h2>

  <h3 id="failures">Debugging Build Failures</h3>
  <table>
    <tr><th>Command</th><th>Description</th></tr>
    <tr><td><code>mvn -X</code> / <code>mvn --debug</code></td><td>Enables debug logging</td></tr>
    <tr><td><code>mvn -e</code></td><td>Shows stack traces on errors</td></tr>
    <tr><td><code>mvn -o</code></td><td>Works offline using only local dependencies</td></tr>
  </table>

  <h3 id="skip-tests">Skipping Tests</h3>
  <table>
    <tr><th>Command</th><th>Description</th></tr>
    <tr><td><code>mvn -DskipTests</code></td><td>Skips test execution (still compiles tests)</td></tr>
    <tr><td><code>mvn -Dmaven.test.skip=true</code></td><td>Skips test compilation and execution</td></tr>
  </table>

  <h3 id="surefire">Debugging Surefire (Test Failures)</h3>
  <table>
    <tr><th>Command</th><th>Description</th></tr>
    <tr><td><code>mvn test -Dtest=MyTestClass</code></td><td>Runs a specific test class</td></tr>
    <tr><td><code>mvn test -Dtest=MyTestClass#testMethod</code></td><td>Runs a specific test method</td></tr>
    <tr><td><code>mvn test -Dmaven.surefire.debug</code></td><td>Debugs tests by suspending execution until a debugger is attached</td></tr>
  </table>

  <h3 id="plugins">Debugging Maven Plugins</h3>
  <table>
    <tr><th>Command</th><th>Description</th></tr>
    <tr><td><code>mvn &lt;plugin-prefix&gt;:&lt;goal&gt; -X</code></td><td>Debugs a specific plugin execution</td></tr>
    <tr><td><code>mvn help:effective-pom</code></td><td>Shows the effective POM after inheritance and interpolation</td></tr>
  </table>

  <h3 id="profiles">Profiles & Properties</h3>
  <table>
    <tr><th>Command</th><th>Description</th></tr>
    <tr><td><code>mvn -PprofileName</code></td><td>Activates a Maven profile</td></tr>
    <tr><td><code>mvn -DpropertyName=value</code></td><td>Sets a system property</td></tr>
  </table>

  <h2 id="issues">Common Issues & Fixes</h2>
  <table>
    <tr><th>Issue</th><th>Fix</th></tr>
    <tr><td>Dependency Conflicts</td><td><code>mvn dependency:tree -Dverbose</code></td></tr>
    <tr><td>Build Hangs</td><td><code>mvn --threads 1</code> to run in single-threaded mode</td></tr>
    <tr><td>Out of Memory</td><td>Set <code>MAVEN_OPTS="-Xmx1024m -XX:MaxPermSize=512m"</code></td></tr>
  </table>

</body>
</html>




## <h2 id="Contact Information">Contact Information</h2>
| Name         | Email address          |
|--------------|------------------------|
| Rajeev Ranjan          |     rajeevsunny05@gmail.com |

## <h2 id="References">References</h2>
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
| https://www.digitalocean.com/community/tutorials/maven-commands-options-cheat-sheet | Document format followed from this link                         |


