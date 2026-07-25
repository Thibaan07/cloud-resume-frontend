# Cloud Resume Challenge — Frontend

My resume, built as a static HTML/CSS site and deployed on AWS — part of the [Cloud Resume Challenge](https://cloudresumechallenge.dev/docs/the-challenge/aws/).

## Live site

Hosted via S3 + CloudFront (HTTPS): *https://d2kzbc507gzeij.cloudfront.net/*

## Tech stack

- **HTML/CSS** — no frameworks, hand-written
- **Amazon S3** — static website hosting
- **Amazon CloudFront** — HTTPS + global CDN caching in front of S3
- **JavaScript (vanilla)** — calls a serverless API to display a live visitor count

## How the visitor counter works

The page calls an API Gateway endpoint on load, which triggers a Lambda function to increment a count in DynamoDB. See the backend repo below for that code.

## Related repo

Backend (Lambda, DynamoDB, API Gateway, Terraform): [cloud-resume-backend](https://github.com/Thibaan07/cloud-resume-backend)

## What I learned

- Deploying a static site to S3 and understanding why CloudFront is needed in front of it for HTTPS and speed
- Wiring frontend JavaScript to a serverless backend via `fetch()`
- CloudFront cache invalidation — and why changes to S3 don't show up immediately without it
