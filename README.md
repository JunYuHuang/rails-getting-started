# README

TODO

## `Fly.io` Deployment Notes

- Ensure the Rails' Puma server is configured to listen any IP address on port 3000. For example, add the line
```ruby
bind 'tcp 0.0.0.0:3000'
```
in the `/config/puma.rb` file before running `fly deploy`. If the address and port has already been binded once on the Fly VM, do not bind it again (i.e. by commenting that line out) or the VM will suspend.

- Update all dependent Gem versions via the `Gemfile.lock` file by running
```bash
bundle update
```
in the terminal.
