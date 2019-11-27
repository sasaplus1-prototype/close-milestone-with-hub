# close-milestone-with-hub

close milestone with [hub](https://hub.github.com)

## How to close milestone with hub

```console
$ hub api repos/sasaplus1-prototype/close-milestone-with-hub/milestones > /tmp/milestones.json
$ jq '.[] | select(.title == "ver.1.0") | .number' /tmp/milestones.json > /tmp/milestone_number.txt
$ hub api -X PATCH repos/sasaplus1-prototype/close-milestone-with-hub/milestones/$(cat /tmp/milestone_number.txt) -f 'state=closed'
```

## License

The MIT license.
