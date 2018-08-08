# Challenges

```
1. Install Docker Plugin ([link](http://saviomathew.blogspot.com/2018/07/q-chef.html))
2. Enable Docker Remote API on docker host
3. Create docker image for Jenkins slave
4. Configure Jenkins
5. Creating Jenkins job to run on docker
```
]#docker build  -f Dockerfile -t jenkins-slave:v1 .

]#docker tag jenkins-slave:v1 saviovettoor/jenkins-slave:v1

]#docker push saviovettoor/jenkins-slave:v1
