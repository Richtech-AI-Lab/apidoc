# API Workflows

## 1. Login
1. Call [```/v1/auth/login```](https://richtech-ai-lab.github.io/apidoc/#api-Auth-LoginUser). 

## 2. Register
1. Call [```/v1/auth/register```](https://richtech-ai-lab.github.io/apidoc/#api-Auth-RegisterUser).

## 3. Register a New Case
1. Create client using [```v1/client/register```](https://richtech-ai-lab.github.io/apidoc/#api-Client-RegisterClient) (No need for email and cell number).
2. Get the **clientId** returned to you in the success data.
3. Create new address using [```v1/utils/address/register```](https://richtech-ai-lab.github.io/apidoc/#api-Utils-RegisterClient).
4. Get the **addressId** returned.
5. Create new premises using [```v1/premises/register```](https://richtech-ai-lab.github.io/apidoc/#api-Premises-RegisterPremises) (need **addressId**).
6. Get the **premisesId** returned.
7. Create new case using [```v1/case/create```](https://richtech-ai-lab.github.io/apidoc/#api-Case-CreateCase) (need **premisesId**, **clientId**).
8. Get **caseId** returned.

## 4. Create a New Stage in a Case
1. Get the **caseId**.
2. Get the **stageType** from case details.
3. Create new stage using [```v1/stage/create```](https://richtech-ai-lab.github.io/apidoc/#api-Stage-CreateStage) (need **caseId**, **stageType**).
4. Get **stageId** returned.
5. Notice that all of the default tasks have been created with the stage (_jump to 5.4 to for reading the task objects_).

## 5. Get Tasks in a Stage
1. Get the **caseId**.
2. Get the **stageType** from case details.
3. Read stage object using [```v1/stage/:caseId/:stageType```](https://richtech-ai-lab.github.io/apidoc/#api-Stage-ReadStageByCaseIdAndStageType).
4. Get **tasks** array from the stage object.
5. Interate through the array, read task object using [```v1/task/:taskId```](https://richtech-ai-lab.github.io/apidoc/#api-Task-ReadTaskById).

