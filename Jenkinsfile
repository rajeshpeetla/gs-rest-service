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
           sh 'aws ecr --region us-east-2 | docker login -u AWS -p eyJwYXlsb2FkIjoiKzVuT0tYY0hKR1lXR01ybjBpNGRlYm1MbnA5NE9IOXdLRDFiUVFBUGZYaFhUWlJTYzNUR1BTalNyVGRKSnFZKzgzTldOOC9UQWtLcFZ1RnMyeC9MOUExZ2lSc1B0Qm1wQWt3aUoreU9QU3lsUm1QUnNKMSt3UWpGZlVYekoyakVocHU4TkVQV3NKb3N6TW5HQkd6a0dpdTg3MXR1YnUwWVA3YWtrSXpsdmthajllMFBlTElLMTFoSnpEOVVsNnJCYlFBc1RqZWl1dEdjUTFQSjRHWEkyVjJFQXNXMi9YcUxLK0E3Rml3WXk3ZnJYRTFZOE9vSmZZNlVlQ1hyUFRYcmNRa0tGcS9TVHpjZEtldWhDTjA0WEtadnhJUXg2eFhLeG1lWlhjWW0wcWlXaDM3Qk40TVJ2K2srci9CdmkwMTVkUGgxSnkvY0gzMGpzd3Q3UUxNclZUQk4zZ0paZDl6TFNBUTJDbGN2cm44Mk1NeENtQWlMa0l4YU8rdVZRdGkzbm5ReFhhdC9CdktOVTZ3Rk5IQ0VFK3VlVStrYWJhOXlidW00b0ltMERZQmNZQWRMSkpLSHR1a1E0dFhjckhsaXo0citYMVFlYXp4dFgzQUsrYzNYaWt2MmRzblZmcXZxdHNwejNyUXRhOWdkSHp2UmJ4bW9lZXl6QWhhWnQrRVJVNlVVZjJWeEUvTTloK1V0a2Q5dTVpYjdqZ21qaHlwNkFsRnFQY3pEV0dMYlcwVVcydzhFLzBsSVU0UzA1NVl1SS9JV3AzWWZCdlR1MTUwME5mc3BFR3N0NFNqU0FZT25KdDQwUlpTa05TZnlQMHltczRneEFWQmhnWGlldFp4S0d2UHBUSWRxQndaQWkrMXZ3WTlTREEydmVnQ1BPeEd2azZJd3ZHWlorNzN5dHU5NWNpdmUrS0JDOUxzbnRxa0MvR2lpNDFEazRqSkE0Um14K0pBUkhNQTR1aGs0Zy83WGxYYWl1eUdMUStVM3A0d3NGV1ByTjRmcXFwVDg4emlVbVhLVGtSb3V3alBycXRqSGlvZG41TDgzM0RxdlJjeldBYkNTREVaY0t6ZTlGencreHM3cjNKQTgvV2syUDlZWVFKbkNnTjBrU2NEcDN2Wm1aQ1psczRCNG5kWEIzK2lSajZyOG8wSWhPVzVGV3N6ckE3Z0tQR1ZBc3FSNytTZ1NYOW5WSTVoTVRreGhTRDJjUGdWVVZxSnB5emt4aEVKT1RySjZXcDEwMmFxaHdxSjRBbWRBbmVhelpXeFZYYm9sMVpGbEFDSWpnbWRibkZLRXhIU1JLR3pZcldvK0piOHhXcGduQjlMTURvOHBBUno2VzlVN2JQNzRwSWVGNGV2ZFkzaGp2bnJ3dVZadmxycUZqUT09IiwiZGF0YWtleSI6IkFRRUJBSGpCNy9pZ3dNZzROUHdhdXJ4U0lZeDRIZm54dUdjLzQ4YkR3dndEcE5ZV1pnQUFBSDR3ZkFZSktvWklodmNOQVFjR29HOHdiUUlCQURCb0Jna3Foa2lHOXcwQkJ3RXdIZ1lKWUlaSUFXVURCQUV1TUJFRURNUDZxT2MvazU0dVQ2aVhQQUlCRUlBNzJPN2NucnpGOFo1dnlZNGl5OTlQakJRQWljamVzdVhoM20rU0tpOUlmSUlIb0FTVjIydy9iNDA2MDBGbHl0a09SWDR0V0pubHZkTnhpd1U9IiwidmVyc2lvbiI6IjIiLCJ0eXBlIjoiREFUQV9LRVkiLCJleHBpcmF0aW9uIjoxNjU0MTQ2ODYwfQ== 817421948276.dkr.ecr.us-east-2.amazonaws.com/gs-rest-service'
           // sh 'aws ecr --region us-east-2 | docker login -u AWS -p eyJwYXlsb2FkIjoic2N6b2RHNE8vckhjSDQ2Y0tnRmxKWlY2dWVPTm9aZCtRN2I2V1VYSFhBczRBSktrYkRHTkN6Y3lHdWFvUlkrY1JEWjJ0VUFMeEJNQWJNajNhWmk3d1RiNXdiSUVKOUFUUHN1K3Z0NkJ0ZUczbmZiWktwM050NC9CakVvUU0zVVQ2RmZnYndCWTBYNitJWFBUcTZWdmNZQWNSQk9kaDdlQUFyOVZGUzBpWk1CZzRyc3hpNEVqQ3JzWkgyNjVRMmJCYmluRm15b1FHSUc1bnRpejNaYmR6aVptTGZBbWNKSnZ2MkcvSGtZWWxqN3Y1T3hzS1VhVnBhOExWaHNZYXU1VEFJR21DOTBoWUtpVTVVaEJCQTQvS1VXS3pmZjJRd3ZBaG8waU9tazNVa05kazVYYUFMUUxGMm1jUTFpRndRYVFvTEZlZlJLVFRFRTh5L2QxYnBTeUM1Ykpmdi9xb2xSdE1Uc2VNVFc0bDRPampuNkJFYTFtRC83WDlkSWdrV3FFT2o0N25OUnhLZWdtTlo1S29EbXdxNDJLZXozT1hJYy8xQll4bEVEVUVrSkFFSUx5QW05dElhUVB4OUcyRC8xbXRmWk1UNzNPQ3F3YnVDcXI0TjNkWEZ3S0NKOFZtYno3c042c3FpQUc4dEMvMituS2ZRM0J6aGswZnd4QnlLbk53c25oS05WWGlhM1p6V29zc0ViQy9YeHlSbDdsenhrQlh1TmNKL3NiNGcrenBpUGJnc2Y4Zzlkc2V1cTV6VmlrcWxwaHM4UmFoM3FrL3Y2bElYNks4L29LZHZGL0ZrNUl6WTdZcW9IRlFKVzA2bW15TEg2MmdLTEtvUnFQdk13REQyekVYUURNeGJvWDJFdmJDWktGSnZRdWVCVDRHNXBmVWRSZGVWZk1WSTd4cVlRemJNVWZMK0dzTXlmN1RjQjJVR1I0d0RDNmtIaTZza0dEd0FjRjBITXFYS0g1UjFYaE1ZNnJHRjhWd1B0Ry9vYWFXVmtGclltaHkxS0tjVExoWkgvOTFDOUMvNWpoSzlrMGp6MkZ3R1J2Z3FoSHFad2xsekFDdWY1cUFod0kwcHk1aDFpdkRpKzFHMUNtZ2NGeGo2dWJxK2tMWDAwSUpsaGdlbTB0cmpJNTIwUkdwNm9NZERxTExQY3FqSkY3RFNtUlVCMVdiR2JtcVNpcmQzTW5DaG9FTW5hcDNvQXgzaDJIbEpLU2hXMkVKUERyZERlSnB2enliWDJBL3pxRUF4c1FsZkpNcHBWZ2Y2Z1RhUnpvSGlFYUxsTHF4NnltOTROSWhBdGdwekorbVo1L1JxTDI1YUdpTlozTitONldidlE4UkUwYTVsNEdyM0xSbmQrM3RFdWk1a3paVzBOMjNJL0tkQT09IiwiZGF0YWtleSI6IkFRRUJBSGpCNy9pZ3dNZzROUHdhdXJ4U0lZeDRIZm54dUdjLzQ4YkR3dndEcE5ZV1pnQUFBSDR3ZkFZSktvWklodmNOQVFjR29HOHdiUUlCQURCb0Jna3Foa2lHOXcwQkJ3RXdIZ1lKWUlaSUFXVURCQUV1TUJFRURMbXhPTHlTM3B3Q2RkWUdoUUlCRUlBN29UcnJLOGJoVCtVZ1pyYVJxUDBoaVE3WVIvRUxSMktYenEzT3NreENCeVc4OG9lZDlaNmVQTTJ1SXRMU1l0NXZkd0RHVVluMlNCK254d2M9IiwidmVyc2lvbiI6IjIiLCJ0eXBlIjoiREFUQV9LRVkiLCJleHBpcmF0aW9uIjoxNjUyOTEzNDMwfQ== 738942673819.dkr.ecr.us-east-2.amazonaws.com/fleetman-webapp'
           // sh 'aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin 817421948276.dkr.ecr.us-east-2.amazonaws.com'
           sh 'docker image build -t ${REPOSITORY_TAG} .'
           sh 'docker push ${REPOSITORY_TAG}'
         }
      }

      stage('Deploy to Cluster') {
          steps {
           // sh '/var/lib/jenkins/workspace/fleetman-webapp/jenkins-cluster-admin-config'
             sh 'envsubst < ${WORKSPACE}/deploy.yaml | kubectl apply -f -'
          }
      }
   }
}
