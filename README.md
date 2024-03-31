**FastAPI Auth0 Integration**

This project demonstrates a secure and efficient way to integrate Auth0 authentication into a FastAPI application. It provides a user login and profile access flow, leveraging Auth0's robust capabilities.

**Key Features:**

- **Seamless Login:** Users can log in through Auth0 using their preferred credentials.
- **Secure Token Management:** Access and ID tokens are stored securely in user sessions using SessionMiddleware.
- **Protected Profiles:** User profiles are accessible only after successful authentication.
- **Environment Variables:** Configuration details like `CLIENT_ID`, `CLIENT_SECRET`, and `DOMAIN` are stored in a `.env` file for enhanced security and environment management.
- **Jinja2 Templating:** Jinja2 templates are used for rendering HTML pages like `home.html` and `profile.html`.
- **Poetry Dependency Management:** This project utilizes Poetry for dependency management, ensuring a consistent development environment.

**Requirements:**

- Python 3.6+
- FastAPI
- Authlib
- pydantic-settings
- Starlette
- Jinja2
- Poetry (recommended)
- httpx
- Uvicorn
- itsdangerous

**Installation:**

1. Create a virtual environment (recommended):
   ```bash
   python -m venv venv
   source venv/bin/activate  # Windows: venv\Scripts\activate
   ```

2. Install dependencies using Poetry (if using Poetry):
   ```bash
   poetry install
   ```

3. If not using Poetry, install dependencies manually:
   ```bash
   pip install fastapi authlib pydantic-settings starlette jinja2
   ```

**Configuration:**

1. Rename the `.env-sample` to `.env` file at the root of the project and add fill the following environment variables:

   ```
   DOMAIN=your-auth0-domain.com  # Replace with your Auth0 domain
   CLIENT_ID=your-auth0-client-id  # Replace with your Auth0 client ID
   CLIENT_SECRET=your-auth0-client-secret  # Replace with your Auth0 client secret
   SECRET_KEY=your-secure-secret-key  # Replace with a strong secret key for session encryption
   AUDIENCE=your-auth0-api-audience  # Replace with your Auth0 API audience (optional)
   ```

2. Replace placeholders (`your-auth0-domain.com`, etc.) with your actual values.

**Usage:**

1. Start the application:
   ```bash
   uvicorn fastid.app:app --reload  # For development with automatic reloading
   ```

2. Access the application in your browser at `http://localhost:8000`.

**Functionality:**

* **Login:** Clicking the "Login" button redirects the user to Auth0's login page. After successful authentication, they are redirected back to your application.
* **Profile:** Once authenticated, users can access their profile details by visiting the "/profile" endpoint.

**Limitations and Enhancements:**

- This example provides a basic login and profile access flow. Consider adding features like user registration, protected API endpoints, roles/permissions, error handling, and UI enhancements.
- Securely store your Auth0 client secret in a secrets management tool or environment variables in a production setting.
- Thoroughly test and document your integration.

**Further Exploration:**

- Refer to the Auth0 documentation for advanced configuration options: [https://auth0.com/docs](https://auth0.com/docs)
- Explore FastAPI and Jinja2 for building sophisticated web applications.
- Learn more about Poetry for dependency management: [https://install.python-poetry.org/](https://install.python-poetry.org/)
