---
layout: post  
title: Building an IP Checker Page with Cloudflare Workers
tag: Cloudflare Workers 
---

In this blog post, we will explore how to create an IP checker page using Cloudflare Workers. Cloudflare Workers provide a serverless execution environment that allows you to run JavaScript code at the edge of the Cloudflare network. By leveraging Workers, we can build a simple and efficient IP checker page that provides information about the visitor's IP address.

## Prerequisites

Before we dive into the implementation, make sure you have the following:

- A Cloudflare account: Sign up for a free account if you don't have one already.
- A text editor or integrated development environment (IDE) to write code.
- Basic knowledge of JavaScript.

## Getting Started

### Create a new Cloudflare Worker

1.  Log in to your Cloudflare account and navigate to the "Workers" section.
2.  Click on "Create a Worker" to create a new worker.
3.  Give your worker a name, such as "IPCheckerPage."
4.  Copy the code from the provided [GitHub repository](https://raw.githubusercontent.com/cjthedj97/ip_page/main/worker.js) and paste it into the worker editor.

### Understanding the code

The code provided in the GitHub repository is a basic implementation of an IP checker page. It uses the Cloudflare Workers API to fetch the client's IP address and display it on a simple HTML page.

### Customize the HTML page

- Modify the HTML content within the `const html` variable to match your desired layout and design.
- Feel free to add additional information or styling to enhance the page's appearance.
  
> Please change the fav icon linked in the header before using my code, thanks.
{: .prompt-info }

### Deploy the worker

1.  Save the worker code and click on the "Save and Deploy" button to deploy it.
2.  Cloudflare will provide you with a unique URL for your worker. This URL will serve as the IP checker page.

### Test the IP checker page

- Visit the provided URL in your web browser.
- You should see the IP address displayed on the page.

## Conclusion

By utilizing Cloudflare Workers, we have successfully built an IP checker page that fetches and displays the client's IP address. Cloudflare Workers offers a simple and cost-effective solution for running serverless code at the edge of the network. 

Remember to explore the [Cloudflare Workers documentation](https://developers.cloudflare.com/workers) for more advanced features and possibilities.
