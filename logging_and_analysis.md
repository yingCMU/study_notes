## problems
Current debugging and optimization methods scale poorly to deal with the complexity of modern Internet
services, in which a single request triggers parallel execution of numerous heterogeneous software components
over a distributed set of computers. The Achilles’ heel
of current methods is the need for a complete and accurate model of the system under observation: producing
such a model is challenging because it requires either assimilating the collective knowledge of hundreds of programmers
responsible for the individual components or restricting the ways in which components interact.
### Component relationship
Fundamentally, analyzing the performance of concurrent
systems requires a model of application behavior
that includes the causal relationships between components;
e.g., happens-before ordering and mutual exclusion.
While the techniques for performing such analysis
(e.g., critical path analysis) are well-understood, prior
systems make assumptions about the ease of generating
the causal model that simply do not hold in many large scale,
heterogeneous distributed systems such as the one
we study in this paper.
## Not heterogeneous system:
many systems are like the Facebook systems
we study; they grow organically over time in a
culture that favors innovation over standardization (e.g.,
“move fast and break things” is a well-known Facebook
slogan). There is broad diversity in programming languages,
communication middleware, execution environments,
and scheduling mechanisms. Adding instrumentation
retroactively to such an infrastructure is a Herculean
task. Further, the end-to-end pipeline includes
client software such as Web browsers, and adding detailed
instrumentation to all such software is not feasible
## user-supplied schema
Use define the causal model of application. To obtain a detailed model of endto-
end request processing, one must assemble the collective
knowledge of hundreds of programmers responsible
for the individual components that are involved in
request processing. Further, any such model soon grows
stale due to the constant evolution of the system under
observation, and so constant updating is required.
### Complexity
1. comes partially from scale a single Web request may trigger the execution of hundreds of executable components running in parallel on many different computers.
2. Complexity also arises from heterogeneity. executable components are often written in different languages, communicate through a wide variety of channels, and run in execution environments that range from third-party browsers to open-source middleware to
in-house, custom platforms.

## solution
we develop a technique that generates a
causal model of system behavior without the need to add
substantial new instrumentation or manually generate a
schema of application behavior. Instead, we generate the
model via large-scale reasoning over individual software
component logs. Our key observation is that the sheer
volume of requests handled by modern services allows us
to gather observations of the order in which messages are
logged over a tremendous number of requests. We can
then hypothesize and confirm relationships among those
messages. We demonstrate the efficacy of this technique
with an implementation that analyzes over 1.3 million
Facebook requests to generate a comprehensive model
of end-to-end request processing.
## related papers
Many prior systems assume that one can generate
such a model by comprehensively instrumenting all middleware
for communication, scheduling, and/or synchronization
to record component interactions [1, 3, 13, 18,
22, 24, 28].
Other prior systems rely on a user-supplied schema
that expresses the causal model of application behavior [6, 31].
## reference
This paper -[The Mystery Machine: End-to-end performance analysis of large-scale Internet services](https://www.usenix.org/system/files/conference/osdi14/osdi14-paper-chow.pdf)

[Mining Dependency in Distributed Systems through
Unstructured Logs Analysis](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/Mining20Dependency20in20Distributed20Systems20through20unstructured20logs20analysis.pdf)
