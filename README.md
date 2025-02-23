<h1>S2CMS (Sig2Labs Content Manager)</h1>
<p>Content Manager for Sig2 Labs Implementation of AutoWIKI content manager</p>

<p>This is forked from <a href="https://github.com/kishorpapnai/AutoWIKI_Content_Manager">https://github.com/kishorpapnai/AutoWIKI_Content_Manager</a></p>

<p>This customization will enable individual content publishers to target only members of the organization.</p>

<h2>How to deploy to google app engine</h2>
<ul>
  <li>Login to <a href="https://console.cloud.google.com">https://console.cloud.google.com</a></li>
  <li>Select the project: S2CMS</li>
  <li>Edit the db/connection.js, comment the local connection code and uncomment the GCLOUD connection code (check the comments to find local vs gcloud connection code)</li>
  <li>Save the file</li>
  <li>Deploy the code to live instance: <code>gcloud app deploy</code></li>
  <li>Prompt will appear for confirmation, press "Y" to continue</li>
  <li>Wait till you see the process is completed.</li>
</ul>

<h2>If any file is updated under [root]/client folder, it requires a rebuild</h2>
<p>Here are the steps to rebuild, on your local system, take the latest code from GitHub:</p>
<ul>
  <li>Update the files which you want to update</li>
  <li>From CLI, go to [root]/client</li>
  <li>Run: <code>npm run build</code></li>
  <li>From CLI, go to [root] folder</li>
  <li>Add, Commit the changes and push to remote</li>
  <li>Login to <a href="https://console.cloud.google.com">https://console.cloud.google.com</a></li>
  <li>Select the project: S2CMS</li>
  <li>Pull the changes from git remote: <code>git pull origin server_and_client</code></li>
  <li>Edit the db/connection.js, comment the local connection code and uncomment the GCLOUD connection code (check the comments to find local vs gcloud connection code)</li>
  <li>Save the file</li>
  <li>Deploy the code to live instance: <code>gcloud app deploy</code></li>
  <li>Prompt will appear for confirmation, press "Y" to continue</li>
  <li>Wait till you see the process is completed.</li>
</ul>

<h2>How to deploy to Cpanel Server</h2>
<ul>
  <li>SSH as root to your WHM/Cpanel server.</li>
</ul>

<h2>Restarting Your Express.js App on WHM/Cpanel server (CentOS)</h2>
<p>This guide explains how to find the process ID (PID) of a running Node.js Express application on CentOS and how to restart it. These instructions are meant for cases when the app has been started with <code>nohup node index.js &</code>.</p>

<h3>1. Finding the Process ID (PID)</h3>
<p>Open the command line interface on your CentOS machine (or SSH into it) and type the following command to list all running Node.js processes:</p>

<pre>
<code>ps aux | grep node</code>
</pre>

<p>This will
 list all Node.js processes currently running on your machine. The PID is the number usually listed in the second column. Look for the PID that corresponds to your Express app.</p>

<h3>2. Killing the Process</h3>
<p>Once you have the PID, use the <code>kill</code> command to stop the process:</p>

<pre>
<code>kill -9 YOUR_PID</code>
</pre>

<p>Replace <code>YOUR_PID</code> with the actual PID you found in the previous step. The <code>-9</code> option sends a <code>SIGKILL</code> signal, which will immediately stop the process.</p>

<p><b>Note:</b> Ensure you are not interrupting any critical tasks by killing this process. If possible, perform these actions during a maintenance window or when the app is not actively being used.</p>

<h3>3. Restarting the Express App</h3>
<p>After killing the process, you can now restart your Express app by rerunning the original command you used to start it:</p>

<pre>
<code>nohup node index.js &</code>
</pre>

<p>This command will start your application and allow it to continue running even after you close the terminal.</p>


