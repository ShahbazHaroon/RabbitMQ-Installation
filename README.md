# RabbitMQ-Installation
Guide to Install RabbitMQ on Windows

<p><a href="https://www.rabbitmq.com/" target="_blank">RabbitMQ</a> is an open source message broker software that implements the Advanced Message Queuing Protocol (AMQP). The RabbitMQ server is written in the <a href="https://www.erlang.org/" target="_blank">Erlang programming language</a> and client libraries to interface with the broker are available for all major programming languages.</p>

<p>Following tutorial shows how to download and install RabbitMQ on Windows and perform a start/stop of the installed instance.</p>

<h1 id="install-erlang">Install Erlang</h1>

<p><a href="https://en.wikipedia.org/wiki/Erlang_(programming_language)" target="_blank">Erlang</a> is a general-purpose concurrent, garbage-collected programming language and runtime system. It was designed by Ericsson to support distributed, fault-tolerant applications.</p>

<p>It was originally a proprietary language within Ericsson, but was released as open source in 1998. OTP (Open Telecom Platform) is the open source distribution of Erlang.</p>

<p>The first thing to do is to download the OTP binaries. Go the the <a href="http://www.erlang.org/download.html" target="_blank">Erlang download page</a> and click on the Windows binary link for your system (32-bit or 64-bit). At the time of writing the latest stable release was <var>otp_win64_20.2.exe</var>.</p>

<p>Double click to run the downloaded <var>'.exe'</var> file and click <var>Next</var> keeping the default settings on the first installer step.</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/erlang-installer-choose-components.png" alt="erlang installer choose components" />
</figure>

<p>Optionally change the default destination folder and click <var>Next</var> and then <var>Install</var>. In the example below the install location was changed to <var>'C:\tools\erl9.2'</var>. From now on we will refer to this directory as: <var>[erlang_install_dir]</var>.</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/erlang-install-location.png" alt="erlang install location" />
</figure>

<p>If Microsoft Visual C++ is not already setup on your system, a second installer window will pop-up. Click the <var>'I have read and accept the license terms'</var> check-box and click <var>Install</var>.</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/erlang-msvisualc-installer.png" alt="erlang msvisualc installer" />
</figure>

<p>Click <var>Finish</var> when the Microsoft Visual C++ setup is complete and then click <var>Close</var> to finish the OTP installation.</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/erlang-installer-finish.png" alt="erlang installer finish" />
</figure>

<p>In order for Erlang applications to be able to run we need to setup an <var>'ERLANG_HOME'</var> environment variable that will point to the Erlang installation directory.</p>

<p>When using Windows the above parameter can be configured on the Environment Variables panel. Click on the <var>Windows Start</var> button and enter “<kbd>env</kbd>” without quotes as shown below.</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/environment-variables.png" alt="environment variables" />
</figure>

<p>Environment variables can be set at account level or at system level. For this example click on <var>Edit environment variables for your account</var> and following panel should appear.</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/edit-environment-variables.png" alt="edit environment variables" />
</figure>

<p>Click on the <var>New</var> button and enter “<kbd>ERLANG_HOME</kbd>” as variable name and the <var>[erlang_install_dir]</var> as variable value. In this tutorial the installation directory is <var>'C:\tools\erl9.2'</var>. Click OK to to save.</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/environment-variable-erlang-home.png" alt="environment variable erlang home" />
</figure>

<h1 id="install-rabbitmq">Install RabbitMQ</h1>

<p>RabbitMQ can be downloaded from the <a href="https://www.rabbitmq.com/download.html" target="_blank">RabbitMQ download page</a>. There are a number of different download packages available, for this tutorial we will be installing the <a href="https://www.rabbitmq.com/install-windows-manual.html" target="_blank">manual install package</a> on Windows. At the time of writing the latest stable release was <var>'rabbitmq-server-windows-3.7.2.zip'</var>.</p>

<p>Extract the binaries archive downloaded in the previous step. The extracted root directory should contain a number of files and subdirectories as shown below. From now on we will refer to this directory as: <var>[rabbitmq_install_dir]</var>.</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/rabbitmq-install-dir.png" alt="rabbitmq install dir" />
</figure>

<p>In order to start RabbitMQ, open a command prompt by clicking on the Windows Start button and typing “<kbd>cmd</kbd>” followed by pressing <var>ENTER</var>. A new command prompt window should open. Navigate to the <var>[rabbitmq_install_dir]/sbin</var> and enter following command:</p>

<div class="language-plaintext highlighter-rouge"><div class="highlight"><pre class="highlight"><code>rabbitmq-server
</code></pre></div></div>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/rabbitmq-start.png" alt="rabbitmq start" />
</figure>

<p>In order to stop RabbitMQ, open another command prompt at  <var>[rabbitmq_install_dir]/sbin</var> and enter following command:</p>

<div class="language-plaintext highlighter-rouge"><div class="highlight"><pre class="highlight"><code>rabbitmqctl stop
</code></pre></div></div>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/rabbitmq-stop.png" alt="rabbitmq stop" />
</figure>

<h1 id="setup-rabbitmq">Setup RabbitMQ</h1>

<p>The <var>'rabbitmq-management'</var> plugin provides a browser-based UI for management and monitoring of the RabbitMQ server . In order to enable the UI, <strong>make sure RabbitMQ is running</strong> and open a new command prompt at <var>[rabbitmq_install_dir]/sbin</var> in which you enter following:</p>

<div class="language-plaintext highlighter-rouge"><div class="highlight"><pre class="highlight"><code>rabbitmq-plugins enable rabbitmq_management
</code></pre></div></div>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/rabbitmq-enable-management-console.png" alt="rabbitmq enable management console" />
</figure>

<p>Open the RabbitMQ web console in a browser using: <a href="http://localhost:15672" target="_blank">http://localhost:15672</a> and following page should be displayed:</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/rabbitmq-management-console-login.png" alt="rabbitmq management console login" />
</figure>

<p>Enter following default credentials: Username=”<kbd>guest</kbd>” and Password=”<kbd>guest</kbd>” and click on <var>Login</var>. An overview page will be displayed that contains some basic information on the RabbitMQ server.</p>

<figure>
    <img src="https://github.com/ShahbazHaroon/RabbitMQ-Installation/blob/master/img/rabbitmq-management-console.png" alt="rabbitmq management console" />
</figure>

<hr />

<p>This concludes setting up and configuring RabbitMQ. If you found this post helpful or have any questions or remarks, please leave a comment.</p>
