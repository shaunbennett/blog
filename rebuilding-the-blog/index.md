---
title: Rebuilding The Blog
date: "2020-05-13T08:53:05Z"
description: "I decided to rebuild my blog. Here's why I did it and how it will change how I blog."
---

Early into university I decided to build my first personal website and blog. It seemed like the natural choice, as most of my classmates already had personal websites online, and it was a good way to show off projects that I have been working on to any potential future employers. I went searching for a simple to setup blogging platform that I could run on my own server and need little maintenance. Considering a few options, I decided that the [Ghost bloging platform](https://ghost.org/) was right for me. This was around the time that [Node.js](https://ghost.org/) was starting to gain popularity, so it felt like a new shiny toy to play with.

I was extremely excited about my new website. I would spend hours tweaking the layout, working to optimize my [nginx](https://www.nginx.com/) configuration for the best performance. I knew that I wanted a beautiful looking website, and I wanted it to be _fast_. After I was satisfied with the look and feel of the website, I started brainstorming about all the awesome stuff I would write about for my new blog. I could write about projects that I have worked on, hobbies of mine, and interesting new things that I learn as I journey through university!

Fast forward a few years, where am I at now? I still run and maintain my personal website - making sure I try and stay up to date with security patches, updating my employment history, and even refreshing the layout of my website every now and then to keep up a modern look. I have spent a lot of time on this little website, and I have enjoyed (almost!) every minute of it. But where are the exciting blog posts I dreamed about when I first set this thing up? This is where I failed. It turns out that maintaining a blog and writing articles for it is a lot of work! I would spend a lot of time dreaming about the content that I wanted to produce instead of actually producing it, and then in a sort of odd type of procrastination, instead of writing for my blog I would just try to improve how it looked, or work on performance, or upgrade it so I can get the latest features that Ghost has to offer.

## A Change in Mindset

That's all fun, but I think it's time now to focus on writing content rather than trying to build the prettiest website. That is why I decided to rebuild my blog. Any time that I spend maintaining or building my blog is just time that I could have been spending on writing content, so the optimal blog for me right now is the one that takes no effort to maintain.

The maintanance for a Ghost blog isn't awful, but there is work that goes into it. I need to pay a server host like [DigitalOcean](https://www.digitalocean.com/) each month to keep the server running. I need to make sure that I have my TLS certificates regularly updated so that my blog continues working. I need to make sure that I update both Ghost and the server with any security patches that are released, and while doing that I should also make sure that I'm not using a version of linux that has passed its end of life.

This new blog takes a different approach. It is an entirely staticly hosted website, meaning that the entire source code for the website is rebuilt every time I write or update a blog post. Instead of storing blog posts in a database, they simply exist in a [git repository](https://github.com/shaunbennett/blog) as markdown files. When a new change is pushed to the repository, my website is automatically rebuilt and deployed.

Just like the layout of my website, the process of hosting it is simple. I don't need to pay for server costs because of services like [GitHub Pages](https://pages.github.com/) or [Netlify](https://www.netlify.com/) - I opted for Netlify because it gives more control over caching headers, so I can optimize the for the static assets. Static assets are built, handed off to Netlify, and then they worry about the hosting, TLS certificates, and everything else.

Now all that's left is for me to sit down and get writing. There is a lot I want to talk about, so I hope you come back soon and join me on this journey. Finally, if you are like me and have been dreaming about blogging without actually doing it, take this as inspiration to put yourself out there and go for it. I understand that the vulnerability of writing a blog is scary, but that's also the beauty of it.

