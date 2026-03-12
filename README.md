# AWS High Availability Web Architecture
### ALB + EC2 + Auto Scaling + CloudWatch Dynamic Scaling

This project demonstrates a highly available AWS architecture using:

- Amazon EC2
- Application Load Balancer (ALB)
- Target Groups
- Auto Scaling Groups
- CloudWatch Alarms
- Dynamic Scaling based on CPU utilization

The architecture distributes traffic across multiple instances and automatically scales infrastructure based on system load.

---

# Architecture Overview

The architecture uses an Application Load Balancer to distribute traffic across EC2 instances managed by an Auto Scaling Group.

If one instance fails or system load increases, traffic is automatically redirected and new instances are launched.

---

# EC2 Instances Running

Two EC2 instances were created to host the web servers.

![EC2 Instances](screenshots/ec2_instances_running.jpg)

---

# Web Servers Running Without Load Balancer

Each EC2 instance serves its own webpage before the load balancer is configured.

![Webservers](screenshots/webservers_without_alb.jpg)

---

# Target Group Configuration

A target group was created to register EC2 instances and perform health checks.

![Target Group Configuration](screenshots/target_group_configuration.jpg)

---

# Target Group Healthy Instances

Both EC2 instances passed the health checks successfully.

![Healthy Instances](screenshots/target_group_healthy_instances.jpg)

---

# Application Load Balancer Configuration

An Application Load Balancer distributes incoming traffic to the target group.

![ALB Configuration](screenshots/alb_configuration.jpg)

---

# Load Balancing Demonstration

Refreshing the ALB DNS endpoint shows traffic alternating between both EC2 instances.

![Load Balancing](screenshots/alb_load_balancing_demo.jpg)

---

# Failure Simulation

One EC2 instance was stopped to simulate infrastructure failure.

![Failure Simulation](screenshots/instance_failure_simulation.jpg)

---

# Target Group After Instance Stop

The stopped instance is no longer used by the load balancer.

![Target Group After Stop](screenshots/target_group_after_instance_stop.jpg)

---

# Traffic Redirected to Healthy Server

All traffic is automatically routed to the remaining healthy instance.

![Traffic Redirect](screenshots/traffic_redirect_to_server2.jpg)

---

# Launch Template Configuration

A launch template was created to define how new EC2 instances are launched by the Auto Scaling Group.

![Launch Template](screenshots/launch_template_configuration.jpg)

---

# Auto Scaling Group Configuration

An Auto Scaling Group manages the EC2 instances and maintains system availability.

![ASG Configuration](screenshots/autoscaling_group_configuration.jpg)

---

# Dynamic Scaling Policy

Dynamic scaling was configured to scale out when CPU utilization exceeds **40%**.

![Scaling Policy](screenshots/dynamic_scaling_policy_cpu40.jpg)

---

# CloudWatch Alarm

CloudWatch monitors CPU utilization and triggers scaling actions.

![CloudWatch Alarm](screenshots/cloudwatch_cpu_alarm.jpg)

---

# CPU Utilization Spike

A stress test was executed on the EC2 instance to increase CPU usage.

![CPU Spike](screenshots/cpu_utilization_spike.jpg)

---

# Auto Scaling Activity

Auto Scaling detects the high CPU load and launches a new EC2 instance.

![Scaling Activity](screenshots/autoscaling_scale_out_activity.jpg)

---

# New Instance Launched

The Auto Scaling Group successfully launched a new EC2 instance to handle increased traffic.

![New Instance](screenshots/asg_new_instance_launched.jpg)

---

# Key Learnings

This project demonstrates key cloud infrastructure principles:

- Load balancing improves application availability
- Health checks ensure traffic reaches only healthy instances
- Auto Scaling enables infrastructure elasticity
- CloudWatch alarms allow automated scaling decisions
- Fault tolerance ensures minimal service disruption

---

# Technologies Used

- Amazon EC2
- Application Load Balancer
- Target Groups
- Auto Scaling Groups
- AWS CloudWatch

---

# Author

Sahana Ballullaya  
GitHub: https://github.com/sahanaballullaya
