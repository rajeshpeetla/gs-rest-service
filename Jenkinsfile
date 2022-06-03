pipeline {
   agent any

   environment {
 
     SERVICE_NAME = "gs-rest-service"
     ECR_URI = "817421948276.dkr.ecr.us-east-2.amazonaws.com/gs-rest-service"
     REPOSITORY_TAG ="${ECR_URI}:${BUILD_ID}"
   }

   stages {
      
      stage('Build') {
         tools {
               maven 'maven'
         }
         steps {
           
             sh "mvn clean package"
            
           
            // sh 'echo No build required for Webapp.'
         }
      }

      stage('Build and Push Image') {
         steps {
           sh 'echo ${WORKSPACE}'
           
           sh 'aws ecr --region us-east-2 | docker login -u AWS -p eyJwYXlsb2FkIjoiNnRJM3VFbUNwTHJjS0VxUkRPWGU2WUZzK3k2T2Y1d2d2aFlCcWNwOGFpNUExcjluY252ZmxEM1RGdUZqZVM1U2VGaGozMk5Ob2FlUm1mck9rMWxPeUFicjBUcVF3ZkhIOVpxRlpwU0h6MVBrekRHWEpmdEp0K3dPUGNTVVh1RU1ocHlQaHZqQ2swWVVLY1hjT0ZHbGhCbFJQdllEQTJUMHVpN08wcUh4aUdjNythQ295SmIzMjJVd3BHRktBWmhjZUhtelU2REphdTFUZ3JYdU9zbHZNOGE3UmJOVmFxaS9HTmh3aHhtZ3hzVW0zU3l1T3FGNjc0Z21vWGJ0aml2cUVRYUp3S3lMa1RiSnhMbVNaWkpTLzdjdEdWM0xMV1NVa0lQZ1VteXUzdEUwV0Z1M0t6WGlzaVVFRjNCb055M3ltQkJ1UUlTZzZCdTlFRHRtTXZ1RVcrVm5wcUFtdHQ0cExIM3Q0UHF0bGI5NTNGTE9oODZrMDRvVnNTc01sbDRNYVlHUFdyaWwzd2Y4a3J4c2t1a0ZubTdOd0g2WUpqS0duR3NlTy9ETk1lNFN5dDcyTDN2ZDhhMy9RQ250eE81OEI4NVFoODhhZkVGV1hBSjlzN2lTWVl4ekE4WjJaT0lidllpSDA0MjdsVFFIczVWdGk5WkZ6ZWFoT21BMUxmeXhjMzgyblBSNVhaV21mMzAvd3k0K0QyNUl0cEFVS0JBZG9zQm00QXJKV3RiNnFHdWpxZDhDekdWMEYwWXNOY3haRzVrQW5lTkpZNVNFMnRaeHNjdFRLa0ZUL0oyOG9sUG42RXF0VFVvMWZ4bmRrelVOenNNWHRwaTgvRFg3a2VjMDJzaDRMRFh4UUlmMDVLVmxlOEJtWi9xeGsrYkE2aEpaVm1RR2pvL2xxN214Y0IwYlNHQlE3TnBPVFYzaVh3L2NuK0tuYU90QTVnWTd4NUFFSXNPYWtuS0t0SVoweUV5b0hYNEEyOTdQQTlrRnpPTEE1MjB6TFJoVndzMnMxYWJ5WUY0Y0lOZXF6NHU2SkFmZkFaQ08rUU9kL0tWeVhNaXo0T2pVN0dBdUJBZU5lZSttTTlveEZwZWFzZGFiT05lT1h6ZWZmWDJtZVE4K05aVkFVdDkwcE1rVWRRRDhzd2RqaDVyekM1UHJzcnZuRUxlNHprSDY4Mm5KUmdaU0FEaU51U0h6MzJaQWszTGkxdWZHR2xHV3JkclppeCtOdEpCVkxNT3dUYStWSjJENW52dUVQK0FFMGE3VWRMaVhqMkMrNmgzYUg3VzNqaW9vNFRnU0JxV0NhMDVaMGVHZ0h4Q0J2Wjh1ZDg2a2VQbVJOUG9LejZRSFBjalErWC9razJJNGFuTmdOTHczV0d4d2daS3RsRXp3Q1BPaXpjUDZxQ0ZjL1E9PSIsImRhdGFrZXkiOiJBUUVCQUhqQjcvaWd3TWc0TlB3YXVyeFNJWXg0SGZueHVHYy80OGJEd3Z3RHBOWVdaZ0FBQUg0d2ZBWUpLb1pJaHZjTkFRY0dvRzh3YlFJQkFEQm9CZ2txaGtpRzl3MEJCd0V3SGdZSllJWklBV1VEQkFFdU1CRUVETThMSFNZSVd0cTVCakZzRGdJQkVJQTdhUE9yeUJzUFBCQW9nRUhWbTFyUitmYm5rZ0Jrb3lXTHRrZnVzeVVzRS9BUmF1Q2xaYWV0RE4yK2FqdGtMcktEaTVRdW1kY1ZLSVJndFhBPSIsInZlcnNpb24iOiIyIiwidHlwZSI6IkRBVEFfS0VZIiwiZXhwaXJhdGlvbiI6MTY1NDI4NTI5OX0= 817421948276.dkr.ecr.us-east-2.amazonaws.com/gs-rest-service'
           // sh 'aws ecr --region us-east-2 | docker login -u AWS -p  $(aws ecr get-login-password --region us-east-2) 817421948276.dkr.ecr.us-east-2.amazonaws.com/gs-rest-service'
           // sh 'aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin 817421948276.dkr.ecr.us-east-2.amazonaws.com'
           sh 'docker image build -t ${REPOSITORY_TAG} .'
           sh 'docker push ${REPOSITORY_TAG}'
         }
      }

      stage('Deploy to Cluster') {
          steps {
             // sh '/var/lib/jenkins/workspace/gs-rest-service/jenkins-cluster-admin-config'
          
             
             sh 'envsubst < ${WORKSPACE}/deploy.yaml | kubectl apply -f - --context terraform-eks-demo'
          }
      }
   }
}
