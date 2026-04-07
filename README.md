# Playwright Test Suite for Shoplane E-Commerce

A test automation project using Playwright to test the Shoplane e-commerce website.

## Project Overview

This project contains a Playwright test suite for testing the Shoplane e-commerce application.

## What's In This Project

- **`tests/`** - Playwright test specifications
  - `example.spec.ts` - Basic test example verifying page title
  - `QA_TEST_SCENARIOS.md` - AI generated test scenarios for the Shoplane website including product catalog, banner carousel, navigation, shopping cart, and checkout functionality
  
- **`e-commerce-project-master/`** - The Shoplane e-commerce website (based on shoaibsayyed03's original project)
  - Responsive e-commerce website built with HTML, CSS, and JavaScript
  - Features product browsing, shopping cart, and checkout functionality
  - Uses the Slick carousel library for product banners
  - Fetches product data from an API
  - Browser localStorage for cart persistence

- **`playwright.config.ts`** - Playwright configuration
  - Configured to test against base URL: `http://localhost:8080`
  - Uses Chromium browser
  - Generates HTML test reports
  - Trace collection on first retry

- **`package.json`** - Project dependencies
  - `@playwright/test` - Test framework
  - `@types/node` - TypeScript node definitions

## Getting Started

1. Install dependencies:
   ```
   npm install
   ```

2. Run tests:
   ```
   npx playwright test
   ```

3. View test report:
   ```
   npx playwright show-report
   ```

## Attribution

The e-commerce project is based on the original work by [shoaibsayyed03](https://github.com/shoaibsayyed03) and has been adjusted for use in this testing project.
