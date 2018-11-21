Modified version that https://github.com/technmsg wrote. 

# slack_delete
slack_delete allows you to delete files from Slack in bulk. If you are on a free Slack plan, you can only have so many files and use up so much space. After a while, this tends to fill up. 

## Reasons For My Version

I decided to modify this script for a few reasons:

1) there was an extraneous call to json.loads() that kept it from running properly
2) python3 support
3) rate limiting to follow Slack's suggestions (https://api.slack.com/docs/rate-limits)

## Requirements

This uses the requests library that you'll need to install (probably best done in a virtual environment)

    python3 -m pip install requests

## Usage

    usage: slack_delete.py [-h] -t TOKEN [-d DAYS] [-c COUNT]

    optional arguments:
      -h, --help            show this help message and exit
      -t TOKEN, --token TOKEN
                        Specifies the OAuth token used for authentication,
                        created at (https://api.slack.com/docs/oauth-test-
                        tokens)
      -d DAYS, --days DAYS  Delete files older than x days (optional)
      -c COUNT, --count COUNT
                        Max amount of files to delete at once (optional)

## Example Run

    python3 slack_delete.py --token yourtokengoeshere -d 90
