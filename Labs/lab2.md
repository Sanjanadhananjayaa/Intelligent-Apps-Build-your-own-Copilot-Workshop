# Lab 2: Deploy Apps to Azure Container Apps

In this lab, you'll be building the docker images and publishing it to Azure Container Apps.

### Task 1: Build Docker Images for the Miyagi Application

1. Open Docker on the Lab VM by selecting the shortcut on the desktop and then double-click on it to open.
1. On **Docker Subscription Service Agreement** window, click **Accept**.
1. If **This site is trying to open Postman.** pop up's click on **Open**.
1. Navigate to miyagi/ui/ right - click on ui/typescript in cascading menu, select **Open in intergate Terminal**.
1. Run following command to build a Docker image

    ```
    Docker build . -t miyagi-ui      
    ```
1. Run foolowing command to show the newly created image
   ```
   docker images
   ```
1. Run following command
   ```
   docker run -t miyagi-ui -p 8001:3000
   ```
1. Navigate to **miyagi/services/recommendation-service/dotnet** right - click on dotnet in cascading menu, select **Open in intergate Terminal**
1. Run following command to build a Docker image

   ```
   Docker build . -t miyagi-recommemdation      
   ```
1. Run foolowing command to show the newly created image
   ```
   docker images
   ```
1. Run following command
   ```
   docker run -t miyagi-ui -p 8001:3000
   ```
1. Navigate to miyagi/ui/ right - click on ui/typescript in cascading menu, select **Open in intergate Terminal**.

1. Run following command

   **Note**: Please replace miyagi[did] with miyagi<inject key="DeploymentID" enableCopy="false"/>

   ```
    docker tag miyagi-ui:latest miyagiacr{did].azurecr.io/miyagi-ui:latest
   ```
1. Run the following command to push image to container registery

   **Note**: Please replace miyagi[did] with miyagi<inject key="DeploymentID" enableCopy="false"/>

   ```
    docker push miyagiacr[did].azurecr.io/miyagi-ui:latest

   ```

1. Navigate to **miyagi/services/recommendation-service/dotnet** right - click on dotnet in cascading menu, select **Open in intergate Terminal**

1. Run following command

   **Note**: Please replace miyagi[did] with miyagi<inject key="DeploymentID" enableCopy="false"/>

   ```
    docker tag miyagi-recommendation:latest miyagiacr{did].azurecr.io/miyagi-recommendation:latest
   ```
1. Run the following command to push image to container registery

   **Note**: Please replace miyagi[did] with miyagi<inject key="DeploymentID" enableCopy="false"/>

   ```
    docker push miyagiacr[did].azurecr.io/miyagi-recommendation:latest

   ```
