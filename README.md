# FlightPro

FlightPro is an ASP.NET Core MVC web application for browsing and booking travel packages, built as a full travel-agency style platform — search and filtering, checkout with Stripe/PayPal, waiting lists for sold-out trips, customer reviews, and an admin dashboard.

## Features

- **Trip browsing & search** — filter packages by destination, country, city, category, price range, dates, and discount status, with sortable results.
- **Booking & checkout** — add trips to a cart or buy directly, with booking limits enforced per user (max active trips) via `BookingRuleService`.
- **Payments** — integrated checkout via [Stripe](https://stripe.com) and [PayPal](https://www.paypal.com).
- **Waiting list** — join a waiting list for sold-out package dates, with just-in-time reassignment when a spot opens up (`WaitlistService`).
- **User accounts** — registration and login with password hashing via BCrypt, session-based authentication.
- **Reviews** — site-wide reviews and per-package reviews.
- **Admin dashboard** — booking stats, revenue, package and user counts, and recent bookings, protected by an `[AdminOnly]` authorization filter.
- **Booking history & PDF receipts** — order history per user, with PDF generation via QuestPDF.

## Tech stack

- **Framework:** ASP.NET Core MVC (.NET 8)
- **Database:** SQL Server (via `Microsoft.Data.SqlClient`, raw ADO.NET/SQL queries)
- **Auth:** Session-based, BCrypt password hashing
- **Payments:** Stripe.net, PayPalCheckoutSdk
- **PDF generation:** QuestPDF
- **Frontend:** Razor views (`.cshtml`)

## Project structure

\`\`\`
FlightPro/
├── Controllers/   # Home, Trips, Order, MyBook, WaitingList, Reviews, User, Admin

├── Models/        # View models and domain models

├── Services/      # PayPalService, StripeService, WaitlistService, BookingRuleService

├── Views/         # Razor views per controller

└── wwwroot/       # Static assets (css, js, img, lib)
\`\`\`

### Prerequisites

- [.NET 8 SDK](https://dotnet.microsoft.com/download)
- A SQL Server instance ,use in Azure SQL

### For run the app: 

\`\`\`bash
cd FlightPro
dotnet restore
dotnet run
\`\`\`
