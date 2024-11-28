---
layout: post
title:  "Understanding GitHub Limits: Size, Boundaries, and Spaces"
date:   2024-11-27 07:00:05 +0100
author: Mohamed Radwan
categories: [Blogging, Post]
tags: [github, limits] 
---

When using GitHub services, it’s crucial to understand the limits and boundaries that come with each feature. These limits determine the size of files, storage space, and the time allowed for processes like CI/CD jobs. Knowing these limits can help you plan accordingly, avoid errors, and determine when to upgrade your plan.

## 1. GitHub Actions - Artifact Limits

GitHub Actions automates workflows like building, testing, and deploying code. Artifacts are files generated during workflows that you might want to store for later use.

### Artifact Size Limit

The individual artifact size is capped at 2 GB per artifact.

**Example:**

Let’s say you have a website package file, Website-Package.zip, that is 300 MB. On the Free Plan, you can upload only 1 artifact of this size (300 MB) because the total storage is capped at 500 MB. If you try to upload a second 300 MB package, you’ll exceed the storage quota.

### Storage Quota

- Free Plan: 500 MB of total storage.
- Pro/Team Plans: 2 GB of storage.
- Enterprise Plan: 50 GB of storage.

If you upgrade to the Pro or Team Plans, you’ll get an additional 1.5 GB of storage, allowing you to upload more artifacts.

### Retention Period

Artifacts are kept for 90 days by default. For example, if you upload Website-Package.zip on March 1st, it will be automatically deleted by May 30th.

**Can I change the retention period?**

Yes, you can adjust the retention period, depending on the type of repository:

- For public repositories: you can change this retention period to anywhere between 1 day or 90 days.
- For private repositories: you can change this retention period to anywhere between 1 day or 400 days.
  
When you customize the retention period, it only applies to new artifacts and log files, and does not retroactively apply to existing objects. For managed repositories and organizations, the maximum retention period cannot exceed the limit set by the managing organization or enterprise.

