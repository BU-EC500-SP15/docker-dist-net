<h1>Network Aware Container Distribution System</h1>

<h2>Project Goal And Outline</h2>

<p>“Network Aware Container Distribution System” is a project which aims at 
    creating a solution to use idle networking resource of a datacenter to 
    distribute data inside that datacenter. The Goals of the Project are to
    design and implement Network Monitoring, File Transmission Control, 
    and Network Congestion Management.
    This project is mentored by Andrey Turkovsky.</p>

<h2>Usage</h2>
<p>Please note that at this stage of development we can only distribute one file
   at a time</p>
<h3><h3>

<h2>Environment Set Up<h2>
<h3>For Master Node(a fresh copy of Ubuntu):</h3>
<p>  · Modifing config.py:  </p> 
<pre>
    file_path = "/home/your_user_name/Desktop/"     #The absolute path of the file that will be distributed 
    file_name = "test.jpg"                          #The name of the file that will be distributed 
</pre>
<p>  · Setting up Master-end Environment:</p> 
<pre>
    ./master_env_setup.sh
</pre>
<p> · To add slave node:  </p> 
<pre>
    ./master_add_slave.sh 
</pre>
<p> · Enter slave id</p> 
<pre>
    001                                              #the same id as configured on the slave machine
</pre>
<p> · Run master.py </p> 
<pre>
    python master.py
</pre>


<h2>For Worker Node(a fresh copy of Ubuntu):</h2>
<p> · Modify config.py:</p>
<pre> 
    master_ip = "172.16.46.154"                     #Master-end IP address
    slave_id = 'slave_001'                          #Input slave id, must be the same as you will enter in ./master_add_slave.sh
                                                    #Must wrap slave_00x with ''
    download path = "~/Desktop/"                    #The file directory that you want to keep 
</pre>
<p> ·  Setting up Slave-end Environment:</p>
<pre>
    ./slave_env_setup
</pre>
<p> ·  Run slave.py</p>
<pre>
    python slave.py
</pre>

<p>As you finish above step, the file will starting to be distributed, if the network
   condition is idle on worker node, the master will send file to this node, if the
   network is not idle, the master will wait for the worker's network to become idle
   then start to distribute file to worker</p>
