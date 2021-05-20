# Endpoints

## training-service-sapi
https://github.com/Caliber-Mulesoft/training-service-sapi

- /training
  Get batchIds - Gets all batchIDs. Must be filtered by trainer email.
  
  example query parameter (required): mock1022.employee870e1a69-f385-4cdb-9c59-986de917eca4@mock.com

  example output (JSON):
    ```
    [
      {
        "batchId": "TR-1028"
      },
      {
        "batchId": "TR-1004"
      },
      {
        "batchId": "TR-1032"
      },
      {
        "batchId": "TR-1003"
      }
    ]
```
- /{trainerEmail}
  Get Trainer Info - Gets trainer email, first name, and last name by email.

  example query parameter (required): mock1022.employee870e1a69-f385-4cdb-9c59-986de917eca4@mock.com

  example output (JSON):
  ```
  {
    "email": "mock1022.employee870e1a69-f385-4cdb-9c59-986de917eca4@mock.com",
    "firstName": "Mock 1022",
    "lastName": "Employee 1022"
  }
```
- /batch
  Get Batches (Training Version) - Gets all batches in the training format.
  Must be filtered by batch ID for a specific batch.
  For more info, look at the batchTrainingDataType.raml in the DataTypes folder. 

  example query parameter (required): TR-1028

Example response:
```
    [
      {
        "id": 16,
        "batchId": "TR-1028",
        "name": "Mock Batch 16",
        "startDate": "2020-04-01",
        "endDate": "2020-06-10",
        "skill": "Java React",
        "location": "Reston",
        "type": "Corporate",
        "goodGrade": 70,
        "passingGrade": 80,
        "employeeAssignments": {
          "role": "ROLE_LEAD_TRAINER",
          "employee": {
            "email": "mock1022.employee870e1a69-f385-4cdb-9c59-986de917eca4@mock.com",
            "firstName": "Mock 1022",
            "lastName": "Employee 1022"
          },
          "deletedAt": null
        }
      },
      {
        "associateAssignments": [
          {
            "trainingStatus": "Training",
            "associate": {
              "email": "mock0.associate59e1088a-6e5d-4cb7-9d36-9463a2beb2bc@mock.com",
              "salesforceId": "SF-1250",
              "firstName": "Mock 0",
              "lastName": "Associate 0",
              "flag": null
            },
            "startDate": "2020-06-10",
            "endDate": "2020-04-01",
            "active": true
          },
          {
            "trainingStatus": "Training",
            "associate": {
              "email": "mock10.associate6d293e73-1aec-48a5-a0ed-ed8829c9e7f3@mock.com",
              "salesforceId": "SF-1260",
              "firstName": "Mock 10",
              "lastName": "Associate 10",
              "flag": null
            },
            "startDate": "2020-06-10",
            "endDate": "2020-04-01",
            "active": true
          }
        ],
        "currentWeek": 11
      }
    ]
```
-/current
  Get Current Batches - Gets all current batches from Caliber.

Example response:
```
    [
      {
        "id": 16,
        "batchId": "TR-1028",
        "name": "Mock Batch 16",
        "startDate": "2020-04-01",
        "endDate": "2020-06-10",
        "skill": "Java React",
        "location": "Reston",
        "type": "Corporate",
        "goodGrade": 70,
        "passingGrade": 80,
        "employeeAssignments": {
          "role": "ROLE_LEAD_TRAINER",
          "employee": {
            "email": "mock1022.employee870e1a69-f385-4cdb-9c59-986de917eca4@mock.com",
            "firstName": "Mock 1022",
            "lastName": "Employee 1022"
          },
          "deletedAt": null
        }
      },
      {
        "associateAssignments": [
          {
            "trainingStatus": "Training",
            "associate": {
              "email": "mock0.associate59e1088a-6e5d-4cb7-9d36-9463a2beb2bc@mock.com",
              "salesforceId": "SF-1250",
              "firstName": "Mock 0",
              "lastName": "Associate 0",
              "flag": null
            },
            "startDate": "2020-06-10",
            "endDate": "2020-04-01",
            "active": true
          },
          {
            "trainingStatus": "Training",
            "associate": {
              "email": "mock10.associate6d293e73-1aec-48a5-a0ed-ed8829c9e7f3@mock.com",
              "salesforceId": "SF-1260",
              "firstName": "Mock 10",
              "lastName": "Associate 10",
              "flag": null
            },
            "startDate": "2020-06-10",
            "endDate": "2020-04-01",
            "active": true
          }
        ],
        "currentWeek": 11
      }
    ]
```
- /trainers
  Get All Trainers - Gets all trainers.

