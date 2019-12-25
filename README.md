# Whedon API

A small service that provides the basic Whedon API. Used to help editors manage reviews for [The Journal of Open Source Software](http://joss.theoj.org). You can see him in action in [this review issue](https://github.com/openjournals/joss-reviews/issues/78).

### Here are some things that Whedon can do:

Here are some things you can ask me to do:

```
# List all of Whedon's capabilities
@whedon commands

# Assign a GitHub user as the sole reviewer of this submission
@whedon assign @username as reviewer

# Add a GitHub user to the reviewers of this submission
@whedon add @username as reviewer

# Remove a GitHub user from the reviewers of this submission
@whedon remove @username as reviewer

# List of editor GitHub usernames
@whedon list editors

# List of reviewers together with programming language preferences and domain expertise
@whedon list reviewers

# Change editorial assignment
@whedon assign @username as editor

# Set the software archive DOI at the top of the issue e.g.
@whedon set 10.0000/zenodo.00000 as archive

GENERAL EDITORIAL TASKS

# Compile the paper
@whedon generate pdf

# Compile the paper from alternative branch
@whedon generate pdf from branch custom-branch-name

# Ask Whedon to check the references for missing DOIs
@whedon check references

EDITOR-ONLY TASKS

# Remind an author or reviewer to return to a review after a
# certain period of time (supported units days and weeks)
@whedon remind @reviewer in 2 weeks

# Ask Whedon to accept the paper and deposit with Crossref
@whedon accept

```

## Generating PDFs

Whedon-api also provides a default front page which allows the generating
of PDFs for multiple journals. See https://whedon.theoj.org/

## Development

Is it green? [![Build Status](https://travis-ci.org/openjournals/whedon-api.svg?branch=master)](https://travis-ci.org/openjournals/whedon-api)

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Added some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request

## Deploying

Whedon uses the following environment variables:

1. APP_ENV: Rack standard 'development', 'test' and 'production' modes (defaults to test)
2. WHEDON_JOURNAL: Default journal to target (defaults to none)
3. WHEDON_DEPLOY: 'local' or 'heroku' (defaults to heroku)

To deploy a version of Whedon on Heroku, an `app.json` template is provided:

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/openjournals/whedon-api)

For installing locally see the [DEVELOPMENT](./doc/DEVELOPMENT.org) doc.

## License

The source code for Whedon is published under the permissive MIT or
expat [license](LICENSE).
