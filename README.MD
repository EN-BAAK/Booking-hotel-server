# Booking-Hotel-Server

A backend server for a hotel booking application, built using **Express**, **TypeScript**, **Mongoose**, and **Multer**.

> **Note:** This project is based on the tutorial from [Chris Blakely's YouTube channel](https://www.youtube.com/@ChrisBlakely). Huge thanks to Chris for the original code and guidance!

## Features

### Routers

#### 1. **Auth**

- `POST api/auth/login` - Log in a user.
- `POST api/auth/logout` - Log out the current user.
- `GET api/auth/verify-token` - Verify the user's authentication token.

#### 2. **Hotels**

- `GET api/hotels/search` - Search hotels by:
  - Star rating
  - Child count
  - Adult count
  - Price per night
  - Facilities
  - Types
  - Maximum price
  - Destination
- `GET api/hotels/:id` - Fetch specific hotel details.
- `POST api/hotels/:hotelId/bookings/payment-intent` - Pay and book a hotel.
- `GET api/hotels` - Fetch all hotels.
- `GET api/hotels/:hotelId/bookings` - Fetch all bookings for a specific hotel.

#### 3. **My Bookings**

- `GET api/my-bookings` - Fetch the authenticated user's bookings.

#### 4. **My Hotels**

- `POST api/my-hotels` - Create a new hotel.
- `PUT api/my-hotels/:id` - Update an existing hotel.
- `GET api/my-hotels` - Fetch all hotels owned by the authenticated user.
- `GET api/my-hotels/:id` - Fetch a specific hotel owned by the authenticated user.

#### 5. **Users**

- `GET api/users/me` - Fetch the user's profile.
- `POST api/users/register` - Register a new user.

---

### Models

#### 1. **Hotel**

- `userId` (string) - The ID of the owner.
- `name` (string) - Hotel name.
- `city` (string) - City where the hotel is located.
- `country` (string) - Country where the hotel is located.
- `description` (string) - Hotel description.
- `type` (string) - Type of hotel (e.g., resort, apartment).
- `adultCount` (number) - Number of adults allowed.
- `childCount` (number) - Number of children allowed.
- `facilities` (array) - Facilities provided by the hotel.
- `pricePerNight` (number) - Price per night in USD.
- `starRating` (number) - Star rating (1–5).
- `imageUrls` (array) - Array of image URLs.
- `lastUpdated` (Date) - Timestamp of the last update.
- `bookings` (array) - List of associated bookings.

#### 2. **Bookings**

- `userId` (string) - The ID of the user who booked.
- `firstName` (string) - First name of the user.
- `lastName` (string) - Last name of the user.
- `email` (string) - Email of the user.
- `adultCount` (number) - Number of adults.
- `childCount` (number) - Number of children.
- `checkIn` (Date) - Check-in date.
- `checkOut` (Date) - Check-out date.
- `totalCost` (number) - Total cost of the booking.

#### 3. **Users**

- `email` (string) - User's email.
- `password` (string) - Hashed password.
- `firstName` (string) - First name of the user.
- `lastName` (string) - Last name of the user.

---

## How to Use

### Backend Setup

1. Clone the repository.
2. Navigate to the repo directory: `cd ./repo`
3. Install dependencies using `npm install`
4. Build the project using `npm build`
5. Create a .env file in the root directory and add the following environment variables:
   ```
   CLOUDINARY_CLOUD_NAME=<your-cloudinary-cloud-name>
   CLOUDINARY_API_KEY=<your-cloudinary-api-key>
   CLOUDINARY_API_SECRET=<your-cloudinary-api-secret>
   STRIPE_API_KEY=<your-stripe-api-key>
   MONGODB_CONNECTION_STRING=<your-mongodb-connection-string>
   FRONTEND_URL=<your-frontend-url>
   JWT_SECRET_KEY=<your-jwt-secret-key>
   ```
6. Clone frontend repository: `git clone https://github.com/EN-BAAK/Booking-hotel-frontend.git`
7. Follow the usages steps in readme file
8. Start the server using `npm start`
