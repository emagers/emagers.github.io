---
layout: page
title: "JSON Schema Validation"
name: json-schema-validation
github: https://github.com/emagers/json-schema-validation
date: 2021-04-25
---
{% include scripts.html %}

GitHub Action that allows you to define and run tests against your JSON schema.

This was a project that came out of a need to be able to validate new versions of a JSON schema that I was developing to communicate data between the company I was working for at the time and a third-party company. The schema was then to be used by both companies to ensure that the data transmitted and received was in the appropriate format. Due to the nature and timeline of the project, I had to deliver an initial schema early on with an understanding that it would be modified to meet our needs as decisions were made for the larger project.

In order to test that the initial schema was correct and worked with the data we were expecting, I worked with analysts to come up with test scenarios for our known use-cases. I then wrote this GitHub action where you can define a set of tests which are then validated against the input schema. When the action runs, it outputs any failures much like a unit test would.

This allowed me to quickly iterate versions of the schema as I could ensure that the any updates were not breaking previously defined tests.

Visit the [GitHub repo]({{ page.github }}) to learn more about how you can use it in your own GitHub workflows.