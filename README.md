# azure-pipelines-merged-universal-adapter
 Adapter can poll all the Builds and Releases related information in a Pipeline.  

## About
- Azure Pipelines lets you build, test, and deploy with continuous integration (CI) and continuous delivery (CD) using Azure DevOps.
- A Build Pipeline is used to generate Artifacts out of Source Code. A Release Pipeline consumes the Artifacts and conducts follow-up actions within a multi-staging system.

### Working Condition:
1. The Adapter consists of two schemes like Builds and Releases.
2. It can only read, update by polling the builds and releases related information.
3. Each Scheme Tested with 20+ fields for insights and attached the field mapping in the images section.
4. We need to use two connection urls to authenticate,
    > for builds scheme: https://dev.azure.com
    > for releases scheme: https://vsrm.dev.azure.com
5. If needed only for builds scheme, configure the dynamic metadata; don't configure releases scheme as it breaks.
    > For Project metadata; depends on organization (also attached the image for reference)
    >> /${organization}/_apis/projects?api-version=7.0
    >> $.value.*.['name']  
    >> $.value.*.['name']

