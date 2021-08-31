# attachmentgenie-pdksync

Repository/Project to manage the attachmentgenie modules., based on [puppetlabs/pdksync](https://github.com/puppetlabs/pdksync).

## Bootstrap setup

    bundle install --path .bundle/gems/
    bundle exec rake git:clone_managed_modules

## PDK update to all modules

warning: this is a destructive action, this process will remove and recheckout all modules. This means all local changes will be removed!!

    bundle exec rake pdksync

## Bump minial puppet version required

    bundle exec rake 'pdksync:update_requirements[puppet,version_requirement,>= 6.21.0 < 8.0.0]'

## Commit all local changes

    bundle exec rake 'git:create_commit[master,"Applying trivial change"]'
    bundle exec rake 'git:push'
    bundle exec rake 'git:create_pr["Applying trivial change"]'