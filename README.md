# GitHub Challenge

<img src="https://octodex.github.com/images/Professortocat_v2.png" align="right" height="200px" />

Hey there!

Your challenge is ready.
Follow the instructions provided for this challenge and complete the required tasks in this repository.

Make sure your work is committed and pushed to your repository before submission.

Good luck!


---

## Operational Data Analysis

### Metrics

* response_time_ms
* cpu_percent
* memory_percent

### Log Information

* log_level
* message

### Timestamp Usage

The timestamp records when each operational event occurred and allows chronological analysis of service behaviour.

### Normal Behaviour

Records from 10:00–10:04 and 10:07–10:09 show normal operation with INFO logs, response time around 120–150 ms, CPU around 42–50%, and memory around 51–57%.

### Unusual Behaviour

Records at 10:05 and 10:06 show abnormal behaviour with ERROR logs, response times of 610 ms and 640 ms, CPU reaching 75% and 94%, and memory reaching 70% and 91%.


## Anomaly Detection Findings

The pipeline processed 10 operational records and detected 2 anomalies.

* 10:05 – High response time, Error log detected.
* 10:06 – High response time, High CPU utilization, High memory utilization, Error log detected.

## Event Processing Flow

Operational Data → Anomaly Detection → Event Producer → Event Topic → Event Consumer → AIOps Output.

## Final Workflow Result

* Records processed: 10
* Anomalies detected: 2
* Events consumed: 2

## Issues Identified and Corrected

* Fixed error log detection (`WARNING` → `ERROR`).
* Fixed producer and consumer to use the same event topic.
* Fixed Python package imports for successful test execution.

## Limitation

The current implementation uses threshold-based anomaly detection.

## Reproduction Steps

1. Run `python src/aiops_pipeline.py`.
2. Run `pytest tests/test_aiops_pipeline.py -v`.
3. Verify that the pipeline completes successfully.

&copy; 2025 GitHub &bull; [Code of Conduct](https://www.contributor-covenant.org/version/2/1/code_of_conduct/code_of_conduct.md) &bull; [MIT License](https://gh.io/mit)

