---
layout: page
title: 7 CyberSecurity Tips for Developers
---


No matter how many penetration tests your organization runs per year, this thing always gives you headaches and overtime. Yes, we're talking about manual penetration tests.

It's undeniable that every now and then you get a list of vulnerabilities in a report created by penetration testers. You've definitely experienced fixing these vulnerabilities in your web applications.

But it's certainly not as easy as it is to spell the names of the vulnerabilities.

Here are the top 7 CyberSecurity Tips, these tips will save you from getting migraines:

## 1. Input Validation

While creating the web application, you should make a note of every function that takes user input. An Excel sheet would work wonders. Name of the parameter, what type of values, etc...

Closely understand what is the requirement of the user's input here and how you could take the minimum possible input from the user.

Boolean, Integers and Floats types are safe inputs by design but Strings and Objects types are where penetration testers try to have their fun.

It's best practice to determine which type of input is required. On top of it, using Regex to whitelist and verify that input is really what is expected by the application.

**For Example:** You need to take input as an email address. Instead of taking the input and immediately processing it through the database, you should process it through a middleware function like this:
```js
function validateEmail(email) {
  const emailRegex = /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/;
  return emailRegex.test(email);
}
```

This was just an example of what middleware function could be used to validate email addresses from the user's input.

After understanding the above code you should be able to create middleware functions for any type of input validation.

## 2. Role-Based Access Control

Whenever a hierarchy exists in an organization, there is a need for a role-based web application.

Roles could be anything from Administrator to the normal user. A role is typically associated with the real role of a person in the business hierarchy.

A web application could have 1 or more roles. In the case of 1 role, there is no need to have authorization-based access control, except for the requirement to check whether the user is logged in.

But when the role count increases to 2, you need to have proper access control.

The user of one role shouldn't be able to perform tasks that should only be performed by the user of another role.

**For Example:** A normal user shouldn't be able to perform a task such as creating new users in the application which according to business logic, only an Administrator should be able to perform.



## 3. Session Management

Managing user sessions includes creating, validating and deleting session cookies.

A session cookie leakage could lead to all sorts of problems including account takeover.

It's a best practice to delete the session cookies from the database after the user logs out to ensure that the cookie can no longer be used by anyone in case an attacker has physical access to the user's computer.


## 4. HTTP Security headers configuration

Some HTTP security headers need to be in place to prevent various types of attacks.

This page from [Mozilla](https://infosec.mozilla.org/guidelines/web_security) explains exactly what you need to understand and implement in the application to ensure that all browser-related security requirements are met.


## 5. Error Handling
Handling the errors the right way in the application is very important. Default error pages of the servers and frameworks are known to reveal information that could be useful to attackers for future exploitation and discovery of new attack scenarios.


**For Example:** A custom error page like this will prevent the leakage of any information.

***

![https://upload.wikimedia.org/wikipedia/commons/e/e0/Wikimedia_error_404.png](https://upload.wikimedia.org/wikipedia/commons/e/e0/Wikimedia_error_404.png)

***

## 6. Secure Javascript
Creating functionality in Javascript is super easy but when it comes to client-side security, it's a rough road.

When it comes to input validation, the first tip is going to help you. But writing secure client-side Javascript is more than that.

This page from [Mozilla](https://developer.mozilla.org/en-US/docs/Web/Security) is going to help you through your journey of your secure by design web application's client-side.


## 7. Patching
Outdated softwares almost always have known vulnerabilities. That's where patching the software and libraries helps your overall web application security posture to be ideal for security by design principles.

Having outdated software doesn't mean only one component could be attacked, it certainly affects the whole application.

You should ensure that your code is not relying on any sort of outdated version of a library. Patching or updating those libraries to the latest versions routinely is a major step towards the security of your web applications.


# Conclusion
Following all the 7 tips listed above will improve your security posture to the next level.

I usually post tips for developers, so feel free to browse through my blog.

Soon, I'll be going through these tips with more details and examples.

So, Until then: STAY TUNED!