# Draftly
## 1. Overview
Draftly is a secure blogging platform built with Spring Boot. Registered users can write posts, save them as drafts, publish them, and discuss them through comments. Admins moderate content. Draftly exposes a RESTful API documented with Swagger UI and is meant to demonstrate a clean, tested, monolithic Spring Boot application.

## 2. User Roles
| Role | what they can do|
|------|-----------------|
| Guest | Register, log in, read published posts and their comments |
| User | Everything a guest can, plus create/edit/delete own posts, manage own drafts, comment, and edit/delete own comments |
| Admin | Everything a user can, plus delete any post or comment and manage users |

## 3. Functional Requirements

### Authentication
- FR-1: As a guest, I want to register with a username, email, and password so that I can create an account.
- FR-2: As a registered user, I want to log in with my credentials so that I receive a JWT and can access protected features.
- FR-3: As a user, I want to my session to expire safely so that a stolen token cannot be used forever.

### Posts
- FR-4: As a user, I want to create a post with a title and content so that I can share my writing.
- FR-5: A a user, I want to save a post as 'DRAFT' so that I can finish it later.
- FR-6: As a user, I want to publish a draft so that others can read it.
- FR-7: As a user, I want to edit or delete my own posts so that I can keep my content up to date.
- FR-8: As a user, I want to archive a post so that it is hidden without being deleted.
- FR-9: AS a guest, I want to browse published posts with pagination and sorting so that I can find content easily.
- FR-10: As a user, I want to see my own drafts so that I can continue working on them. Drafts are visible only to their author.

### Comments
