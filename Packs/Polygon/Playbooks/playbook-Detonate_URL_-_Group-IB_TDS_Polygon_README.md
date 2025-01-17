Detonates one or more files using the Polygon integration. This playbook
returns relevant reports to the War Room and file reputations to the context data.

## Dependencies
This playbook uses the following sub-playbooks, integrations, and scripts.

### Sub-playbooks
* GenericPolling

### Integrations
This playbook does not use any integrations.

### Scripts
* Set

### Commands
* polygon-upload-url
* polygon-analysis-info
* polygon-export-report
* polygon-export-pcap
* polygon-export-video

## Playbook Inputs
---

| **Name** | **Description** | **Default Value** | **Source** | **Required** |
| --- | --- | --- | --- | --- |
| url | The url object to detonate. The URL is taken from the context. | None | URL.Data | Optional |
| Interval | The duration for executing the pooling (in minutes). | 1 | - | Optional |
| Timeout | The duration after which to stop pooling and to resume the playbook (in minutes). | 60 | - | Optional |

## Playbook Outputs
---

| **Path** | **Description** | **Type** |
| --- | --- | --- |
| File.Name | string | The full file name \(including file extension\). | 
| File.MD5 | string | The MD5 hash of the file | 
| File.SHA1 | string | The SHA1 hash of the file | 
| File.SHA256 | string | The SHA256 hash of the file | 
| File.Type | string | File type | 
| File.Malicious.Vendor | string | The vendor that reported the file as malicious | 
| File.Malicious.Description | string | A description explaining why the file was determined to be malicious | 
| DBotScore.Indicator | string | The indicator that was tested | 
| DBotScore.Type | string | The indicator type | 
| DBotScore.Vendor | string | The vendor used to calculate the score | 
| DBotScore.Score | number | The actual score | 
| IP.Address | String | IP address | 
| Domain.Name | String | The Domain name | 
| Domain.DNS | String | A list of IP objects resolved by DNS. | 
| URL.Data | String | The URL | 
| URL.Malicious.Vendor | string | The vendor that reported the url as malicious | 
| URL.Malicious.Description | string | A description explaining why the url was determined to be malicious | 
| RegistryKey.Path | String | The path to the registry key | 
| RegistryKey.Value | String | The value at the given RegistryKey. | 
| Process.Name | String | Process name | 
| Process.PID | String | Process PID | 
| Process.CommandLine | String | Process Command Line | 
| Process.Path | String | Process path | 
| Process.StartTime | date | Process start time | 
| Process.EndTime | date | Process end time | 
| Polygon.Analysis.ID | string | THF File ID | 
| Polygon.Analysis.Name | string | File Name | 
| Polygon.Analysis.Size | number | File Size | 
| Polygon.Analysis.Started | date | Analysis start timestamp | 
| Polygon.Analysis.Analyzed | date | Analysis finish timestamp | 
| Polygon.Analysis.MD5 | string | Analyzed file MD5 hash | 
| Polygon.Analysis.SHA1 | string | Analyzed file SHA1 hash | 
| Polygon.Analysis.SHA256 | string | Analyzed file SHA256 | 
| Polygon.Analysis.Result | boolean | Analysis verdict | 
| Polygon.Analysis.Status | string | Analysis status | 
| Polygon.Analysis.Verdict | string | Analysis verdict | 
| Polygon.Analysis.Probability | string | Verdict probability | 
| Polygon.Analysis.Families | string | Malware families | 
| Polygon.Analysis.Score | number | Polygon score | 
| Polygon.Analysis.Internet-connection | string | Internet availability | 
| Polygon.Analysis.Type | string | File type | 
| Polygon.Analysis.DumpExists | boolean | Network activity dump exists | 
| Polygon.Analysis.File | unknown | The information about files in analysis | 
| Polygon.Analysis.URL | unknown | The information about URL indicators | 
| Polygon.Analysis.IP | unknown | The information about IP indicators | 
| Polygon.Analysis.Domain | unknown | The information about Domain indicators | 
| Polygon.Analysis.RegistryKey | unknown | The information about registry keys which were modified during the analysis | 
| Polygon.Analysis.Process | unknown | The information about processes started during the analysis | 

## Playbook Image
![Polygon Detonate URL](../doc_files/Detonate_URL_-_Group-IB_TDS_Polygon.png)
