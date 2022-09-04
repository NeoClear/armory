---
title: "Code Review Techniques"
description: How to write code reviews that gives you return offers
date: 2022-07-02
images:
  - code-review/og-cover.png
tags:
  - Software Engineering
---

<!-- Linter is getting confused about the asterisks in cron syntax -->
<!-- markdownlint-disable MD037 -->

_This blog is just a rewrite of [How to Make Your Code Reviewer Fall in Love with You](https://mtlynch.io/code-review-love/#1-review-your-own-code-first). The purpose is just for faster personal access._

## Review Your Own Code First

Try to review your code first before submit it to your reviewer. Try to read your code as if it is the first time reading the code. Fix any linting issues and naming issues. Use an automated workflow to help you format your code.

Here's a list of basic things to check before submit them for review.

1. The linting is right.
2. Variable, method and class names are explanatory. Do not make them too short to be understood.
3. Comment your code thoroughly. Use special syntax based on company requirement.
4. For C++, do not use `using namespace ...;`, as it would mess namespace up.
5. For C++, do not rename short type names, as it would confuse readers.
6. Comments can be out dated. Make sure your code does what comment suggests.
7. Delete unnecessary code. For example, do not call `.close()` if the class destructor does it.
8. Prefer range-based loop over iterative loop.
9. Have performance in mind. Use const whenever possible. Use `string_view` over `string` if no string mutation is needed. Use reference over copy whenever possible.
10. Keep your code easy to understand. Do not use tricks over longer but clearer code. Most cases compiler would do optimization for you.
11. Do not over-engineer. Do not add extra class if that is not needed (for example, use helper function over class if extra logic is simple).
12. Your code might actually implement existing library code: do not reinvent the wheel.

## Write Clear Changelist Description

Your changelist description should contain:

1. Feature you implemented on the high level.
2. Why the change is needed.
3. Consider readers other than your teammates. Should summarize the background needed for the code change.

## Narrow Scope Changes & Separate Functional And Non-Functional Changes

Your changelist should do one thing. Do not combine multiple feature changes into one single changelist. Also, do not combine functional change with non-functional change. That is, do not submit changelist with both feature implementation and code formating.

## Take Feedbacks, Be Patient & Communicate Explicitly

Treat reviewer's comments as objective discussion of the code, not the engineer who wrote the code. Also, be patient when your reviewer is wrong. If your reviewer is wrong, it is possible that your code is not clear.

Also, try to be explicit about the code review discussion. Respond to each comment explicitly on code review tool.

## Give The Tie To The Reviewer

Sometimes reviewer could give code fixes comparable to yours. If no one is better, take theirs as they stand for opinions of most reviewers.
