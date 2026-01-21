# What-happens-when-you-type-a-url-and-hit-enter-
BTS of what happens when you type a URL and hit enter? Making tech easier with simple explanation!!!

Let me ask you something.
You open your browser, type a URL in the search bar, hit Enter, and boom — the website appears.
Simple, right?
But in the background… a very big journey is happening.
And the website will show you the desired output only if the URL is typed correctly.

Let’s talk about that journey.

First Problem: Computers Don’t Understand Website Names
Here’s the first thing to understand:

Servers and computers only understand binary things.
They don’t understand names like www.google.com.
As humans, it’s impossible for us to remember IP addresses like 142.250.190.14, so we remember websites by names.
But to make this understandable for the server, the first step is to find the IP address that is mapped to that website.

So the big question becomes:

How do we find the IP address of a website?

Step 1: Browser Cache — “Have You Been Here Before?”
When you hit Enter, the browser first checks its own cache and asks:

“Hey, has this user visited this website before?”

If yes → the browser already has the IP address
It simply returns the request
No extra work needed
But if the website is not found in the browser cache, then the browser says:

“Okay, I need help.”

Step 2: OS Cache — “Do You Know This Website?”
Now the browser asks the Operating System.

The OS starts checking:

The hosts file
System temporary memory
Recently visited websites
If the OS still can’t find the IP address, it realizes:

“This is not local. I need to go outside.”

Step 3: DNS Resolver — The ISP Enters the Chat
Now the OS calls the resolver.

The resolver is basically your ISP, and it knows where to locate the root servers.

The resolver:

Receives the request
Checks its own cache
If the website is not there, it goes global
Step 4: Root Server — “I Don’t Know, But I Know Who Does”
The resolver asks one of the root name servers:

“Where can I find the IP address for this website?”

Important thing:

The root server does not know the IP address
But it knows where to locate the TLD server
There are 13 root name servers in total.

So the root replies:

“I don’t know this website, but since it ends with .com, go ask the .com TLD server.”

Step 5: TLD Server — “Here Are the Name Servers”
Now the resolver goes to the .com TLD server and asks:

“Do you know the IP address of this website?”

The TLD server says:

“No, I don’t know the IP address…
But I do know the name servers associated with this domain.”

For example:

ns1.domain.com
ns2.domain.com
The resolver stores this information.

Step 6: Authoritative Name Server — The Final Boss
Now the resolver goes to the Authoritative Name Server.

Become a member
This server:

Is connected through the domain registrar
Knows everything about the domain
Answers DNS queries
Stores website IPs, emails, records
Does not ask anyone else
Does not look in cache
It is the ultimate authority.

So when the resolver asks:

“Give me the IP address of this website”

The authoritative server finally responds with the real IP address

Step 7: The Journey Back Home
Now the resolver takes the IP address and goes back:

Gives the IP to the Operating System
OS saves it in memory
OS gives it to the browser
Now the browser says:

“Great. Now I know where to go.”

Step 8: Browser Requests the Website
The browser connects to that IP address and requests:

HTML document
CSS (for styling)
JavaScript files
Images, fonts, and other media
The browser discovers references to these files and sends requests for them.

Finally… the page renders

Wait… Isn’t There a DNS Loop Problem?
Now you might think:

The authoritative name server is ns1.domain.com
But that is a subdomain of domain.com
So how can we resolve the subdomain before the domain?

That sounds like a loop, right?

The Solution: Glue Records
This is where Glue Records come in.

When the resolver asks the .com TLD server, the response includes:

The name of the authoritative name server
AND at least one IP address of that name server
That extra IP information is called Glue.

So the resolver:

Does not need to resolve the name server again
Can directly connect using the IP
And the circular dependency is broken
Final Thoughts
So yes…

When you type a URL and press Enter:

Caches are checked
Root servers are contacted
TLD servers guide the way
Authoritative servers give the final answer
Glue records prevent infinite loops
All of this happens in milliseconds.

And that’s the hidden journey behind a single Enter key press!!!
