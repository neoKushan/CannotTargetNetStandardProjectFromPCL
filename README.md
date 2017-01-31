# CannotTargetNetStandardProjectFromPCL
There's a bug/issue in VS2017 that prevents a PCL targeting netstandard from targeting a Netstandard project in the same solution

# Overview

In this solution we have two projects. One of the projects is a PCL that has been made to target the Netstandard (By clicking the "Target Netstandard" button), as shown here:

![](Images\PCLTargetingNetStandard.png)

The other project is a simple Netstandard class library:

![](Images\NetStandardClassLibraryTargetingNetStandard.png)

As you can see, both projects are targeting the same version of the Netstandard (1.4).

It's my understanding that this PCL library should be able to consume Netstandard libraries as a result of targeting the Netstandard profile. Unfortunately, this is what happens:

![](Images\error.png)

You can clone this repoistory to look at an example solution. 

# Steps to reproduce:

1. Create a new, empty solution containing a PCL targeting the profile of your choice

![](Images\Step1a.png)

![](Images\Step1b.png)

2. Retarget the PCL to to use the Netstandard

 ![](Images\Step2.png)

3. Add a new Netstandard library to the solution

![](Images\Step3.png)

4. Ensure Both projects are targeting the same Netstandard version (Or that the PortableClassLibrary is targeting a Netstandard higher than the Netstandard project)

![](Images\Step4a.png)

![](Images\Step4b.png)

5. Try to reference the Netstandard project from the PCL

![](Images\Step5a.png)

![](Images\error.png)





