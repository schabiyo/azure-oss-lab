# AzureOSSDemos : A series of demos showcasing OSS on Azure 

Concourse is used as Pipeline to automate the deployment of the demos. If you are not familir with Concourse (http://concourse.ci), do not worry, the actual demo scripts
has no dependency with concource and can be ran using your favorite CICD pipeline tool. Some parts of these demos are based on the Skylab project by Microsoft that can be found here:
https://blogs.technet.microsoft.com/msuspartner/2017/04/13/open-source-partners-open-source-demos-microsoft-azure/

My pipelines are hosted here if you want to take look: http://ci.syolab.io/

Follow the instruction on that page for a manual deployment.


## Table of contents

* [01 - Environment setup](jumpbox.md)



![Boostrap](/docs/Utility1.PNG "Boostrap")

A second pipeline existe as well to unprovision the envionment. More details on the environment provision/unprovision HERE

* [02- DevOps pipeline](demo1.md)
* [03- demo2](demo2.md)



## Getting started

Install Vagrant/Virtualbox.

Fetch this tutorial and start a local Concourse server:

```
git clone https://github.com/schabiyo/azure-oss-demos.git
cd azure-oss-demos
vagrant box add concourse/lite --box-version $(cat VERSION)
vagrant up
```

Open http://192.168.100.5:8080/ in your browser:


Target Concourse
----------------

In the spirit of declaring absolutely everything you do to get absolutely the same result every time, the `fly` CLI requires that you specify the target API for every `fly` request.

First, alias it with a name `ossdemos` (you can pick whatener name yopu want):

```
fly --target ossdemos login -c http://192.168.100.5:8080
fly --target ossdemos sync
```


If you found this guide lacking please submit an issue or PR through github. We appreciate your feedback.

