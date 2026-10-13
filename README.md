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
- FR-11: As a user, I want to comment on a published post so that I can join the discussion.
- FR-12: As an admin, I want to edit or delete my own comments so that I can correct mistakes.
- FR-13: Aa a guest, I want to read comments on a published post so that I can follow the discussion.

### Admin
- FR-14: As an admin, I want to delete any post so that I can remove inappropriate content.
- FR-15: As an admin, I want to delete any comment so that I can moderate discussions.

## 4. Non-Functional Requirements
- NFR-1: Passwords are stored hashed with BCrypt, never in plain text.
- NFR-2: Authentication is stateless, using JWT.
- NFR-3: Input is validated('@Valid') and Invalid requests return clear 400 responses.
- NFR-4: Errors return meaningful message in a consistent format: stack traces are never exposed.
- NFR-5: All list endpoints support pagination and sorting.
- NFR-6: Unit and integration test coverage of 85% or more (JUnit 5, Mockito, Spring Boot Test).

## 5. Business Rules
- A post's status is one of 'DRAFT','PUBLISHED','ARCHIVED'.
- Only 'PUBLISHED' posts are visible to guests and other users.
- Only the author or an admin can modify or delete a post.
- Deleting a post also deletes its comments.
- Usernames and emails must be unique.

## 6. Out of Scope(v1)
- No fronted(API only)
- No social login (OAuth2) for now
- No image or file uploads
- No email notifications
- No post likes, tags, or categories
- NO nested (threaded) comments

## 7. Future Enhancements
- Email notifications for new comments (Spring Mail)
- File uploads (AWS S3 or GCP Storage)
- Refresh tokens
- Docker, CI/CD with GitHub Actions, cloud deployment
