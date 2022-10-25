# Milestones

## A

- Python 3
  - pylint
- Django 4
- MySQL 8+
- Bootstrap 5
  - Compressor
  - SASS
- Digital Ocean
  - alpha database
  - alpha App Platform
- Github Actions
  - pylint
  - run unit
  - run integration
  - alpha
- User Login
  - Database
  - django auth contrib
  - override username for email
- UI
  - Login
  - Logout
  - Forgot Password
  - Logged In UI
- Admin Setup
  - Super user

## B

- Organizations
  - Relationships
    - Has many Users
    - Has many Entities
    - Has 1 Owner
  - POST /organizations
  - GET /organizations
  - GET /organizations/:id
  - PUT /organizations/:id
  - DEL /organizations/:id
- Organization / Entity Users
  - POST /users - Add a user to org or entity
  - GET /users?orgId=1&entityId=2
  - GET /users/:id
  - PUT /users - Update a user in org or entity
    - Change org user to admin
    - change entity read only to admin
  - DEL /users - Delete a user from org or entity
- Invitations
  A user can be invites to an Org or an Entity
  - POST /invitations
  - DEL /invitations/:id
  - GET /invitations?orgId=1&entityId=2
  - GET /invitations/:token
- Entities
  - POST /entities
  - GET /entities
  - GET /entities/:id
  - PUT /entities/:id
  - DEL /entities/:id
- Test cases
  - Invite user to organization
  - Accept invitation to org
  - Delete invitation to Org
  - Invite user to entity
  - Accept invitation to entity
  - delete invitation to entity
  - Remove user from entity
  - Remove user from organization

## C

- Integration
  Manual integrations to start, lays groundwork for QBO integration
  - POST /integrations
  - GET /integrations
  - GET /integrations/:id
  - PUT /integrations/:id
  - DEL /integrations/:id
- Accounts
  Start with manual accounts (associated to manual integration)
  - POST /accounts
  - GET /accounts
  - GET /accounts/:id
  - PUT /accounts/:id
  - DEL /accounts/:id
- Categories
  - POST /categories
  - GET /categories
  - GET /categories/:id
  - PUT /categories/:id
  - DEL /categories/:id
- Fixed Asset
  - POST /assets
  - GET /assets
  - GET /assets/:id
    - calculate deprecation schedule
  - PUT /assets/:id
    - disposal fields
    - Change category
  - DEL /assets/:id
- Manual Override
  - POST /transactions
  - PUT /transactions/:id
  - DEL /transactions/:id
- Run Depreciation
  - GET /depreciation/:id/step-1
  - GET /depreciation/:id/step-2
  - GET /depreciation/:id/step-3
    - This runs a POST /journal-entries
- Journal Entries
  - POST /journal-entries
    - Stores them locally in database
  - GET /journal-entries
  - DEL /journal-entries
  - GET depreciation/:id/download

## D

- Settings
  - Account Mapping
  - Depreciation Strategy 50% first month
- Quick Books Integration
  - Write to QBO
    - POST /depreciation/:id/upload
  - OAuth with QBO
    - POST /integrations/qbo-callback
    - POST /integrations
    - GET /integrations
    - GET /integrations/:id
    - PUT /integrations/:id
    - DEL /integrations/:id
  - Category to Account Mapping
    - Integration Accounts M:M
  - QBO Finders
    - GET /integration/:id/find-assets
    - GET /integration/:id/find-disposals
- Reporting?

## E

- CSV Import
- Onboarding Wizard
  - GET /onboarding/organization
    - Allows sending invites
  - GET /onboarding/entity
    - Allows sending invites
    - Allows link to QBO
    - Default categories
- Stripe Integration
  - GET /plans (Shows available plans)
  - GET /subscriptions
  - GET /subscriptions/:id
  - GET /subscription/callback
  - POST /subscriptions
  - Transfer Org Ownership
- Locking?
