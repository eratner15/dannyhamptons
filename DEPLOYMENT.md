# Danny Hamptons - Deployment Guide

## Quick Start

This project is now split into **backend** (API) and **frontend** (static site) for easy deployment.

### Backend (Railway/Heroku)
### Frontend (Netlify)

---

## Backend Deployment (Railway - Recommended)

1. **Create MongoDB Atlas Database**
   - Go to [MongoDB Atlas](https://cloud.mongodb.com/)
   - Create a free cluster
   - Get connection string: `mongodb+srv://username:password@cluster.mongodb.net/dannyhamptons`

2. **Deploy to Railway**
   - Connect GitHub repo to [Railway](https://railway.app/)
   - Set environment variables:
     ```
     MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/dannyhamptons
     JWT_SECRET=danny-hamptons-jwt-secret-2024
     EMAIL_USER=your-gmail@gmail.com
     EMAIL_PASS=your-app-password
     PORT=3000
     ```
   - Railway will auto-deploy on git push

3. **Note your backend URL**: `https://your-app-name.railway.app`

---

## Frontend Deployment (Netlify)

1. **Update config file**
   - Edit `frontend/js/config.js`
   - Replace `your-backend-url.railway.app` with your actual Railway URL

2. **Deploy to Netlify**
   - Drag and drop the `frontend/` folder to [Netlify](https://netlify.com/)
   - Or connect GitHub repo and set build directory to `frontend/`

3. **Your app is live!** 🎉

---

## Alternative: Heroku Backend

1. **Create Heroku app**
   ```bash
   heroku create dannyhamptons-api
   ```

2. **Set environment variables**
   ```bash
   heroku config:set MONGODB_URI=mongodb+srv://...
   heroku config:set JWT_SECRET=danny-hamptons-jwt-secret-2024
   heroku config:set EMAIL_USER=your-gmail@gmail.com
   heroku config:set EMAIL_PASS=your-app-password
   ```

3. **Deploy**
   ```bash
   git push heroku main
   ```

---

## Email Setup (Gmail)

1. **Enable 2FA** on your Gmail account
2. **Generate App Password**:
   - Gmail Settings → Security → 2-Step Verification → App passwords
   - Select "Mail" and generate password
3. **Use in environment variables**:
   - `EMAIL_USER`: your-email@gmail.com
   - `EMAIL_PASS`: the-generated-app-password

---

## User Management

The app is pre-loaded with these attendees:
- Dan Brachfeld: brachd@gmail.com
- Ryan Shuwarger: rshuwarger@gmail.com
- James Waldeck: jwaldeck@gmail.com
- Michael Gitner: michaelgitner@gmail.com
- Evan Ratner: evan.ratner@gmail.com
- Dan Nelson: dannelz@gmail.com
- Andrew Liebeskind: andyliebeskind@gmail.com
- Trevor Belton: trevorbelton@gmail.com
- Eric Harwood: emharwood@gmail.com
- Mike Hornbuckle: michael.hornbuckle@gmail.com
- Zach Warren: zwarren2@gmail.com

To login, users enter their email and receive a 6-digit verification code.

---

## Testing Locally

1. **Start MongoDB** (or use Atlas connection)
2. **Install dependencies**: `npm install`
3. **Set environment variables** in `.env`
4. **Start backend**: `npm run dev`
5. **Open frontend**: Open `frontend/index.html` in browser

---

## Production Environment Variables

### Backend (Railway/Heroku)
```
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/dannyhamptons
JWT_SECRET=danny-hamptons-jwt-secret-2024
EMAIL_USER=your-gmail@gmail.com
EMAIL_PASS=your-16-char-app-password
PORT=3000
```

### Frontend (Netlify)
Update `frontend/js/config.js`:
```javascript
API_URL: 'https://your-backend-url.railway.app'
```

---

## App Features

✅ **Email Authentication** - No SMS/Twilio needed
✅ **Real-money Betting** - Create and take bets
✅ **Photo Sharing** - Upload and like photos
✅ **Group Messaging** - Real-time chat
✅ **Leaderboards** - Money and points tracking
✅ **Mobile-First** - Optimized for phones
✅ **Real-time Updates** - Socket.IO integration

Ready for Dan's 40th birthday weekend! 🎉