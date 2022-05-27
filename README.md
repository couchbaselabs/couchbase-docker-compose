# How to create a Couchbase Server and Sync Gateway Developer Environment with Docker Compose

### How to clone this repository

`git clone https://github.com/couchbaselabs/couchbase-docker-compose.git`

### Prerequisites: Install [Docker Desktop](https://docs.docker.com/desktop/) for your OS

**macOS**

* [https://docs.docker.com/desktop/mac/install/](https://docs.docker.com/desktop/mac/install/)

**Windows**

* [https://docs.docker.com/desktop/windows/install/](https://docs.docker.com/desktop/windows/install/)

**Linux**

* [https://docs.docker.com/desktop/linux/install/](https://docs.docker.com/desktop/linux/install/)

### How to run and provision the servers

#### Build and start the `./couchbase-server` and `./sync-gateway` Docker build files:

* `docker-compose up --detach`

Expected response:

`[+] Running 1/2`

` ⠿ Container couchbase-server  Started        0.4s`
                                                                                                 
` ⠼ Container sync-gateway      Starting       0.4s`

#### How to stop the running images

* `docker-compose stop`

Expected response:

`[+] Running 2/2`

`⠿ Container couchbase-server  Stopped 10.5s`                                                                                                          

`⠿ Container sync-gateway      Stopped 0.0s`


#### Show the running images with:

* `docker ps`

* `docker container ls`

Expected responses:

`CONTAINER ID   IMAGE                                       COMMAND                  CREATED          STATUS          PORTS                                                                                               NAMES`
`8a9ac3f1b260   couchbase-docker-compose_couchbase-server   "sh -c /opt/couchbas…"   50 minutes ago   Up 50 minutes   0.0.0.0:8091-8096->8091-8096/tcp, 11207/tcp, 11211/tcp, 0.0.0.0:11210->11210/tcp, 18091-18096/tcp   couchbase-server`


#### Inspect the logs:

* `docker logs couchbase-server`

* `docker logs sync-gateway`

#### Verify with CURL on the commandline:

**Couchbase Server**:

* `curl http://localhost:8092`

Expected response:

`... {"couchdb":"Welcome"}`

**Couchbase Sync Gateway**:

* `curl http://localhost:4984`

Expected response:

`...
{"couchdb":"Welcome","vendor":{"name":"Couchbase Sync Gateway","version":"3.0"},"version":"Couchbase Sync Gateway/3.0.0(541;46803d1) EE"}%`

### License

***This is not an official Couchbase product and is a work in progress!***

Feel free to create Git branches and contribute.

**[MIT License](https://opensource.org/licenses/MIT)**

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
