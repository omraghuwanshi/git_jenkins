pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo 'Building...'
      }
    }

    stage('ServiceNow Ticket') {
      steps {
        script {
          echo "Calling ServiceNow API..."
          def response = httpRequest(
            #url: 'https://dev300396.service-now.com/api/now/table/change_request',
            httpMode: 'POST',
            contentType: 'APPLICATION_JSON',
            authentication: 'servicenow-creds',
            requestBody: '''
            {
              "short_description": "Deployed from Jenkins by om raghuwanshi",
              "category": "Software",
              "state": "New"
            }
            '''
          )
          echo "ServiceNow Response: ${response.content}"
        }
      }
    }
  }
}
