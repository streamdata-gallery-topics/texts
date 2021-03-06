---
swagger: "2.0"
x-collection-name: CallFire
x-complete: 0
info:
  title: Callfire Find texts
  description: Searches for texts sent or received by user. Use "campaignId=0" parameter
    to query for all texts sent through the POST /texts API. See [call states and
    results](https://developers.callfire.com/results-responses-errors.html)
  termsOfService: https://www.callfire.com/legal/terms
  contact:
    name: CallFire
    url: https://www.callfire.com
    email: support@callfire.com
  version: 1.0.0
host: www.callfire.com
basePath: /v2
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /texts:
    get:
      summary: Find texts
      description: Searches for texts sent or received by user. Use "campaignId=0"
        parameter to query for all texts sent through the POST /texts API. See [call
        states and results](https://developers.callfire.com/results-responses-errors.html)
      operationId: findTexts
      x-api-path-slug: texts-get
      parameters:
      - in: query
        name: batchId
        description: An Id of a contact batch, queries for texts which are used in
          the particular contact batch
      - in: query
        name: campaignId
        description: An id of a campaign, queries for texts inside a particular campaign
      - in: query
        name: fields
        description: Limit fields received in response
      - in: query
        name: fromNumber
        description: A phone number in E
      - in: query
        name: id
        description: List of Text ids to search for, if ids specified other query
          params ignored
      - in: query
        name: inbound
        description: Specify true for inbound or false for outbounds
      - in: query
        name: intervalBegin
        description: Start of the find time interval, formatted in unix time milliseconds
      - in: query
        name: intervalEnd
        description: End of the find time interval, formatted in unix time milliseconds
      - in: query
        name: label
        description: A label of a text message
      - in: query
        name: limit
        description: To set the maximum number of records to return in a paged list
          response
      - in: query
        name: offset
        description: Offset to the start of a given page
      - in: query
        name: results
        description: 'Expected text results in comma separated string, available values:
          SENT, RECEIVED, DNT, TOO_BIG, INTERNAL_ERROR, CARRIER_ERROR, CARRIER_TEMP_ERROR,
          UNDIALED'
      - in: query
        name: states
        description: 'Expected text statuses in comma separated string, available
          values: READY, SELECTED, CALLBACK, FINISHED, DISABLED, DNC, DUP, INVALID,
          TIMEOUT, PERIOD_LIMIT'
      - in: query
        name: toNumber
        description: A phone number in E
      responses:
        200:
          description: OK
      tags:
      - Texts
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---