<h1> IBMCloud-Guide</h1>

Documentation: <br>
<a href="https://cli.cloudfoundry.org/en-US/v6/" target="_blank">https://cli.cloudfoundry.org/en-US/v6/</a><br>

<h2>Access and deploy applciation in cloud foundry using the ibmcloud CLI</h2>

#### Login to IBM Cloud via terminal
<i>ibmcloud login -sso</i>

#### Target cloudFoundery applciation in cloud
<i>ibmcloud target --cf </i>

#### Push given project to IBMCloud production
<i>ibmcloud cf push</i>

#### See deployment log <br>
<i>ibmcloud cf logs <-application server name-> </i>

<h2>Deploying Node.js to Cloud foundry</h2>

<h3>Disable cors</h3>
Add the following to your core js server file. <br>
<pre>
app.use('*', function (_, res, next) {
  res.header("Access-Control-Allow-Origin", "*"); // update to match the domain you will make the request from
  res.setHeader('Access-Control-Allow-Headers', 'X-Requested-With,Content-Length,content-type,Authorization');
  next();
});
</pre>

<h3>Host frontend in backend</h3>
1. Make sure to package frontend to a producktion "dist" folder and place it in the root of the backend <br>

2. Add the following line to point towards the dist folder <br>
<pre>
app.use(express.static('./dist'));
</pre>
