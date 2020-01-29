# github-status-checks
Testing GitHub Actions suite and status checks

## b147efab0447fe54c7ea567508ccfabb555816f4
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
