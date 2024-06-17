# keda
Feature / Capability	KEDA	Standard HPA
Scaling to 0 Initial Pods	✔️ Supports minReplicaCount: 0	❌ Minimum minReplicas requirement
Custom Metrics	✔️ Supports a wide range of custom metrics	✔️ Supports CPU and custom metrics
Event-driven Autoscaling	✔️ Can scale based on events	❌ Relies on metrics from running pods
External Metrics	✔️ Integrates with external metrics	❌ Primarily uses Kubernetes native metrics
Scaling Triggers	✔️ Supports various triggers (e.g., cron, external)	❌ Limited to CPU, memory, custom metrics
Use Cases	🚀 Suitable for event-driven workloads, bursty traffic	📊 Best for predictable workload patterns
Minimum Pod Limit	✔️ Can scale down to 0 pods	❌ Requires at least one pod for metrics
Scaling Flexibility	🔄 Offers more flexibility in scaling logic	🔍 Limited to predefined scaling policies
