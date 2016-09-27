#
# This Dangerfile is taken form https://github.com/iflix-letsplay/Dangerfile,
# feel free to open a pull request to suggest new rules or fixes.
#

# Make it more obvious that a PR is a work in progress and shouldn't be merged yet
warn('PR is classed as Work in Progress') if github.pr_title.include? '[WIP]'

# Warn when there is a big PR
warn('Big PR') if git.lines_of_code > 500

# Don't let testing shortcuts get into master by accident
fail('focused `describe` left in tests') if `grep -r fdescribe *Tests/ `.length > 1
fail('focused `it` left in tests') if `grep -r fit *Tests/ `.length > 1

# Make sure the commit message is formatted properly
# Rules: https://github.com/jonallured/danger-commit_lint#usage
commit_lint.check warn: :all