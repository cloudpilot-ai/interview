# Distributed Scheduling

Please write a design document about distributed scheduling and impeachment it.

Evaluation aspects:
- Learning ability
- Depth of thinking on single-point issues
- Hands-on ability

## Background

In all cloud providers, like AWS, Google, and others, there are many spot instances. They are quite cheap (10% of the on-demand instances' price), but after you buy them, they could be terminated with only two minutes' notice (in most scenarios, we don't set PDB, and we should perform the graceful drain).

So I want you to design a way to maximize the use of spot instances without service interruption, to cut costs, by distributed scheduling(on-demand/spot mixed or other ways for one workload). Because all spot instances being terminated at the same time could cause interruptions for different kinds of workloads (single replica workload, multiple replica workload).

Also, I don't want to change the scheduler of the K8s cluster and want to ensure the minimal components necessary in the cluster.

Notes:
> 1. On demand nodes has label: node.kubernetes.io/capacity: on-demand.
> 2. Spot node has label: node.kubernetes.io/capacity: spot.
> 3. Workloads represented as Deployments and StatefulSets.

## Output

- A rough design document (English)
- An easy implementation (After talking to the interviewer)