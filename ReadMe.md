This is a ColdFusion Component for interacting with the [Postmark API](http://www.postmarkapp.com).

Free to use, free to change & improve.  Please share those changes back with the community.
Version 1 was created by Jonathan Lane \([jonathan.lane@gmail.com](mailto:jonathan.lane@gmail.com)\).

---

Pretty easy to use.  Drop `postmarkapi.cfc` in with your files and invoke it like so:

	<cfinvoke component="postmarkapi" method="sendMail" returnVariable="pmCode">
		<cfinvokeargument name="mailTo" value="YOUR RECIPIENT">
		<cfinvokeargument name="mailFrom" value="SENDING ADDRESS">
		<cfinvokeargument name="mailSubject" value="YOUR SUBJECT">
		<cfinvokeargument name="apiKey" value="YOUR API KEY">
		<cfinvokeargument name="mailHTML" value="<body><h1>It worked!</h1></body>">
	</cfinvoke>

Alternatively, the `createObject` syntax is:

	postmark = createObject("component", "path.to.postmarkapi");
	postmark.sendMail(
		"recipient@domain.com"
		,"sender@domain.com"
		,"Email Subject"
		,"your-postmark-api-key"
		,"<body><h1>It worked!</h1></body>"
	);

The component has 4 required arguments and accepts an additional 4 optional arguments.

*REQUIRED:*

* **mailTo:** your recipient
* **mailFrom:** sending address
* **mailSubject:** subject of your message
* **apiKey:** the API key for the Postmark "server" you're using

*OPTIONAL:*

* **mailReply:** reply-to address
* **mailCc:** CC recipient
* **mailHTML:** content of the HTML message body
* **mailTxt:** plain text message body

The component returns the status code returned from Postmark.

The component was built against CF 8, but should work fine at least back to CF 6 (not tested though).

Feel free to send me any questions or comments.  I'll do my best to answer them.