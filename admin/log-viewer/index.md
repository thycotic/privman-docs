[title]: # (Server Logs)
[tags]: # (overview)
[priority]: # (10)
# Server Logs

The Server Logs provide insight into the Privilege Manager Server Logs.

![server logs](images/log-viewer.png "Privilege Manager Server Logs details")

By default the Server Logs are shown for the last 30 minutes and with the Severity and Application set to All. These change be changed via the available drop-down options:

| Drop-downs | Options |
| ----- | ----- |
| Duration | ![duration](images/duration.png "Logs show for selected past time") |
| Severity | ![severity](images/severity.png "Logs show for selected severity level") |
| Application | ![application](images/application.png "Logs show for selected application") |

## Details

Details for a log entry can be viewed by clicking on the row containing the log entry.

![details](images/details.png "Log event details")

## Search by CorrelationID

The Server Logs are searchable via CorrelationID for better troubleshooting support. If you are looking for log details about an error that occurred in the UI, copy the CorrelationID from the error message and enter it in the table grid search field.

* Error providing CorrelationID:

  ![id](images/error.png "Error providing CorrelationID")
* Search Server Logs for CorrelationID:

  ![search](images/id-2.png "Search Server Logs for CorrelationID")
* Details for error based on CorrelationID search:

  ![details](images/details-2.png "Details for error based on CorrelationID search")
