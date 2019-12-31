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