[Learn more about GitHub Actions retention limits here.](https://docs.github.com/en/organizations/managing-organization-settings/configuring-the-retention-period-for-github-actions-artifacts-and-logs-in-your-organization)

If you need to retain your artifacts longer, you can download them before the retention limit expires or move them to an external storage service.

### Options for longer retention

If you need to store artifacts beyond the 90-day period, you can use GitHub Releases, or move them to an external storage service like AWS S3 or Azure Blob Storage.

## 2. GitHub Packages Storage Limits

GitHub Packages is a service for hosting software packages like Docker, npm, Maven, etc., within your GitHub repositories.

### Storage and Data Transfer Limits

- Free Plan: Includes 500 MB storage and 1 GB data transfer per month.
- Pro and Team Plans: Provide 2 GB storage and 3 GB data transfer per month.
- Enterprise Plan: Provides 50 GB storage and 100 GB data transfer per month.

**Example:**

Suppose you’re hosting a Docker image on GitHub Packages that is 300 MB in size. If you're on the Free Plan, you can store this image along with other packages up to 500 MB. After you’ve used up your 500 MB quota, you’ll need to delete or move packages to a different storage system.

### Package Size Limit

GitHub Packages has a 5 GB limit for any individual package. So, if you try to upload a package exceeding 5 GB, the upload will fail.

**Can I increase the storage?**

Yes, you can upgrade your plan for additional storage. On the Pro Plan, you get 2 GB, and on the Enterprise Plan, you get 50 GB of storage.

For more detailed information about the limits on GitHub Packages, you can visit the official GitHub documentation:

[GitHub Packages Limits](https://docs.github.com/en/billing/managing-billing-for-your-products/managing-billing-for-github-packages/managing-your-spending-limit-for-github-packages)

## 3. GitHub Releases - File and Storage Limits

GitHub Releases are used to manage downloadable software versions that can include release notes, binaries, or source code archives. It's an effective way to distribute project versions to users.

### Storage Limit

The total size limit for all files in a single release cannot exceed 2 GB.

**Example:**

Let’s say you are releasing a version of your application, and you have 3 files in the release: app-v1.0.zip (500 MB), docs-v1.0.pdf (150 MB), and changelog-v1.0.txt (10 MB). The total size of these files is 660 MB, which is within the 2 GB limit. However, if you try to add a file larger than the remaining space (e.g., a 1.5 GB binary file), it will exceed the limit, and the upload will fail.

**Can I create multiple releases?**

GitHub does not limit the number of releases you can have in a repository. Therefore, you can have 1000 releases as long as each release does not exceed the 2 GB size limit.

For example, if you have 1000 releases, each containing files totaling 2 GB, GitHub will allow you to upload all of these releases, provided the total size of each release does not exceed 2 GB. However, keep in mind that if your repository has many releases, you should be mindful of the overall repository size limit, which is 100 GB for optimal performance.

### Retention Period

Releases are retained indefinitely unless deleted by the user, unlike artifacts that are deleted after 90 days.

**Can I increase the release limit?**

No, the total size limit of 2 GB per release cannot be increased. You can either reduce the size of your release files or split them across multiple releases.

If your releases contain files larger than 2 GB, you may need to:

- Split them across multiple releases.
- Use Git LFS (Large File Storage) for large assets.


## 4. Repository Size Limits

GitHub repositories have limits on the total size, affecting the overall performance of your projects.

### Repository Size Limit

The recommended size for a repository is 1 GB, but GitHub allows repositories up to 100 GB.

Individual File Size: Files larger than 100 MB cannot be pushed.

Git LFS: Large files exceeding 100 MB can use Git Large File Storage (LFS), with its own quotas.

**Example:**

If your repository exceeds 1 GB, you may notice slower performance, especially when pushing and pulling changes. Let’s say you have a repository that contains large binary files such as images or videos. If the repository reaches 10 GB, you will face performance issues. To avoid this, you can move large files to Git LFS (Large File Storage).

**Can I store larger files?**

For large files beyond 100 MB, you will need to use Git LFS, which is designed to handle files larger than Git’s usual limits.

**Is Git LFS part of the repository size?**

Git LFS is not counted towards the regular repository size. The storage and bandwidth usage for Git LFS are tracked separately.

### Git LFS Size Limits

The default storage for Git LFS is 1 GB per user on the Free Plan. This storage can be increased by purchasing additional storage or upgrading to the Pro or Enterprise plans, which provide 50 GB of storage by default. For more information on Git LFS and its limits, you can visit 

[Git LFS Limits](https://docs.github.com/en/repositories/working-with-files/managing-large-files/about-git-large-file-storage).

### Repository Size Limits Based on Plan

- Free Plan: The repository size is recommended to stay under 1 GB for optimal performance. However, you can push up to 100 GB per repository.
- Pro and Team Plans: The repository size limit is still 100 GB, but you can use Git LFS to store large files efficiently.
- Enterprise Plan: No additional repository size limit. The repository can grow up to 100 GB, but the use of Git LFS is recommended for managing large files.

## 5. GitHub Actions - Minutes for CI/CD Jobs

When using GitHub Actions for continuous integration and deployment, the number of minutes available for running jobs is limited based on your plan.

### Minutes for Workflow Runs

- Free Plan: Includes 2,000 minutes per month.
- Pro Plan: Includes 3,000 minutes per month.
- Team/Enterprise Plans: Unlimited minutes for public repositories; however, private repositories have specific quotas based on the number of users.

**Example:**

Let’s say you have a repository with a CI/CD workflow that runs every hour. If you are on the Free Plan, that’s 2,000 minutes per month, which equates to about 33 hours of build time. After this, additional minutes will incur extra charges.

**Can I increase the minutes?**

Yes, you can upgrade to Pro or Team Plans for more minutes. On the Team Plan, you get unlimited minutes for public repositories, but for private repositories, you still have a limited number of minutes depending on the number of users.

## 6. GitHub Pages Limits

GitHub Pages is a free service for hosting static websites directly from a repository.

### Storage and Bandwidth Limits

- Storage Limit: 1 GB for your GitHub Pages site.
- Bandwidth Limit: 100 GB per month.

**Example:**

Suppose you’re hosting a website on GitHub Pages with large media files. If your site consumes more than 100 GB of bandwidth in a month (e.g., if it's a popular site with high traffic), GitHub will temporarily suspend your site until the next billing cycle.

**Can I increase the bandwidth or storage?**

GitHub Pages does not offer an option to increase bandwidth beyond 100 GB. You’ll need to move to an external hosting solution if you anticipate higher bandwidth needs.

## 7. Rate Limits and API Requests

If you’re using GitHub’s API to automate tasks, be aware of the rate limits imposed on requests.

### API Rate Limits

- Authenticated Requests: 5,000 requests per hour per user.
- Unauthenticated Requests: 60 requests per hour.

**Example:**

If you're running an automation script to fetch data from GitHub’s API and make 5,500 requests per hour, you’ll hit the rate limit. In this case, you can either authenticate your requests (for the higher limit) or space out the requests to avoid hitting the 60 request limit for unauthenticated usage.

**Can I increase the limit?**

Yes, authenticated requests allow up to 5,000 requests per hour. If you need more requests, you can split them into batches and implement caching to reduce unnecessary API calls.

## Conclusion

Understanding the various GitHub limits—whether it's for artifacts, storage, minutes, or API calls—is essential for optimizing your workflows and project management. Depending on your needs, you can adjust your GitHub plan to ensure you have enough resources or find alternative solutions like external storage or APIs to handle limits. Always keep track of your usage to avoid exceeding your limits, and plan ahead for scaling your operations efficiently.
