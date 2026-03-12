# AWS High Availability Web Architecture  
### ALB + EC2 + Auto Scaling + CloudWatch Dynamic Scaling

This project demonstrates a **highly available and automatically scaling web architecture on AWS** using Application Load Balancer, EC2 instances, Auto Scaling Groups, and CloudWatch monitoring.

The architecture distributes traffic across multiple EC2 instances and automatically launches additional instances when CPU utilization increases. It also demonstrates failure recovery where traffic is redirected when one instance becomes unavailable.

---

# Project Overview

The system includes:

- Two EC2 web servers
- Application Load Balancer distributing traffic
- Target Group health checks
- Auto Scaling Group managing instance capacity
- CloudWatch alarms triggering dynamic scaling
- CPU stress test to simulate high load

This project shows **traffic distribution, failure handling, and automatic scaling in a cloud environment**.

---

# EC2 Instances Running

Two EC2 instances were launched to host the web servers.

![EC2 Instances](screenshots/ec2_instances_running.jpg)

---

# Two Web Servers Running Without ALB

Each EC2 instance initially serves its own webpage directly through the instance public IP before introducing the load balancer.

![Webservers](screenshots/webservers_without_alb.jpg)

---

# Target Group Configuration

A target group was created to register EC2 instances and configure health checks used by the load balancer.

![Target Group](screenshots/target_group_configuration.jpg)

---

# Target Group Healthy Instances

Both EC2 instances successfully passed health checks and are marked healthy.

![Healthy Instances](screenshots/target_group_healthy_instances.jpg)

---

# Application Load Balancer Configuration

An Application Load Balancer was created to distribute incoming HTTP traffic across the registered EC2 instances.

![ALB Configuration](screenshots/alb_configuration.jpg)

---

# Load Balancing Demonstration

Refreshing the ALB DNS endpoint shows traffic alternating between both EC2 instances.

![Load Balancing](screenshots/alb_load_balancing.jpg)

---

# Instance Failure Simulation

One EC2 instance was stopped to simulate a server failure scenario.

![Failure Simulation](screenshots/instance_failure_simulation.jpg)

---

# Target Group After Instance Stop

The stopped instance is automatically removed from the routing pool.

![Target Group After Stop](screenshots/target_group_after_instance_stop.jpg)

---

# Traffic Redirected to Healthy Server

All incoming traffic is automatically routed to the remaining healthy instance.

![Traffic Redirect](screenshots/traffic_redirect_to_server2.jpg)

---

# Launch Template Configuration

A launch template was created to define the configuration used by the Auto Scaling Group when launching new EC2 instances.

![Launch Template](screenshots/launch_template_configuration.jpg)

---

# Auto Scaling Group Configuration

An Auto Scaling Group was configured to maintain instance availability and manage scaling.

![ASG Configuration](screenshots/autoscaling_group_configuration.jpg)

---

# Dynamic Scaling Policy

Dynamic scaling was configured to automatically scale out when CPU utilization exceeds **40%**.

![Scaling Policy](screenshots/dynamic_scaling_policy_cpu40.jpg)

---

# CloudWatch CPU Alarm

CloudWatch alarms monitor CPU utilization and trigger scaling actions.

![CloudWatch Alarm](screenshots/cloudwatch_cpu_alarm.jpg)

---

# CPU Utilization Spike

A stress test was executed on the EC2 instance to simulate high CPU usage.

![CPU Spike](screenshots/cpu_utilization_spike.jpg)

---

# Auto Scaling Scale Out Activity

When the CPU threshold was exceeded, Auto Scaling launched a new EC2 instance.

![Scaling Activity](screenshots/autoscaling_scale_out_activity.jpg)

---

# New Instance Launched

The Auto Scaling Group successfully added a new EC2 instance to handle increased workload.

![New Instance](screenshots/asg_new_instance_launched.jpg)

---

# Technologies Used

**Amazon EC2**  
Virtual machines used to host the web servers.

**Application Load Balancer (ALB)**  
Distributes incoming traffic across EC2 instances.

**Target Groups**  
Perform health checks and route traffic only to healthy instances.

**Auto Scaling Groups (ASG)**  
Automatically manage the number of EC2 instances based on demand.

**Launch Templates**  
Define instance configuration used by the Auto Scaling Group.

**Amazon CloudWatch**  
Monitors CPU utilization and triggers alarms for scaling.

**Dynamic Scaling Policies**  
Automatically scale out infrastructure when CPU utilization exceeds defined thresholds.

**Linux Stress Tool (`stress`)**  
Used to simulate high CPU load and trigger scaling behavior.

---

# Key Learnings

- Load balancers distribute traffic across multiple servers
- Health checks prevent failed instances from receiving traffic
- Auto Scaling enables infrastructure elasticity
- CloudWatch alarms enable automated infrastructure scaling
- Failure testing validates reliability of cloud architectures

---

# Author

Sahana Ballullaya  
GitHub: https://github.com/sahanaballullaya
