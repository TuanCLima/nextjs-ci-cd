# Next.js CI/CD Lab

A small Next.js application used to explore GitHub Actions, dependency caching and container builds. The app itself is the Next.js starter page; the focus is the delivery workflow.

## What is included

- Next.js 15, React 19, TypeScript and Tailwind CSS.
- A GitHub Actions workflow that installs dependencies and builds on pushes to `main`.
- A Dockerfile for building and serving the application.

The workflow currently performs a build; it does not deploy to a hosting provider. This is a learning repository, not a production deployment template.

## Run locally

Use Node.js 22 and npm:

```bash
git clone https://github.com/TuanCLima/nextjs-ci-cd.git
cd nextjs-ci-cd
npm ci
npm run dev
```

Open [localhost:3000](http://localhost:3000). The page lives in `src/app/page.tsx`.

## Build and lint

```bash
npm run build
npm run lint
```

The build uses `next/font`, which needs access to the Google font service. No application test suite is included.

## Container

```bash
docker build -t nextjs-ci-cd .
docker run --rm -p 3000:3000 nextjs-ci-cd
```

The container and Actions workflow use Node.js 22 and the checked-in npm lockfile. No deployment credentials are required for the build job.

## License

See [LICENSE](LICENSE).
