# AWS ALB + Auto Scaling Demo

This project demonstrates a highly available AWS web architecture using:

- EC2 instances
- Application Load Balancer (ALB)
- Target Groups
- Auto Scaling Groups
- CloudWatch dynamic scaling

The architecture distributes traffic across EC2 instances and automatically scales based on CPU utilization.

---

## EC2 Instances Running

![EC2 Instances](screenshots/ec2_instances_running.jpg)

---

## Two Web Servers Running Without ALB

![Webservers](screenshots/webservers_without_alb.jpg)

---

## Target Group Configuration

![Target Group](screenshots/target_group_configuration.jpg)

---

## Target Group Healthy Instances

![Healthy Instances](screenshots/target_group_healthy_instances.jpg)

---

## Application Load Balancer Configuration

![ALB Configuration](screenshots/alb_configuration.jpg)

---

## Load Balancing Demonstration

![Load Balancing](screenshots/alb_load_balancing_demo.jpg)

---

## Instance Failure Simulation

![Failure Simulation](screenshots/instance_failure_simulation.jpg)

---

## Target Group After Instance Stop

![Target Group After Stop](screenshots/target_group_after_instance_stop.jpg)

---

## Traffic Redirected to Healthy Instance

![Traffic Redirect](screenshots/traffic_redirect_to_server2.jpg)

---

## Launch Template Configuration

![Launch Template](screenshots/launch_template_configuration.jpg)

---

## Auto Scaling Group Configuration

![ASG Configuration](screenshots/autoscaling_group_configuration.jpg)

---

## Dynamic Scaling Policy

![Scaling Policy](screenshots/dynamic_scaling_policy_cpu40.jpg)

---

## CloudWatch CPU Alarm

![CloudWatch Alarm](screenshots/cloudwatch_cpu_alarm.jpg)

---

## CPU Utilization Spike

![CPU Spike](screenshots/cpu_utilization_spike.jpg)

---

## Auto Scaling Scale Out Activity

![Scaling Activity](screenshots/autoscaling_scale_out_activity.jpg)

---

## New Instance Launched

![New Instance](screenshots/asg_new_instance_launched.jpg)

---

## Key Learnings

- Application Load Balancer distributes traffic across EC2 instances.
- Target group health checks ensure only healthy instances receive traffic.
- Auto Scaling maintains system availability.
- CloudWatch alarms trigger dynamic scaling based on CPU utilization.
