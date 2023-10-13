### Prerequisites

Before you begin, ensure you have the following tools and dependencies installed:

- Node.js and npm
- Docker
- Prisma
- Your favorite code editor

### Installing

1. Clone the repository to your local machine:

   ```shell
   git clone https://github.com/your-repo-url.git
   ```

2. Navigate to the project directory:

   ```shell
   cd prisma
   ```

3. Install the required dependencies:

   ```shell
   npm install
   ```

4. Install Prisma and generate Prisma client:

   ```shell
   npm install prisma @prisma/client
   npx prisma generate
   ```

### Database Setup

To run the project with a MySQL database using Docker, follow these steps:

1. Start a MySQL container using Docker:

   ```shell
   docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=your-root-password -p 3306:3306 -d mysql:latest
   ```

   Replace `your-root-password` with a secure password.

2. Create a `.env` file in the project root directory and configure the database connection:

   ```shell
   DATABASE_URL="mysql://root:your-root-password@127.0.0.1:3306/your-database-name"
   ```

   Replace `your-root-password` and `your-database-name` with your MySQL root password and the desired database name.

3. Run Prisma migrations to initialize the database:

   ```shell
   npx prisma migrate dev --name init --create-only
   npx prisma migrate deploy
   npx prisma format
   ```

### Running the Application

You can now start the application with the following command:

```shell
npm start
```

The application will be available at [http://localhost:3000](http://localhost:3000).
