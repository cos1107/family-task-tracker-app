# Family Task Tracker App - 姐姐妹妹動起來

A family task tracking application for daily activities, specifically designed for tracking exercise and other family tasks.

## Features

- **User Selection**: Easy user identification with saved login state
- **Daily Check-in (每日打卡)**: Mark daily tasks as completed
- **Personal Progress (個人紀錄)**: View your weekly task completion
- **Team Progress (團隊打卡牆)**: See everyone's exercise progress
- **Statistics (成就圖表)**: Monthly completion rates with streak tracking
- **Admin Panel**: Manage users and tasks (admin only)
- **Mobile Responsive**: Works on all devices

## Deployment Options

### Option 1: Local Development (Full Functionality)

1. **Clone the repository**:
```bash
git clone https://github.com/YOUR_USERNAME/family-task-tracker-app.git
cd family-task-tracker-app
```

2. **Install dependencies**:
```bash
npm install
```

3. **Start the development server**:
```bash
npm start
```

4. **Open browser**:
```
http://localhost:3000
```

### Option 2: GitHub Pages (Frontend Only)

**Note**: GitHub Pages only serves the static frontend. For full functionality with data persistence, you'll need to run the backend locally or deploy it separately.

1. **Push to GitHub**:
```bash
git add .
git commit -m "Initial commit"
git push origin main
```

2. **Enable GitHub Pages**:
   - Go to your repository Settings > Pages
   - Under "Build and deployment", select "GitHub Actions"
   - The app will be available at: `https://YOUR_USERNAME.github.io/family-task-tracker-app`

## Important Notes

⚠️ **GitHub Pages Limitation**: GitHub Pages only serves static files. The backend API won't work on GitHub Pages.

✅ **Solution**: The app is configured to work in both environments:
- **Local Development**: Full functionality with Express backend at `http://localhost:3000`
- **GitHub Pages**: Static frontend only (you can view the UI but data won't persist)

## Project Structure

```
family-task-tracker-app/
├── backend/
│   └── server.js       # Express server with API endpoints
├── public/             # Static files (served by both local and GitHub Pages)
│   ├── css/
│   │   └── styles.css  # Application styles
│   ├── js/
│   │   └── app.js      # Frontend JavaScript
│   └── index.html      # Main HTML file
├── data/
│   └── database.json   # Local data storage
├── .github/
│   └── workflows/
│       └── deploy.yml  # GitHub Actions deployment
├── package.json        # Dependencies
└── README.md           # This file
```

## How It Works

### Local Development
- Express server (`backend/server.js`) serves the `public` folder
- API endpoints handle all data operations
- Data persists in `data/database.json`
- Full functionality available

### GitHub Pages
- Only the `public` folder is deployed
- Frontend works as a static site
- API calls will fail (no backend)
- Good for UI demonstration

## Default Users

- **Cosine** (Admin)
- **Iris** (Regular user)
- **Anna** (Regular user)
- **Rita** (Regular user)

## API Endpoints

The app uses the following API endpoints (handled by `backend/server.js`):

- `GET /api/users` - Get all users
- `POST /api/users` - Create new user
- `GET /api/tasks` - Get all tasks
- `POST /api/tasks` - Create new task
- `GET /api/completions/:userId` - Get user completions
- `POST /api/completions` - Save task completion
- `GET /api/statistics` - Get monthly statistics
- `GET /api/user-tasks` - Get user-task assignments

## Tech Stack

- **Frontend**: Vanilla JavaScript, HTML5, CSS3
- **Backend**: Node.js with Express
- **Data Storage**: JSON file-based database
- **Deployment**: 
  - Local: Node.js server
  - GitHub Pages: Static hosting (frontend only)
- **CI/CD**: GitHub Actions

## Troubleshooting

### "無法載入用戶列表，請確認伺服器是否運行中" Error

This means the frontend cannot reach the backend API:

1. **For Local**: Make sure you ran `npm start` to start the server on port 3000
2. **For GitHub Pages**: This is expected - GitHub Pages can't run the backend
3. **Check Console**: Open browser DevTools to see specific error messages

### Making It Work on Both Local and GitHub Pages

To make the app work in both environments, you could:

1. **Modify `app.js`** to detect the environment and use appropriate API URLs
2. **Use a cloud backend** service (Vercel, Heroku, Render) for the API
3. **Use localStorage** for client-side data persistence (no server needed)

## Future Enhancements

- Cloud database integration for persistent storage
- User authentication
- Email notifications
- Data export functionality
- Progressive Web App (PWA) support

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available under the MIT License.

## Support

For issues or questions, please open an issue on GitHub.