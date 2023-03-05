sequenceDiagram
    participant Client
    participant PasswordManagerAPI
    participant AnypointPlatform
    Client->>PasswordManagerAPI: Sends authentication request over HTTPS
    PasswordManagerAPI->>AnypointPlatform: Validates client credentials and requests an access token
    AnypointPlatform-->>PasswordManagerAPI: Returns access token
    PasswordManagerAPI-->>Client: Returns access token over HTTPS
    Client->>PasswordManagerAPI: Sends a request to access protected resource over HTTPS with access token
    PasswordManagerAPI->>AnypointPlatform: Validates access token
    AnypointPlatform-->>PasswordManagerAPI: Returns requested resource if access token is valid
    PasswordManagerAPI-->>Client: Returns requested resource over HTTPS
