# CaptainCook4D: A Dataset for Understanding Errors in Procedural Activities

<div align=center>
  <a src="https://img.shields.io/badge/project-website-green" href="https://captaincook4d.github.io/captain-cook/">
    <img src="https://img.shields.io/badge/project-website-green">
  </a>
  <a src="https://img.shields.io/badge/paper-arxiv-red" href="https://arxiv.org/abs/2312.14556">
    <img src="https://img.shields.io/badge/paper-arxiv-red">
  </a>
  <a src="https://img.shields.io/badge/bibtex-citation-blue" href="https://captaincook4d.github.io/captain-cook/#citation">
    <img src="https://img.shields.io/badge/bibtex-citation-blue">
  </a> 
</div>

<p align="center">
  (This page is under continuous update and construction.)
</p>


> **DISCLAIMER**: The proposed data splits showcase the ways in which our dataset can be used. We do not claim that these splits are the best or the only way to use the dataset. 
> We encourage the community to explore other ways to use the dataset and share their findings with us.

----

<div>
    <h3>Annotation Files</h3>
</div>

1. Annotation CSV
   1. Activity ID and Step ID Mapping
   2. Activity Step Description
   3. Average Segment Length
   4. Error Annotations
   5. Recording ID and Step ID Mapping
   6. Step Annotations
   7. Step ID and Step Description Mapping
2. Annotation JSON
   1. Activity ID and Step ID Mapping
   2. Complete Step Annotations JSON
   3. Error Annotations
   4. Error Category ID
   5. Recording ID and Step ID Mapping
   6. Step Annotations
   7. Step ID and Step Description Mapping
3. Data Splits
   1. Splits based on Environments
      1. Combined
      2. Only Normal Videos
   2. Splits based on Persons
      1. Combined
      2. Only Normal Videos
   3. Splits based on Recipes
      1. Combined
      2. Only Normal Videos
   4. Splits based on Recordings
      1. Combined
      2. Only Normal Videos
4. Metadata
   1. Average Segment Length
   2. Video Information
5. Task Graphs

----

<div>
    <h3>File Contents</h3> 
</div>


File: **activity_id_step_id_mapping.csv**

| Column Name   | Type   | Description                        |
|---------------|--------|------------------------------------|
| activity_idx  | int    | Activity ID                        |
| activity_name | string | Name of the activity (Recipe Name) |
| step_indices  | list   | List of Step IDs                   |

File: **activity_step_description.csv**

| Column Name      | Type   | Description                        |
|------------------|--------|------------------------------------|
| activity_idx     | int    | Activity ID                        |
| activity_name    | string | Name of the activity (Recipe Name) |
| step_index       | int    | Step ID                            |
| step_description | string | Description of the step            |

File: **average_segment_length.csv**

| Column Name            | Type   | Description                            |
|------------------------|--------|----------------------------------------|
| activity_id            | int    | Activity ID                            |
| activity_name          | string | Name of the activity (Recipe Name)     |
| average_segment_length | float  | Average segment length of the activity |

File: **error_annotations.csv**

| Column Name       | Type   | Description                          |
|-------------------|--------|--------------------------------------|
| recording_id      | int    | Recording ID                         |
| step_id           | int    | Step ID                              |
| start_time        | float  | Start time of the step               |
| end_time          | float  | End time of the step                 |
| description       | string | Description of the step              |
| has_errors        | bool   | Error in the step                    |
| Preparation Error | bool   | Error Category: Preparation Error    |
| error_description | string | Description of the preparation error |
| Measurement Error | bool   | Error Category: Measurement Error    |
| error_description | string | Description of the measurement error |
| Order Error       | bool   | Error Category: Order Error          |
| error_description | string | Description of the order error       |
| Timing Error      | bool   | Error Category: Timing Error         |
| error_description | string | Description of the timing error      |
| Technique Error   | bool   | Error Category: Technique Error      |
| error_description | string | Description of the technique error   |
| Temperature Error | bool   | Error Category: Temperature Error    |
| error_description | string | Description of the temperature error |
| Missing Step      | bool   | Error Category: Missing Step         |
| error_description | string | Description of the missing step      |
| Other             | bool   | Error Category: Other                |
| error_description | string | Description of the other error       |


File: **error_category_idx.csv**

| Column Name        | Type   | Description         |
|--------------------|--------|---------------------|
| error_category_idx | int    | Error Category ID   |
| error_category     | string | Error Category Name |


File: **recording_id_step_idx.csv**

| Column Name  | Type | Description                       |
|--------------|------|-----------------------------------|
| recording_id | int  | Recording ID                      |
| activity_idx | int  | Activity ID                       |
| step_indices | list | List of Step IDs in the recording |


File: **step_annotations.csv**

| Column Name  | Type   | Description                        |
|--------------|--------|------------------------------------|
| recording_id | int    | Recording ID                       |
| step_id      | int    | Step ID                            |
| start_time   | float  | Start time of the step             |
| end_time     | float  | End time of the step               |
| description  | string | Description of the step            |
| has_errors   | bool   | Error in the step                  |


File: **step_idx_description.csv**


| Column Name      | Type   | Description             |
|------------------|--------|-------------------------|
| step_idx         | int    | Step ID                 |
| step_description | string | Description of the step |


----

File: **step_idx_description.json**

```json
{
    "step_idx": "step_description"
}
```

File: **step_annotations.json**

```json
{
    "1_7": {
        "recording_id": "1_7",
        "steps": [
            {
                "step_id": 3,
                "start_time": "start_time",
                "end_time": "end_time",
                "description": "description",
                "has_errors": "has_errors"
            }, 
            ....
        ]
    },
    ....
}
```