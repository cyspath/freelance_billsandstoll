
https://medium.com/@LovettLovett/github-pages-godaddy-f0318c2f25a#.d7xywqtk7

Overview
The documentation is a little confusing when it comes to project pages, as opposed to user pages. It feels like you should have to do more, but actually the process is very easy.

It involves:

Setting up 2 static A records for the naked (no www) domain.
Creating one CNAME record for www which will point to a GitHub URL. This will handle www redirection for you.
Creating a file called CNAME (capitalised) in your project root on the gh-pages branch. This will tell Github what URL to respond to.
Wait for everything to propagate.
What you will get
Your content will be served from a URL of the form http://nicholasjohnson.com.

Visiting http://www.nicholasjohnson.com will return a 301 redirect to the naked domain.

The path will be respected by the redirect, so traffic to http://www.nicholasjohnson.com/angular will be redirected to http://nicholasjohnson.com/angular.

You can have one project page per repository, so if your repos are open you can have as many as you like.

Here's the process:

1. Create A records
For the A records, point @ to the following ip addresses:

@: 192.30.252.154
@: 192.30.252.153
These are the static Github IP addresses from which your content will be served.

2. Create a CNAME Record
For the CNAME record, point www to yourusername.github.io. Note the trailing full stop. Note also, this is the username, not the project name. You don't need to specify the project name yet. Github will use the CNAME file to determine which project to serve content from.

e.g.

www: forwardadvance.github.io.
The purpose of the CNAME is to redirect all www subdomain traffic to a GitHub page which will 301 redirect to the naked domain.

3. Create a CNAME file
Add a file called CNAME to your project root in the gh-pages branch. This should contain the domain you want to serve. Make sure you commit and push.

e.g.

nicholasjohnson.com
This file tells GitHub to use this repo to handle traffic to this domain.

4. Wait
Now wait 5 minutes, your project page should now be live.
