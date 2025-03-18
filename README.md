# DRF_API_Authetication

E[User Login] -->|POST /login/| F{Authenticate User}
F -->|Valid| G[Generate Token & Return Response]
F -->|Invalid| H[Return Authentication Error]

I[User Profile] -->|GET /profile/| J{Is Authenticated?}
J -->|Yes| K[Return User Data]
J -->|No| L[Return Unauthorized Error]

M[Change Password] -->|POST /change-password/| N{Validate Passwords}
N -->|Valid| O[Update Password]
N -->|Invalid| P[Return Validation Error]

Q[Send Password Reset Email] -->|POST /send-reset-email/| R{Email Exists?}
R -->|Yes| S[Generate UID & Token, Send Email]
R -->|No| T[Return User Not Found]

U[Password Reset] -->|POST /reset/:uid/:token| V{Validate Token}
V -->|Valid| W[Update Password]
V -->|Invalid| X[Return Token Error]
