---
layout: page
title: "Azure Board Validation Action"
name: ab-story-validation-action
github: https://github.com/emagers/ab-story-validation-action
date: 2021-02-24
---

GitHub Action to validate that pull requests are commented with a link to an Azure Boards story.

The Azure Board Validation GitHub Action was born from a requirement at the organization I worked on at the time which was that every development story in the Azure DevOps(ADO) project board must be linked to a pull request before it can be moved to closed.

The idea was that if we are audited and had the need to be to show where the changes in GitHub came from, and why they were made, this link would provide the information. As right or wrong as this requirement was, it was a pain in the butt to manage. This criteria required the developer, the person doing the pull request, and the person approving the story all to remember that the link needed to exist, and what we found was that everyone involved regularly forgot.

This GitHub Action takes advantage of the fact that there is already an ADO bot which will monitor pull requests and create the link if you comment the story number in a particular format. When the action runs, it validates whether the ADO bot found a story comment and created the link. If the bot was able to create the link, the action status receives a green check-mark. If the bot did not comment, or could not create a link with the provided story number, then the action fails and the pull request status check fails as well.

This has removed some of the frustration around this organizational requirement by at least providing an earlier and more consistent reminder to tie our pull requests to stories.

Visit the [GitHub repo]({{ page.github }}) to learn more about how you can use it in your own GitHub workflows.