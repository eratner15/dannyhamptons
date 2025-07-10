# Danny Hamptons - 40th Birthday Weekend App

A mobile-first web application for Dan's 40th birthday weekend in the Hamptons with real-money betting, photo sharing, and group coordination.

## Features

### 🎰 Betting Hub
- Create and take real-money bets
- Real-time betting updates
- Money tracking and settlement
- Photo evidence for bet resolution

### 📸 Photo Feed
- Upload and share photos
- Like and comment on photos
- Photo challenges and competitions
- Tag friends in photos

### 💬 Messaging
- Group chat for all attendees
- Direct messaging between users
- Real-time messaging with Socket.IO
- Poll creation and voting

### 🏆 Leaderboards
- Money leaderboard (betting winnings/losses)
- Points leaderboard (photo challenges, activities)
- Real-time updates

### 📱 Mobile-First Design
- Responsive design optimized for mobile
- Touch-friendly interface
- Bottom navigation
- PWA capabilities

## Technical Stack

- **Backend**: Node.js, Express, TypeScript
- **Database**: MongoDB with Mongoose
- **Real-time**: Socket.IO
- **Authentication**: SMS verification with Twilio
- **File Upload**: Multer for photo uploads
- **Frontend**: Vanilla JavaScript, HTML5, CSS3

## Setup Instructions

### Prerequisites
- Node.js (v16 or higher)
- MongoDB running locally or connection string
- Twilio account for SMS verification

### Installation

1. **Install dependencies**
   ```bash
   npm install
   ```

2. **Configure environment variables**
   Create a `.env` file with:
   ```
   PORT=3000
   MONGODB_URI=mongodb://localhost:27017/dannyhamptons
   JWT_SECRET=your-secure-jwt-secret
   TWILIO_ACCOUNT_SID=your-twilio-account-sid
   TWILIO_AUTH_TOKEN=your-twilio-auth-token
   TWILIO_PHONE_NUMBER=your-twilio-phone-number
   ```

3. **Build the application**
   ```bash
   npm run build
   ```

4. **Start the server**
   ```bash
   npm start
   ```

   For development with auto-reload:
   ```bash
   npm run dev
   ```

5. **Access the app**
   Open your browser to `http://localhost:3000`

## Pre-loaded Users

The app comes with 12 pre-loaded attendees:
1. Dan Brachfeld (Birthday boy)
2. Ryan Shuwarger
3. James Waldeck
4. Michael Gitner
5. Evan Ratner
6. Dan Nelson
7. Andrew Liebeskind
8. Trevor Belton
9. Eric Harwood
10. Mike Hornbuckle
11. Zach Warren
12. Final Attendee (update name as needed)

**Note**: Update phone numbers in `src/utils/seedUsers.ts` with real numbers before deployment.

## API Endpoints

### Authentication
- `POST /api/auth/send-code` - Send SMS verification code
- `POST /api/auth/verify-code` - Verify SMS code and get JWT token
- `GET /api/auth/profile` - Get user profile

### Betting
- `POST /api/betting/create` - Create new bet
- `GET /api/betting/active` - Get active bets
- `POST /api/betting/:id/take` - Take a bet
- `POST /api/betting/:id/settle` - Settle a bet
- `GET /api/betting/my-bets` - Get user's bets

### Photos
- `POST /api/photos/upload` - Upload photo
- `GET /api/photos` - Get photo feed
- `POST /api/photos/:id/like` - Like/unlike photo
- `POST /api/photos/:id/comment` - Add comment to photo

### Messages
- `POST /api/messages/send` - Send message
- `GET /api/messages` - Get messages
- `POST /api/messages/:id/read` - Mark message as read

### Leaderboards
- `GET /api/leaderboards/money` - Get money leaderboard
- `GET /api/leaderboards/points` - Get points leaderboard
- `GET /api/leaderboards/dashboard` - Get dashboard data

## Real-time Events

The app uses Socket.IO for real-time features:
- New bet notifications
- Bet updates (when someone takes action)
- New photo uploads
- New messages in group chat
- Bet settlements

## Deployment

1. **Update phone numbers** in `src/utils/seedUsers.ts`
2. **Set production environment variables**
3. **Build the application**: `npm run build`
4. **Start with process manager**: `pm2 start dist/server.js`

## Weekend Itinerary

### Thursday
- 3:00 PM: Check-in at house
- 7:30 PM: Dinner at Camp Rubirosa
- 10:00 PM: TalkHouse

### Friday - Montauk Day
- 4:00 PM: Surf Lodge
- 7:00 PM: Mary Lou's dinner/drinks

### Saturday
- 8:30 PM: Calissa dinner/drinks

### Sunday
- 11:00 AM: Departure

## House Information

**WiFi**: 71-granite-8285
**Garage Codes**: 9626 (right), 9627 (left)
**Owner**: Liz Ilgenfritz (917) 602-6520

## Contributing

This app is specifically designed for Dan's 40th birthday weekend. For modifications or improvements, please test thoroughly before the weekend!

## License

Private use only for Dan's 40th birthday weekend.