# Command help from FAHClient
## Created with
`docker run --rm foldingathome/fah-gpu:latest --help > command_help.md`

## Output
```
Usage: /usr/bin/FAHClient [[--config] <filename>] [OPTIONS]...

OPTIONS:
  --chdir <string>
      Change directory before starting server. All files opened after this
      point, such as the configuration file, must have paths relative to the new
      directory.

  --configure
      Create a basic configuration file, then exit.

  --dump <string>
      Dump either 'all' or a specific work unit, identified by its queue ID,
      then exit.

  --finish
      Finish all current work units, send the results, then exit.

  --lspci
      List the PCI bus devices, which can be helpful for finding GPU vendor and
      device IDs.

  --queue-info
      Print work unit queue then exit.

  --send
      Send all finished work units, then exit.

  --send-command <string>
      Send a command to an already running client.

  --send-finish [string]
      Finish a slot or all slots on an already running client.

  --send-pause [string]
      Pause a slot or all slots on an already running client.

  --send-unpause [string]
      Unpause a slot or all slots on an already running client.

Configuration:
  --config <string=config.xml>
      Set configuration file.

  --print
      Print configuration and exit.

Informational:
  --help [string]
      Print help screen or help on a particular option and exit.

  --html-help
      Print help in HTML format and exit.

  --info
      Print application and system information and exit.

  --license
      License information and exit.

  -q|--quiet
      Set verbosity to zero.

  -v|--verbose
      Increase verbosity level.

  --version
      Print application version and exit.


Configuration options:
The following options can be specified in a configuration file or on the command
line using the following syntax:

    --<option> <value>

  or:

    --<option>=<value>

  or when marking boolean values true:

    --<option>

Client Control:
  client-threads <integer=6>
    The number of client processing threads.

  cycle-rate <double=4>
    The maximum cycle frequency in Hz of client threads.

  cycles <integer=-1>
    Run at most this many cycles. A value less than zero means run indefinitely.

  disable-sleep-when-active <boolean=true>
    Attempt to keep the system from sleeping when folding, unless on battery.

  exit-when-done <boolean=false>
    Exit when all slots are paused.

  fold-anon <boolean=false>
    Start folding even if not configured.

  idle-seconds <integer=300>
    Number of seconds of system idle time before enabling idle folding. Set to
    zero to ignore system idle time.

  open-web-control <boolean=false>
    Make an operating system specific call to open the Web Control in a browser
    once client is fully loaded

Configuration:
  config-rotate <boolean=true>
    Rotate the configuration file to a backup when saving would overwrite the
    previous configuration.

  config-rotate-dir <string=configs>
    Put rotated configs in this directory.

  config-rotate-max <integer=16>
    The maximum number of rotated configuration files to keep. A value of zero
    will keep all configuration file backups.

Error Handling:
  max-slot-errors <integer=10>
    The maximum number of errors before a slot is paused.

  max-unit-errors <integer=5>
    The maximum number of errors before a work unit is dumped.

Folding Core:
  checkpoint <integer=15>
    Tell cores to checkpoint at least every # minutes.

  core-priority <string=idle>
    Set the core priority. Valid values are: idle or low

  cpu-usage <integer=100>
    The maximum percentage of the CPU a core should use. Not implemented by all
    cores.

  gpu-usage <integer=100>
    GPU usage as a percent from 10-100

  no-assembly <boolean=false>
    Tell cores to disable optimized assembly code.

Folding Slot Configuration:
  cause <string=ANY>
    The cause you prefer to support.

  client-subtype <string=LINUX>
    The client subtype

  client-type <string=normal>
    The client type. Can be 'normal', 'advanced' or 'beta'.

  cpu-species <string=X86_AMD>
    CPU species.

  cpu-type <string=AMD64>
    CPU type.

  cpus <integer=-1>
    How many CPUs a slot should use. <= 0 will use all the CPUs detected in the
    system.

  cuda-index <integer>
    CUDA device index

  disable-viz <boolean=false>
    Disable reading visualization data.

  extra-core-args <string>
    Pass extra arguments to the core.

  gpu <boolean=true>
    Enable or disable auto-confiugration of GPU slots, requires appropriate
    hardware.

  gpu-beta <boolean=false>
    Enable beta GPUs

  gpu-index <string>
    The index of the GPU in the order detected by the operating system.

  max-packet-size <string=normal>
    Max size in bytes of a work unit packet. Can be small=5MiB, normal=25MiB,
    big=500MiB or a number.

  memory <string>
    Override memory, in bytes, reported to Folding@home.

  opencl-index <integer>
    OpenCL device index

  os-species <string=UNKNOWN>
    Operating system species.

  os-type <string=LINUX>
    Operating system type.

  pci-bus <string>
    The GPUs PCI bus ID.

  pci-slot <string>
    The GPUs PCI slot ID.

  project-key <integer=0>
    Key for access to restricted testing projects.

  smp <boolean=true>
    Enable or disable auto-configuration of SMP slots, requires appropriate
    hardware.

GUI:
  gui-enabled <boolean=true>
    Set to false to disable the GUI. A GUI is not currently supported on all
    operating systems.

HTTP Server:
  allow <string=127.0.0.1>
    Client addresses which are allowed to connect to this server. This option
    overrides IPs which are denied in the deny option. The pattern 0/0 matches
    all addresses.

  connection-timeout <integer=60>
    The maximum amount of time, in seconds, a connection can be idle before
    being dropped.

  deny <string=0/0>
    Client address which are not allowed to connect to this server.

  http-addresses <string=0:7396>
    A space separated list of server address and port pairs to listen on in the
    form <ip | hostname>[:<port>]

  https-addresses <string=>
    A space separated list of secure server address and port pairs to listen on
    in the form <ip | hostname>[:<port>]

  max-connect-time <integer=900>
    The maximum amount of time, in seconds, a client can be connected to the
    server.

  max-connections <integer=800>
    Sets the maximum number of simultaneous connections.

  max-request-length <integer=52428800>
    Sets the maximum length of a client request packet.

  min-connect-time <integer=300>
    The minimum amount of time, in seconds, a client must be connected to the
    server before it can be dropped in favor or a new connection.

HTTP Server SSL:
  certificate-file <string>
    The servers certificate file in PEM format.

  crl-file <string>
    Supply a Certificate Revocation List. Overrides any internal CRL

  private-key-file <string>
    The servers private key file in PEM format.

Logging:
  log <string=log.txt>
    Set log file.

  log-color <boolean=true>
    Print log messages with ANSI color coding.

  log-crlf <boolean=false>
    Print carriage return and line feed at end of log lines.

  log-date <boolean=false>
    Print date information with log entries.

  log-date-periodically <integer=21600>
    Print date to log before new log entries if so many seconds have passed
    since the last date was printed.

  log-domain <boolean=false>
    Print domain information with log entries.

  log-domain-levels <string ...>
    Set log levels by domain. Format is:
      <domain>[:i|d|t]:<level> ...
    Entries are separated by white-space and or commas.
      i - info
    For example: server:i:3 module:6
    Set 'server' domain info messages to level 3 and 'module' info messages to
    level 6. All other domains will follow the system wide log verbosity level.
    If <level> is negative it is relative to the system wide verbosity.

  log-header <boolean=true>
    Enable log message headers.

  log-level <boolean=true>
    Print level information with log entries.

  log-no-info-header <boolean=true>
    Don't print 'INFO(#):' in header.

  log-redirect <boolean=false>
    Redirect all output to log file. Implies !log-to-screen.

  log-rotate <boolean=true>
    Rotate log files on each run.

  log-rotate-dir <string=logs>
    Put rotated logs in this directory.

  log-rotate-max <integer=16>
    Maximum number of rotated logs to keep.

  log-short-level <boolean=false>
    Print shortened level information with log entries.

  log-simple-domains <boolean=true>
    Remove any leading directories and trailing file extensions from domains so
    that source code file names can be easily used as log domains.

  log-thread-id <boolean=false>
    Print id with log entries.

  log-thread-prefix <boolean=true>
    Print thread prefixes, if set, with log entries.

  log-time <boolean=true>
    Print time information with log entries.

  log-to-screen <boolean=true>
    Log to screen.

  log-truncate <boolean=false>
    Truncate log file.

  verbosity <integer=3>
    Set logging level for INFO messages.

Network:
  proxy <string=>
    Set proxy for outgoing HTTP connections

  proxy-enable <boolean=false>
    Enable proxy configuration

  proxy-pass <string=>
    Set password for proxy connections

  proxy-user <string=>
    Set user name for proxy connections

Process Control:
  child <boolean=false>
    Disable 'daemon', 'fork', 'pid' and 'respawn' options. Also defaults
    'log-to-screen' to false. Used internally.

  daemon <boolean=false>
    Short for --pid --service --respawn --log='' --fork

  fork <boolean=false>
    Run in background.

  pid <boolean=false>
    Create PID file.

  pid-file <string=FAHClient.pid>
    Name of PID file.

  priority <string>
    Set the process priority. Valid values are: idle, low, normal, high or
    realtime.

  respawn <boolean=false>
    Run the application as a child process and respawn if it is killed or exits.

  run-as <string>
    Run as specified user

  service <boolean=false>
    Ignore user logout or hangup and interrupt signals

  set-group <string>
    Run in specified group

Remote Command Server:
  command-address <string=0.0.0.0>
    The address to which the command server should be bound.

  command-allow-no-pass <string=127.0.0.1>
    IP address ranges that are allowed access to the command server with out a
    password if the 'password' option is set. These addresses will also have to
    be allowed IP based access.

  command-deny-no-pass <string=0/0>
    IP address ranges that are not allowed access to the command server with out
    a password if the 'password' option is set. Overridden by
    command-allow-no-pass

  command-enable <boolean=true>
    Set to false to disable the command server.

  command-port <integer=36330>
    The port to which the command server should be bound.

  password <string>
    Set a command server password. Warning, setting a password disables the
    default IP address blocking.

Slot Control:
  auto-conf <boolean=true>
    Enable/disable auto configuration of folding slots.

  idle <boolean=false>
    Only run slot when idle.

  max-shutdown-wait <integer=60>
    The maximum amount of time to wait in seconds for a unit to exit on
    shutdown.

  pause-on-battery <boolean=true>
    Pause the client or slot when the OS indicates the machine is running on
    battery power.

  pause-on-start <boolean=false>
    If true the slot will be started in a paused state.

  paused <boolean=false>
    True if slot is paused.

  power <string=medium>
    Set the client's power level. Valid values are 'light', 'medium' or 'full'.
    This setting affects the defaults of several other options such as 'cpus',
    'pause-on-battery', etc.

User Information:
  machine-id <integer=0>
    The machine ID.

  passkey <string=>
    Your passkey.

  team <integer=0>
    Your team number.

  user <string=Anonymous>
    Your user name.

Web Server:
  web-allow <string=127.0.0.1>
    Client addresses which are allowed to connect to this Web server. This
    option overrides IPs which are denied in the web-deny option. This option
    differs from the 'allow'/'deny' options in that clients that are not allowed
    are served an access denied page rather than simply dropping the connection.
    The value '0/0' matches all IPs.

  web-deny <string=0/0>
    Client address which are not allowed to connect to this Web server.

  web-enable <boolean=true>
    Set to false to disable the web server.

Web Server Sessions:
  session-cookie <string=sid>
    The name of the session cookie.

  session-lifetime <integer=86400>
    The maximum session lifetime in seconds. Zero for unlimited session
    lifetime.

  session-timeout <integer=3600>
    The max maximum amount of time in seconds since the last time a session was
    used before it timesout. Zero for no session timeout.

Work Unit Control:
  dump-after-deadline <boolean=true>
    Dump units if their deadline has passed.

  max-queue <integer=16>
    Maximum units per slot in the work queue.

  max-units <integer=0>
    Process at most this number of units, then pause.

  next-unit-percentage <integer=99>
    Pre-download the next work unit when the current one is this far along.
    Values less than 90 are not allowed.

  stall-detection-enabled <boolean=false>
    Attempt to detect stalled work units and restart them.

  stall-percent <integer=5>
    Minimum estimated percent work unit completion since last frame before a WU
    can be considered stalled, if zero the percentage is ignored.

  stall-timeout <integer=1800>
    Minimum time, in seconds, since last frame before a WU can be considered
    stalled.
```