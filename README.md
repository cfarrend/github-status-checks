# github-status-checks
Testing GitHub Actions suite and status checks

## Commits
These commits are in order from oldest to newest

### b147efab0447fe54c7ea567508ccfabb555816f4
First commit, has a GitHub action that fails. If I query the API by using
```
curl -i -u cfarrend:$GITHUB_TOKEN https://api.github.com/repos/cfarrend/github-status-checks/commits/b147efab0447fe54c7ea567508ccfabb555816f4/status
```

I get the response
```
{
  "state": "pending",
  "statuses": [

  ],
  "sha": "b147efab0447fe54c7ea567508ccfabb555816f4",
  ...
```

### cd7d5b99232905a884885b9ee2a7c8bfde48ebbc
Same as the previous commit in terms of the check - this time I am going to manually POST a failed commit status using `curl` again
```
curl -i -u cfarrend:$GITHUB_TOKEN -X POST -d '{"state": "failure"}' https://api.github.com/repos/cfarrend/github-status-checks/statuses/cd7d5b99232905a884885b9ee2a7c8bfde48ebbc
```

Now when querying the API for status
```
{
  "state": "failure",
  "statuses": [
    {
      "url": "https://api.github.com/repos/cfarrend/github-status-checks/statuses/cd7d5b99232905a884885b9ee2a7c8bfde48ebbc",
      "avatar_url": "https://avatars1.githubusercontent.com/u/12799795?v=4",
  ...
```

If you click on the 'x' next to this commit which shows the different checks. You will see that there is one from GitHub actions
