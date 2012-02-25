This plugin shows the bandwidth usage on a given network interface, by
querying the `vnstat` tool.

This is a wildcard plugin, the symbolic link should be named as follows:

vnstat\_interface\_period\_what

* **interface** is the network interface, which should be known in vnstat
  (e.g. _eth0_).
* **period** is either hourly, daily, weekly or monthly
* **what**
  - _rx_   Received
  - _tx_    Transmitted
  - _rxtx_  Show both rx and tx separately
  - _total_ Sum rx and tx and show as one graph

For example, _vnstat\_eth0\_daily\_rxtx_ shows the daily bandwidth usage (in
MB) on eth0, with separate graphs for rx and tx.

Optionally, you can set the estimates flag in the plugin configuration file,
for example:

    [vnstat_eth0_monthly_tx]
      env.estimate 1

This will show the estimate for the total bandwidth usage for the given time
period, similar to the last row in the vnstat output. Note that the estimates
for a single day are not really accurate, generally it's more useful to enable
this for the monthly bandwidth.
