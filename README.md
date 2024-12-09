
# BestBuy Employee Application

This is a Vue.js app designed for the Best Buy management portal. It allows employees to process orders manually, manage product inventory, and monitor the order pipeline. It integrates with the **Product Service** and **Makeline Service**.

## Running the app locally

### Prerequisites

- [Node.js](https://nodejs.org/en/download/)
- [Vue CLI Service](https://cli.vuejs.org/guide/cli-service.html)
- [Docker](https://docs.docker.com/get-docker/)
- [Docker Compose](https://docs.docker.com/compose/install/)
- [OpenAI API Key](https://beta.openai.com/docs/developer-quickstart/your-api-keys)
- [Azure OpenAI API Key](https://azure.microsoft.com/products/cognitive-services/openai-service/)

### Running the app

To set up the necessary services, clone the repository, open a terminal, and navigate to the project directory.

If you plan to use OpenAI or Azure OpenAI, open the `docker-compose.yml` file, uncomment the `ai-service` block, and add your credentials.

```yaml
environment:
  - USE_AZURE_OPENAI=True # Set to False if not using Azure OpenAI
  - AZURE_OPENAI_DEPLOYMENT_NAME= # Required if using Azure OpenAI
  - AZURE_OPENAI_ENDPOINT= # Required if using Azure OpenAI
  - OPENAI_API_KEY= # Always required
  - OPENAI_ORG_ID= # Required if using OpenAI
```

Run the following command:

```bash
docker compose up
```

Then, in a new terminal, navigate to the `BestBuy-Employee` directory and run:

```bash
export VUE_APP_PRODUCT_SERVICE_URL=http://localhost:3002/
export VUE_APP_MAKELINE_SERVICE_URL=http://localhost:3001/

npm install
npm run serve
```

When the app is running, you'll see:

```text
  App running at:
  - Local:   http://localhost:8081/ 
  - Network: http://192.168.0.144:8081/
```

Navigate to `http://localhost:8081/` in your browser to see the Store Admin app.
    