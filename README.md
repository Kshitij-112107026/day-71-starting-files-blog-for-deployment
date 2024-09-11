Here’s a `README.md` file for your blog post website:

```markdown
# Blog Post Website

This is a simple blog post website built using Flask, a lightweight web framework for Python. The website allows users to register, log in, and create blog posts. It also includes an admin-only section for creating, editing, and deleting posts. Additionally, users can comment on blog posts after logging in.

## Features

- User registration and login functionality.
- Secure password hashing using `Werkzeug`.
- Role-based access control with an `admin_only` decorator for post management.
- Users can comment on blog posts.
- Simple WYSIWYG editor for creating blog posts using CKEditor.
- Responsive design with Bootstrap 5 integration.

## Technologies Used

- **Flask**: Web framework for Python.
- **Flask-Bootstrap**: Bootstrap 5 integration for front-end styling.
- **Flask-Login**: User session management (login/logout).
- **Flask-SQLAlchemy**: Object-relational mapping (ORM) for database management.
- **Flask-CKEditor**: WYSIWYG text editor for rich text in posts.
- **SQLite**: Database for storing users, posts, and comments.
- **WTForms**: Handling and validating forms (user registration, login, post creation).

## Project Structure

```
├── static/                     # Static files (CSS, JS, images)
├── templates/                  # HTML templates
│   ├── index.html              # Homepage with all posts
│   ├── post.html               # Single post view
│   ├── register.html           # User registration form
│   ├── login.html              # User login form
│   ├── make-post.html          # Post creation and editing form
│   └── about.html              # About page
├── app.py                      # Main application file
├── forms.py                    # Forms for user registration, login, post creation
├── models.py                   # Database models for User, BlogPost, Comment
├── posts.db                    # SQLite database file
└── README.md                   # Project README
```

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/blog-post-website.git
   cd blog-post-website
   ```

2. Set up a virtual environment (optional but recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # For Linux/macOS
   venv\Scripts\activate     # For Windows
   ```

3. Install the required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Create the SQLite database:
   ```bash
   python
   >>> from app import db
   >>> db.create_all()
   ```

5. Run the Flask application:
   ```bash
   python app.py
   ```

6. Open a web browser and go to `http://127.0.0.1:5002`.

## Usage

- **Homepage**: Displays all blog posts.
- **Register**: Create a new user account by visiting `/register`.
- **Login**: Log in to an existing account by visiting `/login`.
- **New Post**: (Admin-only) Create a new blog post by visiting `/new-post`.
- **Edit Post**: (Admin-only) Edit an existing post by visiting `/edit-post/<post_id>`.
- **Delete Post**: (Admin-only) Delete a post by visiting `/delete/<post_id>`.
- **Comments**: Logged-in users can comment on blog posts.

## Admin Access

By default, the admin user is the user with the `id` of `1`. To create an admin account:

1. Register a new user.
2. Go to the SQLite database (`posts.db`) and change the `id` of this user to `1`.

Alternatively, modify the logic inside the `admin_only` decorator to suit your needs.

## Database Models

- **User**: Stores user details such as `email`, `password`, and `name`.
- **BlogPost**: Stores blog posts with fields like `title`, `subtitle`, `body`, `author_id`, and `date`.
- **Comment**: Stores comments on blog posts, linked to both `User` and `BlogPost`.

## Forms

- **RegisterForm**: For user registration, including fields for email, password, and name.
- **LoginForm**: For logging into an existing account.
- **CreatePostForm**: For creating new blog posts with fields like title, subtitle, and body.
- **CommentForm**: For commenting on a blog post.

## Security

- Passwords are hashed using `pbkdf2:sha256` with `generate_password_hash` for secure storage.
- Flask-Login manages user sessions and restricts certain routes using `@login_required`.
- The `admin_only` decorator restricts access to admin users for actions like adding, editing, and deleting posts.

## Future Improvements

- Add role-based user management to allow multiple admins.
- Implement pagination for displaying posts on the homepage.
- Use a more scalable database like PostgreSQL for production.
- Add better error handling and logging.
- Improve security by adding features like account lockout, password reset, and rate limiting.

## License

This project is licensed under the MIT License.

```

This README file outlines the key features, installation steps, usage, technologies used, and some ideas for future improvements. Feel free to modify it according to your specific project details.
