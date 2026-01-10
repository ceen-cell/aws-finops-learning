# Identity and Access Management. 

Identity and Access Management in AWS is how I manage who has access to an AWS environment and what resources they have access to
and the level of function they can have while using that resource. 

### Users and Groups 
Users are the individual people within the AWS environment.
Lets say we have five users in Company XYX i.e Polly, Kelvin, Mina, Amanda, Michael 

### Groups 
- Polly and Mina are in the Operations team
- Kelvin and Michael are Developers
- Amanda does not belong to any team.
- Mina and Miachael are also in the Management team.

- So for these people to work in AWS, I can give them what we call permisions which will allow them access to the resources they need for their
work.
- These permissions are called **Policies**- JSON documents that contain statements that describe what actions a user is able to perform, 
and on what resources. 
- So I could give policies to the groups within company XYX. So we'd have policies for the Developers, Operations Team, and the Management.
- Since Amanda has no group she will have what we call an **Inline Permission**

  ### FIN-OPS BENEFIT
  - The use of policies to manage access within AWS prevents the users from launching resources that they do not need.
  - Resources in AWS cost money so if a user launches instances they don't need, company XYX's cost optimization efforts will be counterbeneficial. 
  - To enforce this I make use of the **Least Privilage Principle**.
  - As such, I give the users access to what and only what they need to use.
 
  ## MFA
  - Multi Factor Authentication.
  - This is a multi step process in securing access to an AWS acount especially the root account since it is where all changes can be effected without
    a need for Admin permissions. i.e the root account is the mother of all other accounts.
  - So in MFA, you use : A password you know + A device you own.
  - E.g I could use a password plus an authentification software on my phone that would give me a code or pin I can use to get access to my account.
 
  ### FIN-OPS BENEFIT
  - Having MFA on accounts helps prevent unauthorised users from having access to company XYX's AWS account to either steal data or launch 
  resources intentionally which could be detrimental to XYX's cost. A company can try to put a ccompetitor out of busniess and breaching an account
  can help them launch resources that can drain their money.

## ACCESSING AWS 
- I can access AWS enviornment with a non root user account either through :
  1. Management Console
  2. CLI (Command Line Interface)
  3. SDK (Software Developer Kit)
 
 - To use CLI or SDK I will have to go into the AWS console and create an access key.


### IAM Roles 
- This is akin to giving a human like feature to a non human thing say in a movie/story. i.e personification
- Here, it entails me giving AWS services the permissions, I would have otherwise given a real user, so they can perform actions on
 my behalf.
- E.g EC2 roles, lambda function rols, Cloudformstion roles.

## IAM SECURITY TOOLS
1. Credentials Report ---> Detailed report of which users are in the system and what security they have i.e info on passwords, MFA. 
2. Access Advisor ---> users and what resources thay have acces to and when it was last used. Beneficial for cost optimization. 
