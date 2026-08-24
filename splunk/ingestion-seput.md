# Splunk Ingestion Setup

## Objective

The goal of this stage is to make the logs required for the investigation available in Splunk.

Before configuring the ingestion, I first wanted to confirm that my Splunk environment was operational and that I could access the web interface with administrative privileges.

---

## Initial Source Selection

For the first stage of ingestion, I decided to start with:

`/var/log/auth.log`

I selected this source because authentication events are particularly relevant to the initial stages of a security investigation.

This log can provide information about events such as:

- Successful and failed authentication attempts
- SSH sessions
- Remote source IP addresses
- `sudo` activity
- Authentication-related events

Starting with a single source will also allow me to focus on understanding the ingestion process before adding additional data sources.

Other sources, such as `/var/log/syslog`, service-specific logs, or audit logs, may be incorporated later if they become relevant to the investigation.

---

## Selected Ingestion Method

Because Splunk Enterprise and the Linux log source are running on the same system in this laboratory, I will use a file monitoring input to ingest the selected log.

The planned source is:

`/var/log/auth.log`

This approach was selected because it is appropriate for the current laboratory architecture and allows me to clearly identify the original log source inside Splunk.

A Universal Forwarder is not required for this initial setup because the data source and Splunk Enterprise are located on the same host.

---

## Laboratory Environment Verification

Before configuring the ingestion, I verified that Splunk Enterprise was operational.

I confirmed that:

- Splunk started successfully
- The Splunk web server became available on port `8000`
- I was able to access the Splunk Enterprise web interface
- I was able to log in with administrative privileges

At this point, the Splunk environment is ready for the ingestion configuration.

---

## Current Status

The ingestion source and method have been selected, but the actual ingestion of `/var/log/auth.log` has not yet been configured or validated.

The next steps will be:

1. Confirm that `/var/log/auth.log` is available on the Linux system
2. Configure Splunk to monitor the file
3. Verify that events are being indexed
4. Confirm the assigned metadata, including `host`, `source`, `sourcetype`, and `index`
5. Validate that the ingested events can be searched successfully

---

## Current Stage

**Stage:** Splunk Ingestion  
**Status:** In progress

The environment is operational and ready for the ingestion configuration.
