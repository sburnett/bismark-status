bismark-status
==============

This repository contains a simple Web interface for viewing status of the
BISmark deployment.

To use:

1. Generate router availability information using
https://github.com/sburnett/bismark-tools. For example, I run the following cron
job every 10 minutes:

        $HOME/go/src/github.com/sburnett/bismark-tools/scripts/availability-intervals \
            --output_file=$HOME/public_html/bismark-status/status.json \
            --cache_dir=/data/users/sburnett/bismark-availability-intervals-cache \
            --outage_threshold=5m \
            --output_leveldb=$HOME/bismark-availability-intervals.leveldb

(It will take longer to run the first time.) Make sure `status.json` is in the
same directory as `index.html` from this repository.

2. Serve the `www` directory on the Web.
