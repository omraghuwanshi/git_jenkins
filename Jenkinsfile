stage('ServiceNow Ticket') {
  steps {
    script {
      try {
        echo "Calling ServiceNow API..."
        def response = httpRequest(
          url: 'https://dev300396.service-now.com/api/now/table/change_request',
          httpMode: 'POST',
          contentType: 'APPLICATION_JSON',
          authentication: 'servicenow-creds',
          requestBody: '''
          {
            "short_description": "Deployed from Jenkins",
            "category": "Software",
            "state": "New"
          }
          '''
        )
        echo "ServiceNow Response: ${response.content}"
      } catch (err) {
        echo "ServiceNow API call failed: ${err.getMessage()}"
      }
    }
  }
}
