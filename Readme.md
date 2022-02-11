# ASP.NET_MacOs
## setting up the environment
### 1️⃣ Install Rider
###### Rider is made by the same company who does Resharper(JetBrains). Resharper is awesome and makes your life a lot easier when you're coding. It can also suggest better ways of doing things. It also works like a charm on Mac which is great for me who likes to work across my PC and Mac. 
###### Actually that's the best IDE to develop .NET application on MacOs (Apple silicon). However a lot of things that are easily accomplished in Visual Studio take a few more steps to initially setup in Rider. Entity Framework is one of them. Hopefully this will help someone else set it up or me when I need to do this again for my next project and forget 😁
###### First Go download the full version of Rider from [jetbrains.com](https://www.jetbrains.com/dotnet)
###### Then you may install The UI for EntityFramework Core from [plugins.jetbrains](https://plugins.jetbrains.com/plugin/18147-entity-framework-core-ui)
### 2️⃣ Install SQL Server in Mac M1
#### Step 1
###### We must utilize Docker because MacOS does not provide native support for Microsoft technology. Fortunately, Docker already supports ARM applications, so we can get it from the Docker website. 
`Direct Download Link (Docker)` [Click here](https://desktop.docker.com/mac/stable/arm64/Docker.dmg?utm_source=docker&utm_medium=webreferral&utm_campaign=dd-smartbutton&utm_location=header)
#### Step 2
###### After that go running SQL Query and other DB activities, you’ll need to download an IDE. SQL Server Management Studio is the greatest tool for SQL Server to run SQL Query, although it is only supported on Windows OS. Microsoft has developed an alternative to SQL Server Management Studio, thanks to their team. Azure Data Studio is the tool’s name. This tool will be used on our M1-based Mac.
`Download Azure Data Studio` [Click here](https://docs.microsoft.com/en-us/sql/azure-data-studio/download-azure-data-studio?view=sql-server-ver15#get-azure-data-studio-for-macos)
#### Step 3
###### We’ll need to create an ID on [Docker](https://hub.docker.com) or log in with the one you already have. After you’ve logged in, you’ll need to download a Microsoft-hosted docker image called Azure SQL Edge. We’ll use docker commands to download this image to our local system, and then run it in a docker container on the localhost port. We’ll be able to use the SQL server on our M1-based Mac once we run the image in the container.
#### Step 4
###### We can use the mac OS terminal to download the docker image. Open the terminal in your Mac System and Enter the command:
`docker pull mcr.microsoft.com/azure-sql-edge` 
###### Docker will start pulling the image from the web repository and downloading it to your local machine after you run the command above. The image is also visible in the Docker Desktop window, as illustrated below.
#### Step 5
###### Once you’ve downloaded the Docker image, you’ll need to execute it in a Docker container on a live localhost port. Use the same terminal window to run the command below. 
`docker run -d — name MySQLServer -e ‘ACCEPT_EULA=Y’ -e ‘SA_PASSWORD=your_password123’ -p 1433:1433 mcr.microsoft.com/azure-sql-edge`
###### When the command completes successfully, go to the container option in the Docker desktop window and look for a container with the same name as the one we specified in the command.
#### Step 6
###### After that, we can log in to Azure Data Studio using the credentials we just created. Here’s how you can get in touch with it.
