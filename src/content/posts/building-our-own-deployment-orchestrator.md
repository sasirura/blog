---
title: How We Built Our Own Orchestrator for Cloud Deployments
published: 2025-08-31T02:39:03+00:00
description: "How we built our own orchestrator to simplify cloud deployments using Go, Pulumi, and Backstage."
updated: ''
tags:
  - go
  - pulumi
draft: false
pin: 0
toc: true
lang: 'en'
abbrlink: 'building-our-own-deployment-orchestrator'
---

## Introduction
First of all I got to write this post after a long period of time. What happened was I joined a new company and I was so busy with adapting to my new work. I'm planning to write on these later. On this post I want to write about this interesting technology which is how we built our own orchestrator to ease our deployments on our cloud infrastructure.

## So, What Is an Orchestrator?

According to *[Thoughtworks](https://www.thoughtworks.com/en-de/radar/techniques/platform-orchestration)*, **Platform Orchestrators** are a “new generation of tools that go beyond the traditional  platform-as-a-service (PaaS) model and offer published contracts between developers and platform teams. The contract might involve provisioning  cloud environments, databases, monitoring, authentication and more in a  different environment. These tools enforce organizational standards  while granting developers self-service access to variations through  configuration.”

## Manual Deployment Workflow

Let’s first break down how we provision our infrastructure. Our cloud provider is GCP. So what we do is when we have a repository, that repository requires a Dockerfile and cloudbuild.yml file. To deploy we will connect that repository to the Cloud Build and create a connection. Then we create the Cloud Build trigger pointing out the cloudbuild file. In that cloud build file there are instructions to build the image based on what environment, and then that image will be pushed to the GCP Artifact Registry. Then we deploy the image using Cloud Run (basically our main deployments are serverless).

## How Developers Use the Orchestrator Now

So we already have a Backstage internal developer platform (more on this in future) but the basic idea is we can onboard components to the Backstage and those components are connected to a repository. Those onboarded components are basically a yml file which saves necessary data like which GCP project and the region and so on. So what we do is based on these data the user can ask our orchestrator to create a trigger (at the moment it’s based on tags). So after it happens the user just has to click the deploy button, that’s all — no more complicated configurations and thinking about creating yml files.

## Implementation Details

The orchestrator is written in Go and to do the orchestration we are using Pulumi. Pulumi has a Go SDK which became easy since we can write Pulumi code in Go. So it’ll get the pulumi.yml file and based on that do the necessary updates like create, update, delete resources. This is the basic idea but there are a lot of things in the middle like how Pulumi handles the state and logs and all. I’ll discuss them all in a future post because each of them can have their own post.

## What I Learned

This past year building this orchestrator taught me a lot of things that I never learned for the past 4 years. I only worked with TypeScript before but I learned Go language which was great since the Go language enabled me to think differently about how we handle things and how straightforward the language is with less weird stuff. I used Vercel before but now I understand how it works under the hood. Basically I became a software engineer + platform engineer + devops engineer thanks to this.

I kept this article simple because I just wanted to start writing again. My hope is that it will motivate me to write more in-depth posts in the future.

