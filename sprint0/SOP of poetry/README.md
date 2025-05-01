<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
</head>
<body>

  <h1>Standard Operating Procedure (SOP) for Poetry</h1>
  <p>Covering project setup, dependency management, virtual environments, and command execution:</p>

  <h2>Table of Contents</h2>
  <ul>
    <li><a href="#introduction">Introduction</a></li>
    <li><a href="#installing-poetry">Installing Poetry</a></li>
    <li><a href="#creating-project">Creating a New Project</a></li>
    <li><a href="#managing-dependencies">Managing Dependencies</a></li>
    <li><a href="#virtualenv-management">Virtual Environment Management</a></li>
    <li><a href="#running-commands">Running Commands in Context</a></li>
    <li><a href="#building-publishing">Building & Publishing</a></li>
    <li><a href="#configuration">Configuration (Optional)</a></li>
    <li><a href="#best-practices">Best Practices</a></li>
    <li><a href="#troubleshooting">Troubleshooting</a></li>
    <li><a href="#contact-info">Contact Information</a></li>
    <li><a href="#references">References</a></li>
  </ul>

  <hr>

  <h2 id="introduction">1. Introduction</h2>
  <p>Poetry is a modern dependency management and packaging tool for Python...</p>
  <p><strong>Various reasons for using Poetry:</strong></p>
  <ul>
    <li><strong>Simplified Dependency Management</strong> – Handles install, update, and lock operations efficiently.</li>
    <li><strong>Better Dependency Resolution</strong> – Avoids conflicts using a modern resolver.</li>
    <li><strong>Virtualenv Automation</strong> – Automatically creates and manages virtual environments.</li>
    <li><strong>Project Packaging & Publishing</strong> – Easily build and publish packages to PyPI.</li>
    <li><strong>Single Configuration File</strong> – Uses pyproject.toml instead of setup.py.</li>
  </ul>

  <h2 id="installing-poetry">2. Installing Poetry</h2>
  <ul>
    <li><strong>Official install (Unix/macOS)</strong><br><pre><code>curl -sSL https://install.python-poetry.org | python3 -</code></pre></li>
    <li><strong>Windows (PowerShell)</strong><br><pre><code>(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -</code></pre></li>
    <li><strong>Verify installation</strong><br><pre><code>poetry --version</code></pre></li>
  </ul>

  <h2 id="creating-project">3. Creating a New Project</h2>
  <ul>
    <li><strong>Create a new project (interactive)</strong><br><pre><code>poetry new poetry-demo</code></pre></li>
    <li><strong>Create with a specific Python version</strong><br><pre><code>poetry env use python3.9</code></pre></li>
    <li><strong>Initialize Poetry in an existing project</strong><br><pre><code>cd existing-project</code><br><code>poetry init</code></pre></li>
  </ul>

  <h2 id="managing-dependencies">4. Managing Dependencies</h2>
  <ul>
    <li><strong>Add a dependency</strong><br><pre><code>poetry add &lt;package&gt;</code></pre></li>
    <li><strong>Add development dependency</strong><br><pre><code>poetry add --group dev &lt;package&gt;</code></pre></li>
    <li><strong>Remove a dependency</strong><br><pre><code>poetry remove &lt;package&gt;</code></pre></li>
    <li><strong>Update dependencies</strong><br><pre><code>poetry update</code><br><code>poetry update &lt;package&gt;</code></pre></li>
    <li><strong>List installed packages</strong><br><pre><code>poetry show --tree</code></pre></li>
  </ul>

  <h2 id="virtualenv-management">5. Virtual Environment Management</h2>
  <ul>
    <li><strong>Create/use a virtualenv</strong><br><pre><code>poetry install</code></pre></li>
    <li><strong>Activate the virtualenv</strong><br><pre><code>poetry shell</code></pre></li>
    <li><strong>Deactivate</strong><br><pre><code>exit</code></pre></li>
    <li><strong>List virtualenvs</strong><br><pre><code>poetry env list</code></pre></li>
    <li><strong>Remove a virtualenv</strong><br><pre><code>poetry env remove &lt;python-version|name&gt;</code></pre></li>
  </ul>

  <h2 id="running-commands">6. Running Commands in Context</h2>
  <ul>
    <li><strong>Run a script</strong><br><pre><code>poetry run python script.py</code></pre></li>
    <li><strong>Execute one-off commands</strong><br><pre><code>poetry run pytest</code></pre></li>
    <li><strong>Run with environment variables</strong><br><pre><code>poetry run env VAR=value python script.py</code></pre></li>
  </ul>

  <h2 id="building-publishing">7. Building & Publishing</h2>
  <ul>
    <li><strong>Build the project</strong><br><pre><code>poetry build</code></pre></li>
    <li><strong>Publish to PyPI</strong><br><pre><code>poetry publish</code></pre></li>
  </ul>

  <h2 id="configuration">8. Configuration (Optional)</h2>
  <ul>
    <li><strong>Disable virtualenv creation</strong><br><pre><code>poetry config virtualenvs.create false</code></pre></li>
    <li><strong>Change virtualenvs path</strong><br><pre><code>poetry config virtualenvs.path /path/to/venvs</code></pre></li>
  </ul>

  <h2 id="best-practices">9. Best Practices</h2>
  <ul>
    <li><strong>pyproject.toml</strong>: Edit manually for complex configurations.</li>
    <li><strong>Lockfile</strong>: Commit <pre><code>poetry.lock</code></pre> to ensure reproducible builds.</li>
    <li><strong>CI/CD</strong>: Use <pre><code>poetry install --no-dev</code></pre> in production.</li>
  </ul>

  <h2 id="troubleshooting">10. Troubleshooting</h2>
  <ul>
    <li><strong>"Project not initialized"</strong>: Run <pre><code>poetry init</code></pre>.</li>
    <li><strong>Dependency conflicts</strong>: Use <pre><code>poetry update</code></pre> or edit <pre><code>pyproject.toml</code></pre>.</li>
    <li><strong>"SSL certificate errors"</strong>: Set cert path using <pre><code>poetry config certificates</code></pre>.</li>
    <li><strong>"Virtualenv not detected"</strong>: Use <pre><code>poetry env use python3.x</code></pre>.</li>
  </ul>

  <h2 id="contact-info">11. Contact Information</h2>
  <p>(You can add contact details here.)</p>

  <h2 id="references">12. References</h2>
  <p>(List useful documentation links or references here.)</p>

</body>
</html>
