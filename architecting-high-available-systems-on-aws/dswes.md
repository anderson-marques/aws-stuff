# Durable Storage with EBS and S3

## Types of VM storage

- File storage (local)
    - Exposed via distributed file system protocol
    - Clients access data through OS at file system level
    - Synonymous with NAS
- Block storage
    - Exposed via low level bus interface accessible over network
    - clients access through OS at device level
    - Synonymous with SAN
- Object storage
    - Exposed via HTTP interface
    - Client access at user level

## What type to use in a distributed cloud system?
- Use file storage via EC2 when...
    - Wnat lots of cheap, temporary storage
    - Great for duplicated web servers
- Use block storage via EBS when...
    - Need consistent, reliable off-instance storage for frequently changing data
    - Ideal for primary DB storage
- Use object storage via S3 when...
    - Looking for high durable, shared data
    - Perfect for static content used by web applications

# Amazon EBS

- Unformatted block storage volumes
- Tied to single AZ, and single instance
- Can be used as boot partition
- Good durability, but failures can occurs

## EBS High Availability 
- Create EBS snapshots periodically and put then on S3
- In case of faillure, recover the Snapshot to another AZ (Availability Zone)
- Use more de one volume per instance. In case one fail, use the next, and so on...
- In case of problem is on the instance. Just replace for another one and attach the same data volumes.

## EBS best practices
- Architect for additional availability
    - Snapshots
    - Cross AZ replication
    - RAID with volumes
- Maximize performance
    - Use provisioned IOPS vs standard EBS
    - Mix and match different volume types
    - Provision 1TB for more consistent performance
- Monitor performance
    - CloudWatch service
    - Status checks
    - Volume events

# Amazon S3
- Scalable, durable, abailable object storage
    - Consistent performance
    - Multi-server access
- Write, read, delete objects up to 5TB each
    - 11 9's of durability. 99,9999999
    - Versioning supported
- Can be accessed by multiples servers via HTTP
- Data replication accross AZ in a region
- Flat organization structure of "buckets" and "objects"

## S3 High Availability
- Replicate data between regions for higher availability

## S3 Best Practices
- Use muilti-part uploads for objects larger than 100MB
- Built-in management capabilities
    - Lifecycle policies
    - Logging
    - Object versioning
- Use reduced Storage for easily recreated data
- Consider and plan for naming restrictions
    - Uniqueness
    - Characters
    - Structure

#
## [Goback...](./index.md)