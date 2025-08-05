# Overview

The goal is to design a rest wrapper on top of kafka that accepts messages as json, validates them based on custom rules and finally converts the message to avro and send it to kafka. 

The solution should centre around performance and understanding of java’s latest features.

 The candidate will be judged by choices made in the code and technologies used. The solution doesn’t have to be the fastest possible but be reasonably performant and candidate be ready to discuss choices and tradeoffs made in the code. 

Endpoints

POST /messages?topic={topic}&key={key}

Accept arbitrary (and nested) JSON, validate against topic rules, convert to Avro using the schema registry, auto-create Kafka topic if missing, and send to kafka. Wait for ack from Kafka before returning to the caller.

POST /topics/{topic}/rules

Register validation rules (3 types: in, regex, range) for a given topic; reject non-conforming messages with HTTP 400.

# Requirements

Java 21

Spring boot

Docker compose using confluent kafka and schema registry images.

README outlining build/run steps, configuration and potential comments on tradeoffs/choices and improvements.

Comply with our API spec  

For storage of rules any storage system is welcome but rules must be persisted outside of the jvm process 

# Expectations

We expect the code to be well structured and in a state you are proud of handing over.

We expect you to be familiar with the codebase and able to reason about it

We expect you to test the parts of the codebase that you believe need special attention



For this assignment we can assume a single instance of the API to be running but bonus points are given if multiple instances are supported as well. 

We’ve attached the OpenAPI specs for the API and candidates are welcome to generate the backend/client or even use Agentic tools to speed up delivery. 

In general we expect your assignment back within a week but if you need longer time we prefer you let us know instead of submitting unfinished work.


Submit the assignment on github or gitlab as a public repository with your work on a branch