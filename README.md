# 📚 Development Guidelines

This repository is part of a modular architecture for Shopify theme development.  
Below is the defined workflow:

## Repository and Branch Structure

- **`base`** → Main repository, forked from Shopify’s official **Dawn** theme.
  - **`base.base`** → Branch where all **common components and configurations** for child themes are stored.
- **`natural`** → Child repository, forked from **`base.base`**.
  - **`natural.base`** → Main branch for the **Natural** child theme.

## Core Principles

1. The **base** repository is used exclusively to maintain reusable components and shared configurations.
2. Theme-specific development is carried out within each child repository.
3. **Do not connect the `base` branch directly to Shopify.**  
   Shopify may automatically modify the code when using the page builder, and these changes should not be merged into `base.base` unless thoroughly reviewed.

## Recommended Workflow

1. Work from an alternative branch (`dev`) that mirrors `base`.
2. Create **feature branches** for every new development (`feature/your-new-feature`).
3. Connect alternative branches (`dev`, `feature/*`) to Shopify for real-time development and testing.
4. Use **cherry-pick** to selectively merge changes from secondary branches into `natural.base`.
5. Create **pull requests** from `natural.base` to `base.base` to share common improvements with the parent repository.

## Important Notes

- Unreviewed changes made via Shopify's visual editor **must not** be merged automatically into `base.base`.
- Only components and configurations useful across all child themes should be pushed to the parent repository.
- Keep the **base** repository as clean, stable, and reusable as possible.
