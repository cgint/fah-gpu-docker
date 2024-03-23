# Example Config Files
The config options used for running the client in containers are slightly different than the ones used in a standalone install. These are the interesting ones:

- user, passkey, team - user and team. Set them to your values.
- exit-when-done - have container exit once a finish is sent to it.
- power - run 100% of the time but idle priority.
- web-enable, disable-viz, gui-enabled - disable unnecessary things.
- slots ... - SMP and GPU slots. Each GPU slot also takes 1 CPU core. Each SMP slot can be set to use N cores. The "cpus" tag can be left out on 1-cpu low core count machines and it will autoconfig.