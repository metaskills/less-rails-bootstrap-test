
# Less Rails Bootstrap Test Project

Simple integration test project for both [less-rails](https://github.com/metaskills/less-rails) and the [less-rails-bootstrap](https://github.com/metaskills/less-rails-bootstrap) gems.


# The Setup

The `Gemfile` for this project has the latest less-rails and less-rails-bootstrap versions specified. It also has optional environment variables so you can specify a source path to a local checkout of each project. I have run `rake assets:precompile` and checked in all generated assets. That way it is easy to see if things work or what might be changed or not work when you ran `rake assets:clean` and then `rake assets:precompile` again to test.

