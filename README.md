
# DpWear Portfolio Website

## Project Description

This project involves creating a showcase website focused on displaying photographic works. The design is inspired by references from major brand sites such as Nike and Zalando, adopting a minimalist approach to highlight the photos. The goal is to develop an intuitive user experience with easy navigation and clear action buttons.

## Objectives

- **Define Purpose:** Create a portfolio site to showcase photographic works.
- **Research and Planning:** Analyze design elements and functionalities of competitors to plan the website sections (Hero, About, Gallery, etc.).
- **Design and UX:** Design a clean interface to emphasize visuals, with intuitive navigation.
- **Development and Implementation:** Code in HTML, CSS, and JavaScript to structure, style, and add dynamics to the site.
- **Testing and Optimization:** Ensure compatibility across various browsers and devices, optimize loading times.
- **Analytics and Monitoring:** Install and configure tools like Google Analytics to track visitor interactions.
- **Legal and Compliance:** Include necessary legal notices and ensure copyright compliance.

## Technology

- **HTML:** Basic structure of the site.
- **CSS:** Styling and layout.
- **JavaScript:** Site interactivity (dynamic menus, interactive maps).

## Site Structure

### Header:

* Company logo
* Search bar to allow users to quickly find products

* Links to important pages like "Home," "Products," "About," "Contact," etc.
* Shopping cart displaying the number of items and the total amount

### Slider or main banner:

* Highlight featured products or special promotions to attract visitors' attention

### Product Categories:

A section showcasing different product categories with images or icons, such as "Clothing," "Electronics," "Home & Garden," (adapted to the need of Daniel of course). Visitors can click on these categories to explore corresponding products.

### Featured Products:

Showcase some of your most popular or newest products to encourage visitors to explore further.

### Promotion or Special Offers Section:

Display ongoing promotions, special offers, or discounted products here to encourage impulse purchases.

### Customer Testimonials:

Testimonials from satisfied customers can boost confidence among new visitors in your business and products.

### Newsletter or Sign-Up:

Encourage visitors to sign up for your newsletter to receive special offers and updates on new products.

### Footer:

* Links to important pages like "Terms & Conditions," "Privacy Policy," etc.
* Contact information

* Links to your social media profiles

## Development Guide

### Installation

Clone the repository with:

```bash
git clone [URL_OF_GIT_REPOSITORY]
```

### Introduction to GitFlow

GitFlow is a branching strategy for Git, designed to provide a robust framework for managing larger projects. This approach defines a strict branching model designed around the project release. This guide will cover the basics of setting up and following the GitFlow pattern.

#### Setting Up GitFlow

Before you begin, ensure Git is installed on your system. You can optionally use Git extensions that assist with GitFlow operations, but here, we'll focus on the manual process.

#### GitFlow Branches

GitFlow revolves around two main branches with an infinite lifetime:

- **`master`**: This branch contains production-ready code only.
- **`develop`**: This branch serves as an integration branch for features. It contains the complete history of the project.

Other supporting branches are used for development, hotfixes, and releases:

- **Feature branches**: Branch off from `develop` and merge back into `develop`.
- **Release branches**: Branch off from `develop` and merge into both `develop` and `master`.
- **Hotfix branches**: Branch off from `master` and merge into both `develop` and `master`.

#### Workflow Overview

1. **Feature Development**:

   - Create a feature branch from `develop`:
     ```
     git checkout -b feature/<feature_name> develop
     ```
   - Regularly commit your changes to this branch.
   - Once the feature is complete, merge it back into `develop`:
     ```
     git checkout develop
     git merge --no-ff feature/<feature_name>
     git branch -d feature/<feature_name>
     git push origin develop
     ```
2. **Releasing**:

   - Create a release branch from `develop`:
     ```
     git checkout -b release/<release_version> develop
     ```
   - Prepare for a release: bump versions, update changelogs, fix bugs.
   - When ready, merge the release branch into `master` and `develop`:
     ```
     git checkout master
     git merge --no-ff release/<release_version>
     git tag -a <release_version>
     git checkout develop
     git merge --no-ff release/<release_version>
     git branch -d release/<release_version>
     ```
3. **Hotfixes**:

   - Create a hotfix branch from `master`:
     ```
     git checkout -b hotfix/<hotfix_version> master
     ```
   - Complete the hotfix and commit the changes.
   - Merge the hotfix branch into both `master` and `develop`:
     ```
     git checkout master
     git merge --no-ff hotfix/<hotfix_version>
     git tag -a <hotfix_version>
     git checkout develop
     git merge --no-ff hotfix/<hotfix_version>
     git branch -d hotfix/<hotfix_version>
     ```

#### Best Practices

* Regularly pull the latest changes from the origin to keep your local branches up-to-date.
* Use descriptive names for your feature, release, and hotfix branches.
* Always use the `--no-ff` flag when merging to preserve the branch information and facilitate potential rollbacks.
* Tag all releases to maintain a history of what's been deployed into production.

#### Conclusion

GitFlow is especially suited for projects that have a scheduled release cycle and for managing multiple versions in production. It may seem complex at first, but with practice, it becomes an invaluable tool for systematic version control.
