# CloudSlice_Pilot

![image](https://user-images.githubusercontent.com/64772417/171635588-43fb57eb-2f42-4bbc-93e0-a576206e60f0.png)

The pilot is composed of:
- it is composed of two public repositories:
    - **CloudSlice Pilot** (https://github.com/ESI-EMEA/CloudSlice_Pilot/edit/main/README.md) --> simulates the lab repositories used by **MicrosoftLearning** organization (for example AZ204 repo https://github.com/MicrosoftLearning/AZ-204-DevelopingSolutionsforMicrosoftAzure)
    - CloudSlice Pilot LODS (https://github.com/ESI-EMEA/CloudSlice_Pilot_LODS) --> Simulates repositories used by LODS/Skillable for lab issues under **LODSCloudSlice** organization  (for example Cloudslice AZ204 repo https://github.com/LODSCloudSlice/AZ-204T00-A-Cloud-Slice)

And it works the following way:
1. **MicrosoftLearning** repos are used to report any kind of lab related issue.
2. If the reported issue is related to CloudSlide(or Skillable), a label **cloudslice** is added to the issue (label can be assigned during or after issue is created). Labels will be assigned by Content Developers or MTT Content Leads.
3. **When the label is assigned**, it will trigger a **GitHub Action** (https://github.com/ESI-EMEA/CloudSlice_Pilot/blob/main/.github/workflows/actions.yml) that creates a replica of the issue in **LODSCloudSlice**, that way cloudslice can use their own project management tools provided by GitHub (like GitHub Projects) to work on the issue. The originally reported issue (the one in **MicrosoftLearning** repo), keeps track of the cloudslice pending work. Check the example on the diagram or jump to the provided demo repos shown above.
4. **When the issue is closed by Skillable/LODS** the original repo used by **MicrosoftLearning** will see it reflected. PENDING: We could even automate closing issue using another GitHub Action.

EXTRA:
As an alternative, the GitHub Action is also prepared to trigger a Logic App in Azure that sends an email to specified account/list.

# Summary
This approach would provide:
1. A single place for all learners+MTT/MCTs to track and report lab related issues.
2. Give freedom to both Content Dev and Skillable organization to define their own project management approach, keeping traceability on pending work. 