Example response:
```
{
  "firstName": "Mock 1027",
  "lastName": "Employee 1027",
  "email": "mock1027.employee74df14df-5842-4811-a57c-be9836537a40@mock.com",
    "trainingBatches": [
      {
        "role": "ROLE_LEAD_TRAINER",
        "employee": {
          "email": "mock1027.employee74df14df-5842-4811-a57c-be9836537a40@mock.com",
          "firstName": "Mock 1027",
          "lastname": "Employee 1027"
      },
      "deletedAt": null
    },
    {
      "role": "ROLE_LEAD_TRAINER",
      "employee": {
        "email": "mock1027.employee74df14df-5842-4811-a57c-be9836537a40@mock.com",
        "firstName": "Mock 1027",
        "lastname": "Employee 1027"
      },
      "deletedAt": null
    }
  ],
  "tier": "ROLE_LEAD_TRAINER"
}
```

- /batches
  Get Batches (Qc Version) - Gets all batches in the QC version.
  For more info, look at the batchQCDataType.raml in the DataTypes folder.

example query parameter (required): TR-1028

Example response:
```
[
  {
    "BatchId": "TR-1201",
    "StartDate": "2021-02-22",
    "EndDate": "2021-05-15"
  },
  {
    "BatchId": "TR-1201",
    "StartDate": "2021-01-01",
    "EndDate": "2021-03-15"
  }
]
```

## evaluation-service-sapi
https://github.com/Caliber-Mulesoft/evaluation-service-sapi

- GET all assessments: /assessments

Example Response:
```
[
  {
    "assessmentId": 63,
    "rawScore": 100,
    "assessmentTitle": "Mock Assessment 1-0",
    "assessmentType": "Presentation",
    "weekNumber": 1,
    "batchId": "TR-1028",
    "assessmentCategory": 5,
    "assignmentDate": "01-01-2020"
  },
  {
    "assessmentId": 64,
    "rawScore": 100,
    "assessmentTitle": "Mock Assessment 1-1",
    "assessmentType": "Presentation",
    "weekNumber": 1,
    "batchId": "TR-1028",
    "assessmentCategory": 39,
    "assignmentDate": "02-02-2020"
  }
]
```
- GET assessments by ID: /assessments/{ID}

Example Response:
```
[
  {
    "assessmentId": 63,
    "rawScore": 100,
    "assessmentTitle": "Mock Assessment 1-0",
    "assessmentType": "Presentation",
    "weekNumber": 1,
    "batchId": "TR-1028",
    "assessmentCategory": 5,
    "assignmentDate": "01-01-2020"
  }
]
```
- GET all grades: /grades

Example Response:
```
[
  {
    "dateRecieved": "2021-04-16",
    "gradeId": 1,
    "score": 9.104028,
    "traineeId": "SF-2128",
    "assessmentId": 1
  },
  {
    "dateRecieved": "2021-01-06",
    "gradeId": 24660,
    "score": 83.40503,
    "traineeId": "SF-1819",
    "assessmentId": 1355
  }
]
```
- GET grades by ID: /grades/{ID}

Example Output:
```
[
  {
    "dateRecieved": "2021-04-16",
    "gradeId": 1,
    "score": 9.104028,
    "traineeId": "SF-2128",
    "assessmentId": 1
  }
]
```
- GET an average of grades dependent on the week, assessment or batch: /average

Example Output:
```
76.988
```

## category-service-sapi
https://github.com/Caliber-Mulesoft/category-service-sapi

-GET All Categories: Retrieves a list of assessment category objects. /category

Example response:
 ```
 [
  {
    "active": true,
    "categoryId": 90,
    "skillCategory": "Unix"
  },
  {
    "active": false,
    "categoryId": 8,
    "skillCategory": "Necromancy"
  }
]
 ```

- GET category by id: Retrieves assessment category object based on its unique ID. /category/{id}
URI Parameter: 'id' Required

Example response:
```
[
  {
    "active": true,
    "categoryId": 90,
    "skillCategory": "Unix"
  }
]
```

## audit-service-sapi
https://github.com/Caliber-Mulesoft/audit-service-sapi

