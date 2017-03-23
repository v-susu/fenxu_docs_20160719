# Service rollback options for new deployment bits
Due to the high rate of LSI happening after each deployments, operation team wants to know if there's a way that can quickly work around the issue due to this time's deployment. So they can unblock partner immediatly and leave the investigation to OPS team later.

# Options of rollback
## Rollback by using last version of build tool
OPS provide a mechanism that using different version of build tool to build content. Every deployment will generate a new version of build tool. Sometimes the latest version of build tool may have bug so we can try to use older one to unblock partners.  
The following steps is letting you to decide whether this rollback way can work.
1. Create a new branch on the failed repository. If you don't have permission, you can fork the repository to your own and provision that, then you can do the next step.
2. Set [package_version](../partnerdocs/publish-configuration.md) in publish configuration file with specified version number.
3. Check build results, if it is OK and can unblock partners, merge it to the corresponding failed branch.

> [!NOTE]
> Build team will add the build tool version information in deployment notification in the future.

## Rollback by turnning off some feature flags 
To add some new feature with risk, OPS may add some feature flags to controller that. Sometimes the flags are on repositories and sometimes they are global configured.  
If you find the error message that is obviously related to some new feature, you can try to turn that feature flags off either on modifying [Publish configuration 


## How to figure out the root cause of the issue
If you find a repository build/publish is failed. You can follow the following ways to figure out if the issue is related to build tool.

### Offline way
1. Clone the failed repository to your local.
2. Run local build.

- If local build is failed, then it should be build tool issues, for this issue, please follow [Rollback with build tool issues](#rollback-with-build-tool-issues) to fix the issue.

### Online way
If local build is succeed, it doesn't directly mean the issue is related to build service, because usually local build input paramters is different with that on service. So if possible, please do the following things to see if the issue is realted to build tool.
1. Create a new branch on the failed repository. If you don't have permission, you can fork the repository to your own and provision that, then you can do the next step.
2. Using the way of [Rollback by using last version of build tool](#Rollback-by-using-last-version-of-build-tool) on the new created branch. If you the build can pass on newly created branch with specified build tool version. Then mostly it will be related to

please check the build error to see if it is related to some new feature deployment. If yes, check if there's related feature flag to turn this feature off.


## Rollback by using last version of build tool

## Rollback by turnning off some feature flags 
