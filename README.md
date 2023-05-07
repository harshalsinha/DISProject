# Final Project: CS553 Design of Internet Services

Overview: This repository contains four NextJS web applications that have authentication configured using NextAuth.js and they also have the necessary configurations needed to measure performance using OpenTelemetry.

Installation: Follow these steps after cloning the repo.

Web App 1: Custom Adapter for Postgresql
1. Go into the Adapters/Custom_Postgresql/next-auth-example directory. 
2. In the terminal, run the command 'npm install' . This installs all the required dependencies.
3. Create an env file and mention the following variables to configure Postgresql database 
    
    DATABASE_URL=postgresql://postgres:<Password_for_Postgres>@localhost:5432/nextauth
    PGHOST=<IP_Address_Postgresql>
    PGUSER=postgres
    PGPASSWORD=<Your Password>
    PGDATABASE=nextauth

    GITHUB_ID=<Your Github ID>
    GITHUB_SECRET=<Your Github Secret>

You can follow the instruction here to obtain your Github ID and secret: https://support.heateor.com/get-github-client-id-client-secret/#:~:text=Navigate%20to%20GitHub%20Developer%20Settings,login%20to%20your%20Github%20account.&text=Copy%20the%20Client%20ID%20and,page%20in%20the%20admin%20area.

Note: You will need to create a database named nextauth which has the schema defined at this URL: https://authjs.dev/reference/adapters#models
4. At this point the webapp should run on "http://localhost:3000/".
5. To set up OpenTelemetry for the benchmarking you will need to run the following commands in another directory: A pre-requisite here is that Docker should be installed.

    git clone -b main https://github.com/SigNoz/signoz.git
    cd signoz/deploy/
    ./install.sh
6. At this point, OpenTelemetry should be running and will be available at http://localhost:3301/ .

Note: The configurations required to measure the performance of our NextJS application is already present. So, once you open the url: http://localhost:3301/ to view OpenTelemetry's dashboard you should be able to see a service named: "Custom-Postgresql"

Web App 2: Prisma Adapter for Postgresql
1. Go into the Adapters/Prisma_Postgres/next-auth-example directory.
2. In the terminal, run the command 'npm install' . This installs all the required dependencies.
3. Create an env file and mention the following variables to configure Prisma and the database:
    DATABASE_URL=postgresql://postgres:<Password_for_Postgres>@localhost:5432/nextauth
    GITHUB_ID=<Your Github ID>
    GITHUB_SECRET=<Your Github Secret>
4. At this point the webapp should run on "http://localhost:3000/".
5. If OpenTelemetry is already installed and running, you can skip the steps mentioned below.
6. To set up OpenTelemetry for the benchmarking you will need to run the following commands in another directory: A pre-requisite here is that Docker should be installed.

    git clone -b main https://github.com/SigNoz/signoz.git
    cd signoz/deploy/
    ./install.sh
7. At this point, OpenTelemetry should be running and will be available at http://localhost:3301/ .

Web App 3: Prisma Adapter for MongoDB
1. Go into the Adapters/Prisma_Mongo directory/next-auth-example.
2. In the terminal, run the command 'npm install' . This installs all the required dependencies.
3. Create an env file and mention the following variables to configure Prisma and the database:
    DATABASE_URL=mongodb+srv://<Mongo_User>:<Your_Password><Your_Mongo_Cluster_IP>
    GITHUB_ID=<Your Github ID>
    GITHUB_SECRET=<Your Github Secret>
4. At this point the webapp should run on "http://localhost:3000/".
5. If OpenTelemetry is already installed and running, you can skip the steps mentioned below.
6. To set up OpenTelemetry for the benchmarking you will need to run the following commands in another directory: A pre-requisite here is that Docker should be installed.

    git clone -b main https://github.com/SigNoz/signoz.git
    cd signoz/deploy/
    ./install.sh
7. At this point, OpenTelemetry should be running and will be available at http://localhost:3301/ .

Web App 3: Custom Adapter for MongoDB
1. Go into the Adapters/MongoDb_Adapter/next-auth-example.
2. In the terminal, run the command 'npm install' . This installs all the required dependencies.
3. Create an env file and mention the following variables to configure Prisma and the database:
    MONGODB_URI=mongodb+srv://<Mongo_User>:<Your_Password><Your_Mongo_Cluster_IP>
    GITHUB_ID=<Your Github ID>
    GITHUB_SECRET=<Your Github Secret>
4. At this point the webapp should run on "http://localhost:3000/".
5. If OpenTelemetry is already installed and running, you can skip the steps mentioned below.
6. To set up OpenTelemetry for the benchmarking you will need to run the following commands in another directory: A pre-requisite here is that Docker should be installed.

    git clone -b main https://github.com/SigNoz/signoz.git
    cd signoz/deploy/
    ./install.sh
7. At this point, OpenTelemetry should be running and will be available at http://localhost:3301/ .

PS: This entire process of cloning and evaluation will take around 45 minutes - 1 hr. Also, please note that since all the evaluations have been carried out on my local machine the results that might show up during your run might be a little different(as it is not hardware agnostic) if we talk about latency numbers but the overall conclusion that we have drawn should be consistent.
