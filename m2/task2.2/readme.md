# TASK2.2
## Workflow:


<details>
<summary>Review the 10-minute example. Launch a Linux Virtual Machinewith Amazon Lightsail. Repeat, create your own VM in the AWS cloud and connect to it. </summary>
<br>
Launched a CentOS VM by tutorial, connected by SSh.
 
 ![Screen1](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m2/task2.2/screenshots/Screenshot_1.png)
</details>

<details>
<summary>Launch anotherLinux Virtual MachinewithoutAmazon Lightsail.It is recommended to use the t2or t3.micro instance and the CentOS operating system.</summary>
<br>
Launched a CentOS VM by on t2.micro instance in us-east-2 region. Checked connection by SSH.
 
 ![Screen2](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m2/task2.2/screenshots/Screenshot_2.png)
</details>

<details>
<summary>Create and attach a Disk_D (EBS)to your instance to add more storage space.Create and save some file on Disk_D.</summary>
<br>
Created another volume on EBS, attached to instance and uploaded an image.
 
 ![Screen3](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m2/task2.2/screenshots/Screenshot_3.png)
</details>

<details>
<summary>Launch the third instance from backup.Detach Disk_D from the 2nd instance and attach disk_D to the new instance.</summary>
<br>
Created AMI from backup snapshot, launched an instance. Detach from firs instance and attached to new one.
 
 ![Screen4](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m2/task2.2/screenshots/Screenshot_4.png)
</details>

<details>
<summary>Launch and configure a WordPress instancewith Amazon Lightsail</summary>
<br>
Launched anothe WordPress instance on Lighsail.
 
 ![Screen5](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m2/task2.2/screenshots/Screenshot_5.png)
</details>

<details>
<summary>Review the 10-minute exampleStore and Retrieve a File. Repeat, creating your own repository.Review the 10-minute exampleBatch upload files to the cloudto Amazon S3 using the AWS CLI.Create a user AWS IAM, configure CLI AWS and upload any files to S3. </summary>
<br>
Created an S3 repository, uploaded an image of cat to directory on new repo.
 
 ![Screen6](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m2/task2.2/screenshots/Screenshot_6.png)
 ![Screen7](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m2/task2.2/screenshots/Screenshot_7.png)
</details>

<details>
<summary>Review   the   10-minute exampleDeploy   Docker   Containers   on   Amazon   Elastic Container Service (Amazon ECS). Repeat, create a cluster, and run the online demo applicationor better otherapplicationwith custom settings.</summary>
<br>
Created an ECS cluster, made a Docker image, uploaded to cluster. Created a task definition, run a task on cluster instance.
 
 ![Screen9](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m2/task2.2/screenshots/Screenshot_9.png)
 ![Screen8](https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4/blob/main/m2/task2.2/screenshots/Screenshot_8.png)
</details>

<details>
<summary>Create a static website on Amazon S3, publicly available</summary>
<br>
Created an S3 bucket for static website, uploaded index.html and myself picture.
 
[Link to website][website-S3-url] with picture and lists of used AWS services and completed labs.
</details>


[//]: #
[git-repo-url]: <https://github.com/wrldwde/DevOps_online_Kharkiv_2021Q4>
[website-S3-url]: <http://wrldwde.pp.ua.s3-website.us-east-2.amazonaws.com>
