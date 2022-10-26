# Using eBPF superpower

### k8s security policies

Different kindws of policies:

1. Seccomp
2. Pod capabilities
3. Network policies

hard problem: which sys calls should it perform, which linux cap. does it need, which network endpoints does it comm. with.

### generating security policies

Observe the application and use this data to generate policies.

1. eBPF allows capture the activity of an app
 - Low overhead
 - Great flexibility

2. Generate a policy (can be easy or very hard)

Seccomp

1. Linux kernal mech. to limit sys calls.
2. Defines a list of syscalls and an action for them:
   - Kill, Trap, Errno, Log

SPO (security profiles operator)

1. tool to handle sec profiles in k8s
2. Provides seccompProfile custom resource
    - saves profile on nodes to be referenced in pod spec.

Defining Seccomp profiles

1. an allow-list is preferred
   - more secure
   - Must include all sys calls needed by the application

2. how to know which syscalls are needed?
   - Analyze the code
   - use strace
   - define a profile with `SCMP_ACT_LOG` and check the audit log
   - use a tool that records the syscalls performed in a container

you can use [inspektor-gadget](https://github.com/inspektor-gadget/inspektor-gadget) advise seccomp-profile tool.

### auditing security policies

1. could use defaultAction: SCMP_ACT_LOG
2. or, you can use inspektor_gadget to audit instead.

### What about linux capabilities

1. It's possible to give a process only some privileges.
2. CAP_CHOWN, CAP_NET_BIN_SERVICE, CAP_SYS_BOOT, many more.
3. In k8s the container runtime grants some capabilities by default.
4. Others can be added / dropped.

### Network policies

1. Operate at IP or port level 
2. Usually defined when designing the architecture.
3. In some cases, those are defined afterwards.

Inspektor gadget advise is really neat: https://github.com/inspektor-gadget/inspektor-gadget/tree/a219c9c29c67d07e41b36bd762d8330915f554db/docs/guides/advise