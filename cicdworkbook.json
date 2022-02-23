{
  "contentVersion": "1.0.0.0",
  "parameters": {
    "workbookDisplayName": {
      "type": "string",
      "defaultValue": "cicd audit workbook",
      "metadata": {
        "description": "The friendly name for the workbook that is used in the Gallery or Saved List.  This name must be unique within a resource group."
      }
    },
    "workbookType": {
      "type": "string",
      "defaultValue": "sentinel",
      "metadata": {
        "description": "The gallery that the workbook will been shown under. Supported values include workbook, tsg, etc. Usually, this is 'workbook'"
      }
    },
    "workbookSourceId": {
      "type": "string",
      "defaultValue": "/subscriptions/66b6bf2d-0483-4184-a490-db0b846adabb/resourcegroups/sentinel/providers/microsoft.operationalinsights/workspaces/sentinelctm",
      "metadata": {
        "description": "The id of resource instance to which the workbook will be associated"
      }
    },
    "workbookId": {
      "type": "string",
      "defaultValue": "[newGuid()]",
      "metadata": {
        "description": "The unique guid for this workbook instance"
      }
    }
  },
  "variables": {
    "workbookContent": {
      "version": "Notebook/1.0",
      "items": [
        {
          "type": 1,
          "content": {
            "json": "<img src=\"https://allvectorlogo.com/img/2016/06/belgian-railways-logo.png\" alt=\"belgian rail logo\" style=\"width:200px;height:125px ; vertical-align:middle;margin:0px 0px\">"
          },
          "customWidth": "25",
          "name": "text - 9"
        },
        {
          "type": 1,
          "content": {
            "json": "<p><h1 style=\"text-align:center; color:#5FA6C3; \">AUDITING WORKBOOK</h1></p>"
          },
          "customWidth": "50",
          "name": "text - 0"
        },
        {
          "type": 9,
          "content": {
            "version": "KqlParameterItem/1.0",
            "crossComponentResources": [
              "{Workspace}"
            ],
            "parameters": [
              {
                "id": "ccd5adcd-8d59-4cfe-99ec-98075de2e253",
                "version": "KqlParameterItem/1.0",
                "name": "DefaultSubscription_Internal",
                "type": 1,
                "isRequired": true,
                "query": "where type =~ 'microsoft.operationalinsights/workspaces'\r\n| take 1\r\n| project subscriptionId",
                "crossComponentResources": [
                  "value::selected"
                ],
                "isHiddenWhenLocked": true,
                "queryType": 1,
                "resourceType": "microsoft.resourcegraph/resources"
              },
              {
                "id": "1ca69445-60fc-4806-b43d-ac7e6aad630a",
                "version": "KqlParameterItem/1.0",
                "name": "Subscription",
                "type": 6,
                "query": "summarize by subscriptionId\r\n| project value = strcat(\"/subscriptions/\", subscriptionId), label = subscriptionId, selected = iff(subscriptionId =~ '{DefaultSubscription_Internal}', true, false)\r\n",
                "crossComponentResources": [
                  "value::selected"
                ],
                "typeSettings": {
                  "additionalResourceOptions": [],
                  "showDefault": false
                },
                "queryType": 1,
                "resourceType": "microsoft.resourcegraph/resources"
              },
              {
                "id": "e94aafa3-c5d9-4523-89f0-4e87aa754511",
                "version": "KqlParameterItem/1.0",
                "name": "Workspace",
                "type": 5,
                "query": "where type =~ 'microsoft.operationalinsights/workspaces'\n| project id",
                "crossComponentResources": [
                  "{Subscription}"
                ],
                "value": "/subscriptions/66b6bf2d-0483-4184-a490-db0b846adabb/resourceGroups/Sentinel/providers/Microsoft.OperationalInsights/workspaces/SentinelCTM",
                "typeSettings": {
                  "resourceTypeFilter": {
                    "microsoft.operationalinsights/workspaces": true
                  },
                  "additionalResourceOptions": []
                },
                "queryType": 1,
                "resourceType": "microsoft.resourcegraph/resources"
              },
              {
                "id": "c4b69c01-2263-4ada-8d9c-43433b739ff3",
                "version": "KqlParameterItem/1.0",
                "name": "TimeRange",
                "type": 4,
                "typeSettings": {
                  "selectableValues": [
                    {
                      "durationMs": 300000
                    },
                    {
                      "durationMs": 900000
                    },
                    {
                      "durationMs": 1800000
                    },
                    {
                      "durationMs": 3600000
                    },
                    {
                      "durationMs": 14400000
                    },
                    {
                      "durationMs": 43200000
                    },
                    {
                      "durationMs": 86400000
                    },
                    {
                      "durationMs": 172800000
                    },
                    {
                      "durationMs": 259200000
                    },
                    {
                      "durationMs": 604800000
                    },
                    {
                      "durationMs": 1209600000
                    },
                    {
                      "durationMs": 2419200000
                    },
                    {
                      "durationMs": 2592000000
                    },
                    {
                      "durationMs": 5184000000
                    },
                    {
                      "durationMs": 7776000000
                    }
                  ],
                  "allowCustom": false
                },
                "value": {
                  "durationMs": 7776000000
                }
              }
            ],
            "style": "pills",
            "queryType": 0,
            "resourceType": "microsoft.insights/components"
          },
          "name": "parameters - 1"
        },
        {
          "type": 11,
          "content": {
            "version": "LinkItem/1.0",
            "style": "tabs",
            "links": [
              {
                "id": "7bdd6d06-3cfc-46a2-97ec-7d5c5eec9699",
                "cellValue": "selectedTab",
                "linkTarget": "parameter",
                "linkLabel": "Summary",
                "subTarget": "Summary",
                "style": "link"
              },
              {
                "id": "fd4ee7d3-d3e8-4409-95a1-3e27c51a5089",
                "cellValue": "selectedTab",
                "linkTarget": "parameter",
                "linkLabel": "Failed Queries",
                "subTarget": "Failed Queries",
                "style": "link"
              },
              {
                "id": "b60a25a6-a656-4c2f-b8bc-8a82fa5bb044",
                "cellValue": "selectedTab",
                "linkTarget": "parameter",
                "linkLabel": "Query Run Performance",
                "subTarget": "Query Run Performance",
                "style": "link"
              },
              {
                "id": "0e3cb4d4-c253-4b92-8446-f413fbb4c33a",
                "cellValue": "selectedTab",
                "linkTarget": "parameter",
                "linkLabel": "Queries run by user",
                "subTarget": "Queries run by user",
                "style": "link"
              },
              {
                "id": "c49da361-4cc5-4835-818c-5ce32a678561",
                "cellValue": "selectedTab",
                "linkTarget": "parameter",
                "linkLabel": "Query explorer",
                "subTarget": "Query explorer",
                "style": "link"
              },
              {
                "id": "a4e71b31-f676-4a6c-ac3f-cc79692167ed",
                "cellValue": "selectedTab",
                "linkTarget": "parameter",
                "linkLabel": "CRUD Operations",
                "subTarget": "CRUD Operations",
                "style": "link"
              }
            ]
          },
          "name": "links - 19"
        },
        {
          "type": 12,
          "content": {
            "version": "NotebookGroup/1.0",
            "groupType": "editable",
            "items": [
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "LAQueryLogs\r\n| summarize events_count=count() by bin(TimeGenerated, 1d)",
                  "size": 0,
                  "title": "Total queries run on workspace",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "visualization": "linechart"
                },
                "name": "query - 0"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "LAQueryLogs\r\n| summarize events_count=count() by AADEmail\r\n| extend UserPrincipalName = AADEmail, Queries = events_count\r\n| join kind= leftouter (\r\n    SigninLogs)\r\n    on UserPrincipalName\r\n| extend User = UserPrincipalName, NoOfQueries = Queries\r\n| project User, NoOfQueries\r\n| summarize arg_max(NoOfQueries, *) by User\r\n| sort by NoOfQueries desc\r\n| take 20",
                  "size": 0,
                  "title": "Top query users",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "visualization": "tiles",
                  "tileSettings": {
                    "showBorder": false,
                    "titleContent": {
                      "columnMatch": "User",
                      "formatter": 1
                    },
                    "leftContent": {
                      "columnMatch": "NoOfQueries",
                      "formatter": 12,
                      "formatOptions": {
                        "palette": "auto"
                      },
                      "numberFormat": {
                        "unit": 17,
                        "options": {
                          "maximumSignificantDigits": 3,
                          "maximumFractionDigits": 2
                        }
                      }
                    }
                  }
                },
                "name": "query - 1"
              }
            ]
          },
          "conditionalVisibility": {
            "parameterName": "selectedTab",
            "comparison": "isEqualTo",
            "value": "Summary"
          },
          "name": "group - 8"
        },
        {
          "type": 12,
          "content": {
            "version": "NotebookGroup/1.0",
            "groupType": "editable",
            "items": [
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "LAQueryLogs\r\n| where ResponseCode != 200 \r\n| summarize events_count=count() by AADEmail\r\n| sort by events_count desc \r\n| take 10",
                  "size": 0,
                  "title": "Users with the most failed queries",
                  "timeContext": {
                    "durationMs": 1209600000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "visualization": "barchart",
                  "tileSettings": {
                    "showBorder": false,
                    "titleContent": {
                      "columnMatch": "AADEmail",
                      "formatter": 1
                    },
                    "leftContent": {
                      "columnMatch": "events_count",
                      "formatter": 12,
                      "formatOptions": {
                        "palette": "auto"
                      },
                      "numberFormat": {
                        "unit": 17,
                        "options": {
                          "maximumSignificantDigits": 3,
                          "maximumFractionDigits": 2
                        }
                      }
                    }
                  }
                },
                "name": "query - 0"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "LAQueryLogs\r\n| where ResponseCode != 200 \r\n| summarize events_count=count() by ResponseCode\r\n| extend HTTPResponse = ResponseCode, QueryCount = events_count\r\n| project-away ResponseCode, events_count\r\n| sort by QueryCount desc ",
                  "size": 0,
                  "title": "Number of failed queries by error code",
                  "timeContext": {
                    "durationMs": 1209600000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "visualization": "table",
                  "tileSettings": {
                    "showBorder": false
                  }
                },
                "name": "query - 1"
              }
            ]
          },
          "conditionalVisibility": {
            "parameterName": "selectedTab",
            "comparison": "isEqualTo",
            "value": "Failed Queries"
          },
          "name": "group - 9"
        },
        {
          "type": 12,
          "content": {
            "version": "NotebookGroup/1.0",
            "groupType": "editable",
            "items": [
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "LAQueryLogs\r\n|summarize arg_max(StatsCPUTimeMs, *) by AADClientId\r\n| extend User = AADEmail, QueryRunTimeMs = StatsCPUTimeMs\r\n| project User, QueryRunTimeMs, QueryText\r\n| order by QueryRunTimeMs desc ",
                  "size": 0,
                  "title": "Longest running queries",
                  "timeContext": {
                    "durationMs": 1209600000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "visualization": "table"
                },
                "name": "query - 0"
              }
            ]
          },
          "conditionalVisibility": {
            "parameterName": "selectedTab",
            "comparison": "isEqualTo",
            "value": "Query Run Performance"
          },
          "name": "group - 10"
        },
        {
          "type": 12,
          "content": {
            "version": "NotebookGroup/1.0",
            "groupType": "editable",
            "items": [
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "LAQueryLogs\r\n| summarize count () by AADEmail, bin(TimeGenerated, 1d)",
                  "size": 0,
                  "title": "Query runs by user",
                  "timeContext": {
                    "durationMs": 0
                  },
                  "timeContextFromParameter": "TimeRange",
                  "timeBrushParameterName": "TimeBrush",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "visualization": "timechart"
                },
                "name": "query - 0"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "LAQueryLogs\r\n| project TimeGenerated, AADEmail, QueryTimeRangeStart, QueryTimeRangeEnd, QueryText",
                  "size": 0,
                  "timeContext": {
                    "durationMs": 0
                  },
                  "timeContextFromParameter": "TimeBrush",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces"
                },
                "name": "query - 1"
              }
            ]
          },
          "conditionalVisibility": {
            "parameterName": "selectedTab",
            "comparison": "isEqualTo",
            "value": "Query explorer"
          },
          "name": "group - 6"
        },
        {
          "type": 12,
          "content": {
            "version": "NotebookGroup/1.0",
            "groupType": "editable",
            "items": [
              {
                "type": 9,
                "content": {
                  "version": "KqlParameterItem/1.0",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "parameters": [
                    {
                      "id": "76ca20d6-06fd-4aa0-bbf4-8adbdebf7d40",
                      "version": "KqlParameterItem/1.0",
                      "name": "User",
                      "type": 2,
                      "query": "SigninLogs\r\n| distinct UserPrincipalName",
                      "crossComponentResources": [
                        "{Workspace}"
                      ],
                      "value": null,
                      "typeSettings": {
                        "additionalResourceOptions": []
                      },
                      "timeContext": {
                        "durationMs": 1209600000
                      },
                      "timeContextFromParameter": "TimeRange",
                      "queryType": 0,
                      "resourceType": "microsoft.operationalinsights/workspaces"
                    }
                  ],
                  "style": "pills",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces"
                },
                "name": "parameters - 0"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "LAQueryLogs\r\n| where AADEmail contains '{User}'\r\n| summarize events_count=count() by bin(TimeGenerated, 1d) ",
                  "size": 0,
                  "title": "Query runs by user",
                  "timeContext": {
                    "durationMs": 1209600000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "visualization": "linechart"
                },
                "name": "query - 1"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "LAQueryLogs\r\n| where AADEmail contains '{User}'\r\n| project TimeGenerated, AADEmail, QueryTimeRangeStart, QueryTimeRangeEnd, QueryText\r\n",
                  "size": 0,
                  "title": "User query details",
                  "timeContext": {
                    "durationMs": 1209600000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "visualization": "table"
                },
                "name": "query - 2"
              }
            ]
          },
          "conditionalVisibility": {
            "parameterName": "selectedTab",
            "comparison": "isEqualTo",
            "value": "Queries run by user"
          },
          "name": "group - 7"
        },
        {
          "type": 12,
          "content": {
            "version": "NotebookGroup/1.0",
            "groupType": "editable",
            "items": [
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity \r\n| where OperationNameValue contains \"SecurityInsights\" \r\n| where OperationName contains \"Delete\" \r\n| where ActivityStatusValue contains \"Succeeded\" \r\n| project TimeGenerated, Caller, OperationName \r\n| extend User = Caller\r\n| project-away Caller\r\n| summarize events_count=count() by User\r\n| sort by events_count desc  ",
                  "size": 0,
                  "title": "Workspace delete activity",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ]
                },
                "customWidth": "33",
                "name": "query - 0"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity \r\n| where OperationNameValue contains \"SecurityInsights\" \r\n| where OperationName contains \"Create\" \r\n| where ActivityStatusValue contains \"Succeeded\" \r\n| project TimeGenerated, Caller, OperationName \r\n| extend User = Caller\r\n| project-away Caller\r\n| summarize events_count=count() by User\r\n| sort by events_count desc  ",
                  "size": 0,
                  "title": "Workspace create activity",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ]
                },
                "customWidth": "33",
                "name": "query - 1"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity \r\n| where OperationNameValue contains \"SecurityInsights\" \r\n| where OperationName contains \"Update\" \r\n| where ActivityStatusValue contains \"Succeeded\" \r\n| project TimeGenerated, Caller, OperationName \r\n| extend User = Caller\r\n| project-away Caller\r\n| summarize events_count=count() by User\r\n| sort by events_count desc  ",
                  "size": 0,
                  "title": "Workspace update activity",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ]
                },
                "customWidth": "33",
                "name": "query - 2"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity \r\n| where OperationNameValue contains \"SecurityInsights\" \r\n| where ActivityStatusValue contains \"Failed\" \r\n| summarize count() by Caller",
                  "size": 0,
                  "title": "Unauthorized requests",
                  "color": "redBright",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "timeBrushParameterName": "Unauthorized",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "visualization": "barchart"
                },
                "name": "query - 3"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity\r\n| where OperationNameValue startswith \"MICROSOFT.SECURITYINSIGHTS/ALERTRULES\"\r\n| where OperationName contains \"Update alert rule response actions\"\r\n//| where OperationNameValue contains \"update\"\r\n| where Properties contains \"alertRules/\"\r\n| parse  Properties with * \"entity\" entity\r\n| extend parse_properties = split(['entity'], \"/\")\r\n| extend rule_id = tostring(parse_properties[12])\r\n| extend rule_id = tostring(split(rule_id, \",\",0))\r\n| extend rule_id = trim(@\"[^\\w]+\", rule_id)\r\n//| project rule_id, Caller , CallerIpAddress , TimeGenerated, ActivityStatusValue\r\n| join kind= leftouter ( SecurityIncident \r\n| extend id = tostring(RelatedAnalyticRuleIds)\r\n| extend id = trim(@\"[^\\w]+\", ['id']) \r\n| distinct id , Title)\r\non $left.rule_id == $right.['id']\r\n| project TimeGenerated, rule_id,Title,Caller,CallerIpAddress, OperationName , ActivityStatusValue",
                  "size": 0,
                  "title": "Updated alert rule response actions by an user",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "sortBy": []
                },
                "name": "Updated alert rule response actions by an user"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity\r\n| where OperationNameValue startswith \"MICROSOFT.SECURITYINSIGHTS/ALERTRULES\"\r\n| where OperationName contains \"Update alert rules\"\r\n//| where OperationNameValue contains \"update\"\r\n| where Properties contains \"alertRules/\"\r\n| parse  Properties with * \"entity\" entity\r\n| extend parse_properties = split(['entity'], \"/\")\r\n| extend rule_id = tostring(parse_properties[12])\r\n| extend rule_id = tostring(split(rule_id, \",\",0))\r\n| extend rule_id = trim(@\"[^\\w]+\", rule_id)\r\n//| project rule_id, Caller , CallerIpAddress , TimeGenerated, ActivityStatusValue\r\n| join kind= leftouter ( SecurityIncident \r\n| extend id = tostring(RelatedAnalyticRuleIds)\r\n| extend id = trim(@\"[^\\w]+\", ['id']) \r\n| distinct id , Title)\r\non $left.rule_id == $right.['id']\r\n| project TimeGenerated, rule_id,Title,Caller,CallerIpAddress, ActivityStatusValue,OperationName",
                  "size": 0,
                  "title": "Sentinel Analytics Rule Updated",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ]
                },
                "name": "Sentinel Analytics Rule Updated"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity\r\n| where OperationNameValue startswith \"MICROSOFT.SECURITYINSIGHTS/ALERTRULES\"\r\n| where OperationName contains \"Delete alert rules\"\r\n//| where OperationNameValue contains \"update\"\r\n| where Properties contains \"alertRules/\"\r\n| parse  Properties with * \"entity\" entity\r\n| extend parse_properties = split(['entity'], \"/\")\r\n| extend rule_id = tostring(parse_properties[12])\r\n| extend rule_id = tostring(split(rule_id, \",\",0))\r\n| extend rule_id = trim(@\"[^\\w]+\", rule_id)\r\n//| project rule_id, Caller , CallerIpAddress , TimeGenerated, ActivityStatusValue\r\n| join kind= leftouter ( SecurityIncident \r\n| extend id = tostring(RelatedAnalyticRuleIds)\r\n| extend id = trim(@\"[^\\w]+\", ['id']) \r\n| distinct id , Title)\r\non $left.rule_id == $right.['id']\r\n| project TimeGenerated, rule_id, Title, Caller, CallerIpAddress, ActivityStatusValue, OperationName",
                  "size": 0,
                  "title": "Existing Alert Deleted By User",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ]
                },
                "name": "Existing Alert Deleted By User"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity\r\n| where OperationNameValue contains \"Microsoft.Insights/workbooks\"\r\n//| where Properties contains \"alertRules/\"\r\n| parse  Authorization with * \"scope\" scope\r\n| extend parse_Authorization = split(scope, \"/\")\r\n//| project parse_Authorization\r\n| extend workbook_id = tostring(parse_Authorization[8])\r\n//| project workbook_id\r\n| extend workbook_id = tostring(workbook_id)\r\n| extend workbook_id = trim(@\"[^\\w]+\", workbook_id)\r\n| project TimeGenerated, workbook_id , Caller , CallerIpAddress , ActivityStatusValue , OperationName",
                  "size": 0,
                  "title": "New workbook Created or updated By A User",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ],
                  "gridSettings": {
                    "sortBy": [
                      {
                        "itemKey": "TimeGenerated",
                        "sortOrder": 2
                      }
                    ]
                  },
                  "sortBy": [
                    {
                      "itemKey": "TimeGenerated",
                      "sortOrder": 2
                    }
                  ]
                },
                "name": "New workbook Creation By A User"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity\r\n| where OperationNameValue contains \"Microsoft.Insights/workbooks\"\r\n| where OperationName contains \"Delete\"\r\n//| where Properties contains \"alertRules/\"\r\n| parse  Authorization with * \"scope\" scope\r\n| extend parse_Authorization = split(scope, \"/\")\r\n//| project parse_Authorization\r\n| extend workbook_id = tostring(parse_Authorization[8])\r\n//| project workbook_id\r\n| extend workbook_id = tostring(workbook_id)\r\n| extend workbook_id = trim(@\"[^\\w]+\", workbook_id)\r\n| project TimeGenerated, workbook_id , Caller , CallerIpAddress , ActivityStatusValue , OperationName",
                  "size": 0,
                  "title": "Existing Workbook deleted by an user",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ]
                },
                "name": "Existing Workbook deleted by an user"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity \r\n|where OperationNameValue contains \"Microsoft.Logic/workflows/\"\r\n|where OperationName contains \"Set workflow\"\r\n|project TimeGenerated,Caller, ActivityStatusValue, OperationName , ResourceId",
                  "size": 0,
                  "title": "Workflow Set By an User",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ]
                },
                "name": "Workflow Set By an User"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity \r\n|where OperationNameValue contains \"Microsoft.Logic/workflows/write\"\r\n|where ActivityStatusValue contains \"succeeded\"\r\n|project TimeGenerated, ResourceProvider,Caller, ActivityStatusValue , OperationName , ResourceId",
                  "size": 0,
                  "title": "Sentinel Logic App Run Succeeded",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ]
                },
                "name": "Sentinel Logic App Run Succeeded"
              },
              {
                "type": 3,
                "content": {
                  "version": "KqlItem/1.0",
                  "query": "AzureActivity \r\n|where OperationNameValue contains \"Microsoft.Logic/workflows/\"\r\n|where OperationName contains \"Delete workflow\"\r\n|project TimeGenerated, ResourceProvider,Resource,Caller, ActivityStatusValue, OperationName , ResourceId",
                  "size": 0,
                  "title": "Playbook Deleted By User",
                  "timeContext": {
                    "durationMs": 7776000000
                  },
                  "timeContextFromParameter": "TimeRange",
                  "queryType": 0,
                  "resourceType": "microsoft.operationalinsights/workspaces",
                  "crossComponentResources": [
                    "{Workspace}"
                  ]
                },
                "name": "Playbook Deleted By User"
              }
            ]
          },
          "conditionalVisibility": {
            "parameterName": "selectedTab",
            "comparison": "isEqualTo",
            "value": "CRUD Operations"
          },
          "name": "group - 8"
        }
      ],
      "isLocked": false,
      "fallbackResourceIds": [
        "/subscriptions/66b6bf2d-0483-4184-a490-db0b846adabb/resourcegroups/sentinel/providers/microsoft.operationalinsights/workspaces/sentinelctm"
      ],
      "fromTemplateId": "sentinel-UserWorkbook"
    }
  },
  "resources": [
    {
      "name": "[parameters('workbookId')]",
      "type": "microsoft.insights/workbooks",
      "location": "[resourceGroup().location]",
      "apiVersion": "2021-03-08",
      "dependsOn": [],
      "kind": "shared",
      "properties": {
        "displayName": "[parameters('workbookDisplayName')]",
        "serializedData": "[string(variables('workbookContent'))]",
        "version": "1.0",
        "sourceId": "[parameters('workbookSourceId')]",
        "category": "[parameters('workbookType')]"
      }
    }
  ],
  "outputs": {
    "workbookId": {
      "type": "string",
      "value": "[resourceId( 'microsoft.insights/workbooks', parameters('workbookId'))]"
    }
  },
  "$schema": "http://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#"
}
