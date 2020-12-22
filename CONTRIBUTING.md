# Contributing

**k8s-jsonpath** is a **GPL GNU3** Licensed project and uses the standard GitHub pull requests process to review and accept contributions.

There are several areas of **k8s-jsonpath** that you could help the project to contribute. This is just in the initial state of the project and together **WE** can make it large.

- If you are a first-time contributor, please see [Steps to Contribute](#steps-to-contribute).
- If you would like to suggest features to be added to **k8s-jsonpath**, please go ahead and [create a new issue](https://github.com/himadriganguly/k8s-jsonpath/issues/new) describing your requirement and why you think that it will be need on this project.
- If you would like to make code contributions, all your commits should be signed with **Developer Certificate of Origin**. See [Sign your work](#sign-your-work).

## Steps to Contribute

**K8s is required.**

0. Clone the git repository and enter into the folder

```
git clone https://github.com/himadriganguly/k8s-jsonpath.git
cd k8s-jsonpath
```

1. Add jsonpath code in the **jsonpath.md** file on the respective folder, such as if it is related to **nodes** then the code will be under **nodes** folder.

2. The code should be in the following format

- Serial number should be there
- Description of the code and the K8s version
- Then the code under code block
- And also the output

`Note:- The minimum version of K8s should be v1.19.0`

**Example**

````
1. Get the name of all the nodes and their taint effect if any. <br/>**K8s** version used - **v1.19.5**

<details>
  <summary>Click to expand!</summary>

```shell
kubectl get nodes -o jsonpath='{range $.items[*]} {.metadata.name} {.spec.taints[*].effect}{"\n"}'
```

**Output**
```shell
kubemaster NoSchedule
kubenode01
kubenode02
```

</details>
````

3. Create a new branch `git checkout -b MY_BRANCH_NAME`

- Find an issue to work on or create a new issue. The issues are maintained at [k8s-jsonpath](https://github.com/himadriganguly/k8s-jsonpath/issues). You can pick up from a list of [good-first-issues](https://github.com/himadriganguly/k8s-jsonpath/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22).
- Claim your issue by commenting your intent to work on it to avoid duplication of efforts.
- Fork the repository on **GitHub**.
- Create a branch from where you want to base your work (usually master).
- Make your changes.
- Commit your changes by making sure the commit messages convey the need and notes about the commit.
- Push your changes to the branch in your fork of the repository.
- Submit a pull request to the original repository. See [Pull Request checklist](#pull-request-checklist)

## Pull Request Checklist

- Rebase to the current master branch before submitting your pull request.
- Commits should be as small as possible. Each commit should follow the checklist below:

  - Commit header (first line) should convey what changed
  - Commit body should include details such as why the changes are required and how the proposed changes
  - **DCO** Signed

## Sign your work

We use the **Developer Certificate of Origin** (**DCO**) as an additional safeguard for the **k8s-jsonpath** project. This is a well established and widely used mechanism to assure that contributors have confirmed their right to license their contribution under the project's license. Please add a line to every git commit message:

```
  Signed-off-by: Random Developer <random@developer.example.org>
```

Use your real name (sorry, no pseudonyms or anonymous contributions). The email id should match the email id provided in your **GitHub profile**.

If you set your `user.name` and `user.email` in **git config**, you can sign your commit automatically with `git commit -s`.

You can also use git [aliases](https://git-scm.com/book/tr/v2/Git-Basics-Git-Aliases) like `git config --global alias.ci 'commit -s'`. Now you can commit with `git ci` and the commit will be signed.
