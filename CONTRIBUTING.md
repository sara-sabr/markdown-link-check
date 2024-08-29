Contributing
============

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## New features

### Warn on broken links

Instead of throwing an error when a broken link is detected, the test now displays a warning message listing the broken links.

### Broken link tracker

The broken link tracker automatically saves any detected broken links to `data.json` each time the test is run.

For each broken link, a dictionary is saved with the following key-value pairs:
- **url_Location**: The page or post where the broken link was found.
- **initial_date**: The first date the broken link was detected.
- **latest_date**: The most recent date the broken link was detected.
- **broken**: A boolean value indicating whether the link is considered broken.

How broken links are determined: A link is considered "broken" if it remains broken for 7 days after its initial detection.

If a broken link is no longer detected in subsequent tests, it will be automatically removed from `data.json`.