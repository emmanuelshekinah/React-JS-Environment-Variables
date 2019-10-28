---


---

<h1 id="docker---react-js">Docker - React JS</h1>
<h2 id="pre-requisite">Pre-requisite</h2>
<ol>
<li>Window 10</li>
</ol>
<h2 id="step-1-getting-docker">Step 1: Getting Docker</h2>
<ol>
<li><a href="https://hub.docker.com/">Goto DockerHub Website</a></li>
<li>Signup</li>
<li>Verify email account</li>
<li>Login</li>
<li>Download Docker for desktop</li>
</ol>
<h2 id="step-2-installing-docker">Step 2: Installing docker</h2>
<p>Open docker setup to install</p>
<h2 id="configure-docker-in-your-project.">Configure Docker in your project.</h2>
<p>Once docker is installed, then</p>
<ol>
<li>go to project folder you wanna dockerise,</li>
<li>Create file in a main root of your project with “Dockerfile” without extension</li>
<li>Define Environment within docker configuration file</li>
</ol>
<p><strong>Development</strong></p>
<pre><code>FROM node:latest as build
# set working directory
WORKDIR /app
# add /app/node_modules/.bin to $PATH
ENV PATH /app/node_modules/.bin:$PATH
# install and cache app dependencies
COPY package.json /app/package.json
RUN npm install --silent
RUN npm install react-scripts@3.0.1 -g --silent
COPY . /app
RUN npm run build
</code></pre>
<p><strong>Run Command</strong></p>
<pre><code>docker build . -t image_name
</code></pre>
<p>image_name can be any name of your choice</p>
<p><strong>Check Image</strong><br>
We have to check if the docker image is successfully built.</p>
<pre><code>docker images
</code></pre>
<ul>
<li>this will show a list of docker images and the latest will show by its time stamp</li>
</ul>
<p><strong>Run Docker</strong></p>
<pre><code>docker
</code></pre>

