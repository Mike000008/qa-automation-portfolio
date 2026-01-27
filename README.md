# QA Web & API Testing Portfolio

## Project Overview
This repository contains a QA portfolio project demonstrating a full testing workflow:
manual testing, API testing, test automation using Python, and CI integration.
The project is designed to simulate a realistic QA process used in production environments.

## Applications Under Test
- **Web UI:** Sauce Demo (e-commerce demo application)
- **REST API:** Reqres (public REST API for testing)

## Testing Scope
- Manual testing (test plan, test cases, bug reports)
- API testing (Postman collections and automated API tests)
- UI automation (basic Playwright tests)
- CI integration (GitHub Actions)

## Tools & Technologies
- Python
- pytest
- requests
- Playwright
- Postman
- GitHub Actions

## Repository Structure
manual-testing/     # Test plan, test cases, bug reports
postman/            # Postman collections
automation/         # Automated API and UI tests
.github/workflows/  # CI pipelines


## CI/CD
Automated tests are executed using GitHub Actions on every push and pull request.
The pipeline runs API and UI tests and fails if critical checks do not pass.

## Notes
This project focuses on QA activities and testing practices rather than application development.
