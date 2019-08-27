SSH Tools
-

* [connect-to](connect-to) -- tolerate multiple possible addressing methods for an ssh connection

  `~/.ssh/config`:

  ```
  host somehost
  proxycommand ~/bin/connect-to somehost-wired:22 somehost-wifi:22
  ```

  You can then use `ssh somehost` without worrying about whether the computer is only reachable by `somehost-wired` or `somehost-wifi`. Otherwise, ssh tends to pick only a single of the IP addresses returned by DNS.

  This can be combined with [autossh](https://www.harding.motd.ca/autossh/) to transparently failover between addressable interfaces.
