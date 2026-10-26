# MyCommerce — Full-Stack Fashion E-Commerce Application

A full-stack single-page e-commerce application built with a Django/Python backend and a Vue-based frontend. The codebase models common online-store workflows, including product catalogs, customer accounts, carts, orders, discounts, stock, and shipment information.

## Highlights

The repository includes Django applications and models related to:

- Products and product media
- User profiles and saved addresses
- Cart and order workflows
- Product history and shipment records
- Discounts and coupons
- Stock management and reviews
- API endpoints using Django REST Framework
- A Vue frontend with routing and state-management dependencies
- A Postman collection for API exploration

The presence of these modules indicates the project's intended scope; verify each workflow in a running instance before describing it as production-ready.

## Technology

- Python and Django
- Django REST Framework
- PostgreSQL support via Psycopg (database configuration must be checked locally)
- Vue 3 / Vite and related frontend packages
- JWT / authentication-related packages
- Docker and Docker Compose files
- Postman collection for API requests

## Setup notes

This repository includes multiple frontend directories, notebooks, data files, and environment-specific configuration. Review the existing project settings and Docker configuration before choosing a run path.

1. Clone the repository and create a virtual environment.
2. Install the Python dependencies using the dependency manager supported by the checked-in files.
3. Configure environment variables and database settings using local, non-committed values.
4. Install the dependencies for the intended frontend directory.
5. Apply migrations, create a local development user, and load test products only using the project's documented import flow.
6. Run the Django backend and the selected frontend using the commands appropriate to their current configuration.

Because the repository contains several frontend folders and legacy setup notes, the exact commands and ports should be verified against the current branch before relying on them. Do not use production credentials or real customer data for local testing.

## API exploration

The repository includes [Commerce.postman_collection.json](Commerce.postman_collection.json). Import it into Postman and update the base URL and authentication variables for your local environment before sending requests.

## Portfolio review checklist

Before submitting this repository to employers:

- Confirm a clean install from a fresh clone.
- Verify migrations and database setup.
- Exercise authentication, cart, order, stock, and discount workflows.
- Run the frontend build and any available tests.
- Remove or exclude generated/static/media data that is not needed for a source review.
- Document the intended frontend, API base URL, and database engine.
- Add screenshots or a short walkthrough using synthetic data.
- Confirm that secrets and personal/customer information are not committed.

## Project status

This is a substantial learning/project codebase, but the README and setup paths need validation before it should be described as a production-ready commerce system. It is a useful candidate for demonstrating full-stack concepts once a fresh setup and core user journeys have been tested.

## License

See [LICENSE](LICENSE).
