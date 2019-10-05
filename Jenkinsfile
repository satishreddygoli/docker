node {
  stage 'Checkout'
  git 'ssh://git@github.com:satishreddygoli/docker.git'
 
  stage 'Docker build'
  app = docker.build("doceree/nginx","-f Dockerfile .")
 
  stage 'Docker push'
  docker.withRegistry('https://432827583079.dkr.ecr.us-east-2.amazonaws.com', 'ecr:us-east-2:AWS_ECR_CRED_ID') {
    app.push("latest")
  }
}
