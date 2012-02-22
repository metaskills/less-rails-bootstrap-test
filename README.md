
# Less Rails Bootstrap Test Project

Simple integration test project for both [less-rails](https://github.com/metaskills/less-rails) and the [less-rails-bootstrap](https://github.com/metaskills/less-rails-bootstrap) gems.


# The Setup

The `Gemfile` for this project has the latest less-rails and less-rails-bootstrap versions specified. It also has optional environment variables so you can specify a source path to a local checkout of each project. 

You can run `rake assets:precompile` to make sure all the stylesheets and javascript manifest files are generated too for production use. The test suite files have their own names, remember that you have to set `config.assets.precompile` in production.rb like so to make this happen. I have already done this here though.

```ruby
config.assets.precompile += [
  'basic.css', 
  'basic_less.css',
  'full_control.css'
]
```

# CSS Tests Suites

A review of our basic CSS test cases and different ways to use less-rails and less-rails-bootstrap.

### Basic Bootstrap

http://less-rails-bootstrap-test.dev/assets/basic.css

Does not get any more simple, require the entire bootstrap code. This does not give you access to any of the variables or mixins, just a final processed file.

```css
/*
 *= require twitter/bootstrap
*/
```

### Basic Less Bootstrap

http://less-rails-bootstrap-test.dev/assets/basic_less.css

Requires a Less file which uses an `@import` to to bring in bootstrap. 

```css
/*
 *= require basic_less/index
*/
```

Unlike using a sprockets manifest, this gives you access to the variables and mixins in the `basic_less/index.css.less` files.

```css
@import "twitter/bootstrap";

#foo {
  .border-radius(4px);
}
```

### Full Control & Customization

http://less-rails-bootstrap-test.dev/assets/full_control.css

This is the end all method for any "I need..." type of request. That could include customizing variables, mixins to anything else. Honestly. Just like the Less method above your main asset manifest requires a delegate Less file.

```css
/*
 *= require full_control/index
*/
```

However, in the full control method it is up to you to [duplicate the imports of the main bootstrap.less file](http://github.com/metaskills/less-rails-bootstrap/blob/master/vendor/frameworks/twitter/bootstrap/bootstrap.less) found in the less-rails-bootstrap gem. If you [look at the full_control/index.css.less](https://github.com/metaskills/less-rails-bootstrap-test/blob/master/app/assets/stylesheets/full_control/index.css.less) file you will see something like this.

```css
@import "twitter/bootstrap/reset";
@import "twitter/bootstrap/variables";
@import "full_control/variables";                 // Your own variable overrides.
@import "twitter/bootstrap/mixins";
@import "full_control/mixins";                    // Your own mixin.
@import "twitter/bootstrap/scaffolding";
...
```

Notice how that file imports the entire bootstrap files and your own in a few key spots? This is how you override things. The `full_control/variables.less` sets the `@linkColor` to `#121212` and it works. You can aso build out your own framework on top of bootstrap using this simple structure too. The possibilities are endless.




