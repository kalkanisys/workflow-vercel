# Workflow Vercel

This repository contains a reusable GitHub workflow to deploy frontend projects (mostly React/Next.js) on Vercel.

## Features

- Automated deployment to Vercel
- Easy integration with React/Next.js projects
- Reusable workflow for multiple projects

## Usage

1. Copy the workflow file from this repository to your project's `.github/workflows` directory.

2. Create a `.github/workflows/deploy.yml` file in your project with the following content:

   ```yaml
   name: Deploy to Vercel

   on:
     push:
       branches:
         - main

   jobs:
     deploy:
       uses: kalkanisys/workflow-vercel/.github/workflows/deploy.yml@main
       with:
         VERCEL_ARGS: '--prod'
         VERCEL_PROJECT_ID: 'project-id'
         VERCEL_ORG_ID: ${{ secrets.VERCEL_ORG_ID }}
         VERCEL_SCOPE: 'token-scope'
       secrets:
         VERCEL_TOKEN: ${{ secrets.VERCEL_TOKEN }}
   ```

3. Add the required secrets to your GitHub repository:
   - `VERCEL_TOKEN`: Your Vercel token
   - `VERCEL_PROJECT_ID`: Your Vercel project ID
   - `VERCEL_ORG_ID`: Your Vercel organization ID

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request for any changes.

## Contact

For any questions or support, please open an issue in this repository.
