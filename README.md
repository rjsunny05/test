![image](https://github.com/user-attachments/assets/e93e9988-17e8-43f8-8601-7acfcd679bfb)




| Author      | Created on  | Version    | Last updated by | Last edited on |
|-------------|-------------|------------|-----------------|----------------|
| Rajeev Ranjan    | 16-04-25    | version 1  | Rajeev Ranjan        |        |


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
 
</head>
<body>

<h2>Table of Contents</h2>
<ul class="toc">
  <li><a href="#structure">Standard Directory Structure</a></li>
  <li><a href="#Detailed Explanation of Each Directory">Detailed Explanation of Each Directory</a></li>
  <li>
    <ul>
      <li><a href="#defaults">1. defaults/main.yml</a></li>
      <li><a href="#files">2. files/</a></li>
      <li><a href="#handlers">3. handlers/main.yml</a></li>
      <li><a href="#meta">4. meta/main.yml</a></li>
      <li><a href="#tasks">5. tasks/main.yml</a></li>
      <li><a href="#templates">6. templates/</a></li>
      <li><a href="#vars">7. vars/main.yml</a></li>
      <li><a href="#tests">8. tests/</a></li>
      <li><a href="#readme">9. README.md</a></li>
    </ul>
  </li>
  <li><a href="#best-practices">Best Practices</a></li>
</ul>

<h1>Ansible Role Directory Structure Explained</h1>

<p>An Ansible role provides a framework for organizing playbooks, variables, files, templates, and tasks in a standardized way. Here's a breakdown of the default directory structure and the purpose of each component:</p>




<h2 id="structure">Standard Ansible Role Directory Structure</h2>
<pre><code>role_name/
roles/
    common/               # this hierarchy represents a "role"
        tasks/            #
            main.yml      #  <-- tasks file can include smaller files if warranted
        handlers/         #
            main.yml      #  <-- handlers file
        templates/        #  <-- files for use with the template resource
            ntp.conf.j2   #  <------- templates end in .j2
        files/            #
            bar.txt       #  <-- files for use with the copy resource
            foo.sh        #  <-- script files for use with the script resource
        vars/             #
            main.yml      #  <-- variables associated with this role
        defaults/         #
            main.yml      #  <-- default lower priority variables for this role
        meta/             #
            main.yml      #  <-- role dependencies
        library/          # roles can also include custom modules
        module_utils/     # roles can also include custom module_utils
        lookup_plugins/   # or other types of plugins, like lookup in this case

    webtier/              # same kind of structure as "common" was above, done for the webtier role
    monitoring/           # ""
    fooapp/               # ""
</code></pre>

<hr>

<h2 id="Detailed Explanation of Each Directory">Detailed Explanation of Each Directory</h2>

<h3 id="defaults">1. <code>defaults/main.yml</code></h3>
<ul>
  <li><strong>Purpose</strong>: Contains default variables for the role (lowest precedence)</li>
  <li><strong>Use Case</strong>: Define default configurations that users can override</li>
</ul>
<pre><code># defaults/main.yml
http_port: 80
service_name: "nginx"
</code></pre>

<h3 id="files">2. <code>files/</code></h3>
<ul>
  <li><strong>Purpose</strong>: Stores static files to be copied to remote hosts</li>
  <li><strong>Use Case</strong>: Configuration files, scripts, or binaries that don't need templating</li>
</ul>
<pre><code># tasks/main.yml
- name: Copy Nginx config
  ansible.builtin.copy:
    src: files/nginx.conf
    dest: /etc/nginx/nginx.conf
</code></pre>

<h3 id="handlers">3. <code>handlers/main.yml</code></h3>
<ul>
  <li><strong>Purpose</strong>: Defines handlers (tasks triggered by <code>notify</code>)</li>
  <li><strong>Use Case</strong>: Restart services after config changes</li>
</ul>
<pre><code># handlers/main.yml
- name: Restart Nginx
  ansible.builtin.service:
    name: nginx
    state: restarted
</code></pre>
<pre><code># tasks/main.yml
- name: Update Nginx config
  template:
    src: templates/nginx.conf.j2
    dest: /etc/nginx/nginx.conf
  notify: Restart Nginx
</code></pre>

<h3 id="meta">4. <code>meta/main.yml</code></h3>
<ul>
  <li><strong>Purpose</strong>: Defines role metadata and dependencies</li>
  <li><strong>Use Case</strong>: Specify role dependencies, supported platforms, and author info</li>
</ul>
<pre><code># meta/main.yml
galaxy_info:
  author: "Your Name"
  description: "Nginx role"
  license: "MIT"
  platforms:
    - name: "Ubuntu"
      versions: ["20.04", "22.04"]
dependencies: []
</code></pre>

<h3 id="tasks">5. <code>tasks/main.yml</code></h3>
<ul>
  <li><strong>Purpose</strong>: Main task file executed when the role runs</li>
  <li><strong>Use Case</strong>: Define the core automation steps</li>
</ul>
<pre><code># tasks/main.yml
- name: Install Nginx
  ansible.builtin.apt:
    name: nginx
    state: present
</code></pre>

<h3 id="templates">6. <code>templates/</code></h3>
<ul>
  <li><strong>Purpose</strong>: Stores Jinja2 templates (dynamic files with variables)</li>
  <li><strong>Use Case</strong>: Config files that need variable substitution</li>
</ul>
<pre><code># templates/nginx.conf.j2
server {
    listen {{ http_port }};
    server_name {{ server_name }};
}
</code></pre>
<pre><code># tasks/main.yml
- name: Configure Nginx
  ansible.builtin.template:
    src: templates/nginx.conf.j2
    dest: /etc/nginx/nginx.conf
</code></pre>

<h3 id="vars">7. <code>vars/main.yml</code></h3>
<ul>
  <li><strong>Purpose</strong>: Higher-priority variables (override <code>defaults/</code>)</li>
  <li><strong>Use Case</strong>: Define role-specific variables that shouldn’t be changed</li>
</ul>
<pre><code># vars/main.yml
nginx_user: www-data
</code></pre>

<h3 id="tests">8. <code>tests/</code></h3>
<ul>
  <li><strong>Purpose</strong>: Contains test playbooks and inventory</li>
  <li><strong>Use Case</strong>: Verify role functionality with Molecule or manual tests</li>
</ul>
<pre><code># tests/test.yml
- hosts: localhost
  roles:
    - role_name
</code></pre>

<h3 id="readme">9. <code>README.md</code></h3>
<ul>
  <li><strong>Purpose</strong>: Documents the role’s purpose, variables, and usage</li>
  <li><strong>Use Case</strong>: Helps users understand how to use the role</li>
</ul>
<pre><code># Nginx Role
Installs and configures Nginx.

## Variables
- `http_port`: Web server port (default: `80`)
</code></pre>

<hr>

<h2 id="best-practices">Best Practices for Ansible Roles</h2>
<ol>
  <li><strong>Keep tasks modular</strong> – Split into separate files (<code>tasks/install.yml</code>, <code>tasks/config.yml</code>).</li>
  <li><strong>Use <code>defaults/</code> for user-customizable variables</strong>.</li>
  <li><strong>Use <code>vars/</code> for internal role variables</strong>.</li>
  <li><strong>Document all variables</strong> in <code>README.md</code>.</li>
  <li><strong>Test roles</strong> using Molecule or <code>tests/</code>.</li>
</ol>

<p>This structure ensures <strong>reusability</strong>, <strong>maintainability</strong>, and <strong>clarity</strong> in Ansible automation. 🚀</p>

</body>
</html>






## <h2 id="Contact Information">Contact Information</h2>
| Name         | Email address          |
|--------------|------------------------|
| Rajeev Ranjan          |     rajeevsunny05@gmail.com |

## <h2 id="References">References</h2>
| Links                                             | Descriptions                                                    |
|---------------------------------------------------|-----------------------------------------------------------------|
| https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html#role-directory-structure | Document format followed from this link                         |