- Get all notes:  /notes
- Get all notes by batch ID:  /notes/{batchId}
- Get all notes by batch ID and week number:  /notes/{batchId}/{week}

Example response:
 ```
  [
  {
    "AssociateId": null,
    "BatchId": "TR-1201",
    "Content": "This is a Qc batch note on week 1",
    "CreatedOn": null,
    "EmployeeId": "QC-User",
    "LastUpdated": null,
    "NoteId": 982,
    "TechnicalStatus": "Poor",
    "Type": "QC_BATCH",
    "Week": 1
  }
]
 ```

- Get all batches information: /batches
 
Example response:
 ```
 [
  {
    "BatchId": "TR-1201",
    "StartDate": "2021-02-22",
    "EndDate": "2021-05-15"
  },
  {
    "BatchId": "TR-1201",
    "StartDate": "2021-01-01",
    "EndDate": "2021-03-15"
  }
]
 
 ```

## training-reports-papi
https://github.com/Caliber-Mulesoft/training-reports-papi

- /report/{trainerEmail}
  Get Report by Email - Gets a comprehensive report concerning trainer/batch information from a given trainer email address.

  example URI parameter (required): mock1022.employee870e1a69-f385-4cdb-9c59-986de917eca4@mock.com

  In total, the return 
  data should contain:

  A top-level JSON object containing:

    A) An employee object containing:
    the trainer's email, first name, and last name.

    B) An array containing:

      B.1) A number of Batch objects each containing:
      A unique ID, batch ID, batch name, batch start date, batch end date, 
      batch skill, batch location, batch type, and an array containing:

        B.1.1) A number of QC Notes objects each containing:
        A QC note ID, batch ID, associate ID (of the Trainee who the note is written about),
        the employee ID of the trainer, note type, technical Status of the QC, 
        the date the note was created on, the date the note was last updated on,
        and an array of strings containing:
                         
          B.1.1.1) Skills written as strings.

    C) An array containing:
      C.1) A number of assessment objects each containing:
      The unique ID, assessment score, assessment title,
      assessment type, assessment week, batch ID,
      assessment category, skill category, assignment date,
      and the average score.

    Becuase of the size of output, the JSON will not be listed here.
    For an in-depth JSON example of the data returned, see the example.json document included.

- /report/utilization
  Get trainer utilization - Gets the percentage of trainers currently training a batch.

Example response:
```
{
  "message": "Trainer utilization: 59%"
}
```

## assessment-aggregations-papi
https://github.com/Caliber-Mulesoft/assessment-aggregations-papi

```
[
  {
    "category": "SOAP",
    "aggregatedScore": 76.54
  },
  {
    "category": "REST",
    "aggregatedScore": 87.65
  }
]
```
- Get the average of assessments by type: /type/average

Example response:
```
[
  {
    "assessmentType": "Written Evaluation",
    "aggregatedScore": 89.65
  },
  {
    "assessmentType": "Oral Exam",
    "aggregatedScore": 76.25
  }
]
```

## qc-aggregations-papi
https://github.com/Caliber-Mulesoft/qc-aggregations-papi

- Get percentages: /percentages/{period} (period can be week, year, all, or year number"2020")

This returns the performance of all batches for a specific period:

week: returns the current week percentages
year: returns the last 52 weeks percentages
all: returns all time percentages

Example response:
```
{
  "PoorPer": "29.63",
  "AveragePer": "22.22",
  "GoodPer": "48.15",
  "SuperstarPer": ".00"
}
```
- Get comparison: /compare/{period} (period can be week, year, or all)

This returns the differnece in performance of all batches between a specific period and the current week:

week: returns the differnece in performance between last week and the current week
year: returns the differnece in performance between last 52 weeks and the current week
all: returns the differnece in performance between all time and the current week

Example response:
```
{
{
  "PoorPercentageChange": "-29.63",
  "AveragePercentageChange": "22.22",
  "GoodPercentageChange": "48.15",
  "SuperstarPercentageChange": "0"
}
}
```

## Historic_Trendline
https://github.com/Caliber-Mulesoft/Historic_Trendline.git

- Name of Endpoint: /trendline

Example response:
```
[{
      year: 2021
      month: 12
      rolling_average: 89.65
  }{
      year: 3022
      month: 15
      rolling_average: 69.69
}]
```
