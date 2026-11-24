# Prompt Reflection

One thing the agent got wrong was assuming and documenting a live deployment URL before the app had actually been deployed. I noticed the mistake because the hosting URL was only a proposed Render-style address and no successful deployment had been verified. I initially depended on the written deployment instructions rather than checking a real public HTTP response.

I fixed the prompt and documentation process by first configuring and validating the deployment files, then using credentials with explicit user authorization to publish the project to GitHub and create a Render service. I verified the real public URL and the Reception PIN screen by sending live HTTP requests, and I replaced the unverified setup with the confirmed deployment details.

The corrected approach is to never present an address as live until hosting confirms the service and a public request succeeds. A deployment prompt should require repository publication, hosting authentication, successful build/deploy status, and an HTTP smoke test before writing the live link into the README.
