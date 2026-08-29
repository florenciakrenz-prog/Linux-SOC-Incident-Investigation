# Splunk Fields — Learning Notes

During the ingestion validation, I learned an important distinction between raw events and extracted fields in Splunk.

## Raw event

A raw event contains the original information received by Splunk from the data source.

For example:

`session opened for user root`

From this event, I can read that a session was opened for the `root` user.

## Extracted field

Seeing `root` inside the raw event does not necessarily mean that Splunk has extracted it as a field such as:

`user=root`

The information can exist in the event without being available as a structured field.

This helped me understand that a successful ingestion and field extraction are different processes.

## What I learned

If I can see the information in the raw event but cannot find a corresponding field, it does not mean that the ingestion failed. Splunk may have received and indexed the event correctly without extracting that specific value as a field.
