MagtanimAyDiBiro (MADB)
Rice Farming Management System

A Progressive Web App (PWA) designed to help Bagabag farmers manage their rice cultivation cycles with ease. Track farm progress, manage expenses, and receive timely reminders for each cultivation stage.

![MADB Dashboard](icon-192x192.svg)

---

## 📱 **Features**

### 🏡 **Multi-Farm Management**
- Create and manage multiple farm profiles
- Track separate cultivation cycles for each farm
- Switch between farms seamlessly
- Edit or delete farm information anytime

### 🌱 **Rice Cultivation Guide**
- Step-by-step guidance for all cultivation stages
- Automatic progress tracking based on planting date
- Visual timeline of cultivation progress
- Stage-specific recommendations and best practices

### 💰 **Expense Tracking**
- Record and categorize farm expenses
- View monthly and total cropping expenses
- Visual expense breakdown by category
- Filter expenses by farm
- View-only mode for completed farms

### ✅ **Farm Lifecycle Management**
- Mark farms as completed when harvest is done
- Maintain historical data for completed farms
- Unmark completion if needed
- Prevent accidental data modification on completed farms

### 🔔 **Smart Notifications**
- Get reminders for upcoming cultivation stages
- In-app notification banners
- Browser notifications (optional)
- Notifications for all active farms
- Daily notification checks to avoid spam

### 💾 **Data Backup & Restore**
- Export all farm and expense data as JSON
- Import backup files to restore data
- Data validation on import
- Confirmation prompts for safety

### 📊 **Dashboard Overview**
- Real-time cultivation progress
- Current stage and next action
- Financial overview (monthly & total)
- Expense breakdown chart
- Quick access to common actions

### 🔄 **Offline Capability**
- Works offline as a PWA
- Data stored locally using IndexedDB
- Automatic data persistence
- No internet required after installation

---

## 🛠️ **Technologies Used**

- **HTML5** - Semantic markup
- **CSS3** - Modern styling with gradients and animations
- **JavaScript (ES6+)** - Core functionality
- **IndexedDB** - Local database storage
- **Chart.js** - Data visualization
- **Service Worker** - Offline functionality
- **Web App Manifest** - PWA installation

---

## 🚀 **Getting Started**

### **Installation**

#### **Option 1: Install as PWA (Recommended)**
1. Visit the app URL in your browser
2. Look for "Install" or "Add to Home Screen" option
3. Follow the prompts to install
4. Launch from your home screen or app menu

#### **Option 2: Use in Browser**
1. Simply navigate to the app URL
2. No installation required
3. Works in any modern browser

### **First-Time Setup**
1. Open the app
2. Click "Get Started" on the welcome page
3. Fill in your farm details:
   - Farm name
   - Farm size (in hectares)
   - Planting date
   - Cropping cycle (First/Second/Third)
4. Click "Save & Continue"
5. Start tracking your cultivation!

---

## 📖 **Usage Guide**

### **Managing Multiple Farms**
1. Go to **Dashboard**
2. Click **"Manage Farms"** button
3. View all your farms
4. Click **"Add New Farm"** to create another
5. Use **Select**, **Edit**, or **Delete** buttons as needed

### **Adding Expenses**
1. Navigate to **Resources** tab
2. Click the **"+"** button (bottom right)
3. Fill in expense details:
   - Name (e.g., "Urea Fertilizer")
   - Category (Seeds, Fertilizer, etc.)
   - Date
   - Amount (₱)
4. Click **"Add Expense"**

### **Viewing Cultivation Progress**
1. Go to **Dashboard** tab
2. See current stage and progress bar
3. Check "Next Action" for upcoming tasks
4. Review stage timeline below

### **Checking Rice Guide**
1. Navigate to **Rice Guide** tab
2. Browse through cultivation stages
3. Read recommendations for each stage
4. See scheduled dates based on your planting date

### **Marking Farm as Complete**
1. Go to **Dashboard**
2. Click **"Mark as Completed"** button
3. Confirm the action
4. Farm will be marked as complete (no more expense edits)

### **Backing Up Your Data**
1. Go to **Manage Farms** page
2. Scroll to **"Backup & Restore"** section
3. Click **"Backup My Data"**
4. Save the JSON file to a safe location

### **Restoring from Backup**
1. Go to **Manage Farms** page
2. Click **"Restore from Backup"**
3. Select your backup JSON file
4. Confirm the restoration
5. App will reload with restored data

---

## 📁 **Project Structure**

```
MADB/
├── index.html              # Welcome/landing page
├── dashboard.html          # Main dashboard
├── farm-setup.html         # Farm creation/editing form
├── manage-farms.html       # Farm management page
├── rice-guide.html         # Cultivation guide page
├── resource-tracker.html   # Expense tracking page
├── manifest.json           # PWA manifest
├── service-worker.js       # Service worker for offline support
├── icon-192x192.svg        # App icon
├── css/
│   └── main.css           # All styles
└── js/
    ├── db.js              # IndexedDB utilities
    ├── rice-stages.js     # Cultivation stages data
    └── notifications.js   # Notification manager
```

---

## 🎨 **Design System**

### **Color Palette**
- **Primary Green**: `#4a7c59` - Main brand color
- **Secondary Green**: `#8fb996` - Accents and highlights
- **Accent Blue**: `#3d85c6` - Action buttons
- **Warning Orange**: `#e6a23c` - Current stage indicator
- **Background**: `#f5f5f5` - Page background
- **Text**: `#333` - Primary text color

### **Typography**
- **Font Family**: Arial, sans-serif
- **Headings**: Bold, larger sizes
- **Body Text**: Regular weight, readable sizes

---

## 💾 **Data Storage**

### **IndexedDB Structure**
- **Database Name**: `MADB`
- **Version**: `2`

#### **Object Stores:**
1. **`farms`** - Farm profiles
   - `id` (primary key)
   - `name`, `size`, `startDate`, `cropping`
   - `completed`, `completedDate`
   - `createdAt`, `updatedAt`

2. **`expenses`** - Expense entries
   - `id` (primary key)
   - `farmId` (indexed)
   - `name`, `category`, `amount`, `date`

3. **`settings`** - App settings
   - `selectedFarmId` - Currently active farm

4. **`farm_info`** - Legacy single-farm data (backward compatibility)

---

## 🔧 **Development**

### **Local Development**
1. Clone the repository
2. Open in a local web server (required for service workers)
3. Navigate to `index.html`

### **Recommended Tools**
- **VS Code** with Live Server extension
- **Chrome DevTools** for debugging
- **Lighthouse** for PWA testing

### **Testing**
- Test on multiple screen sizes (responsive design)
- Test offline functionality
- Test data persistence
- Test notification system
- Test backup/restore feature

---

## 🌐 **Deployment**

### **GitHub Pages**
1. Push code to GitHub repository
2. Go to **Settings** → **Pages**
3. Select branch (e.g., `main`)
4. Select root folder (`/`)
5. Click **Save**
6. Access via `https://yourusername.github.io/repositoryname/`

### **Other Hosting Options**
- Netlify
- Vercel
- Firebase Hosting
- Any static site hosting service

---

## 🔄 **Updates & Migration**

### **Data Migration**
The app automatically migrates data from older versions:
- Single-farm `localStorage` → Multi-farm `IndexedDB`
- Preserves all existing data
- Runs on first load with new version

### **Version History**
- **v2.0** - Multi-farm support, notifications, backup/restore
- **v1.0** - Initial release with single-farm tracking

---

## 🎯 **Browser Compatibility**

### **Supported Browsers**
- ✅ Chrome/Edge (v90+)
- ✅ Firefox (v88+)
- ✅ Safari (v14+)
- ✅ Mobile browsers (iOS Safari, Chrome Android)

### **Required Features**
- IndexedDB
- Service Workers (for PWA)
- ES6+ JavaScript
- CSS Grid & Flexbox

---

## 📝 **License**

This project is designed for Bagabag farmers and the agricultural community. Feel free to use, modify, and distribute.

---

## 👥 **Credits**

### **Development**
- Progressive Web App architecture
- IndexedDB for robust data storage
- Responsive design for mobile-first experience

### **Cultivation Data**
- Rice cultivation stages based on standard Philippine farming practices
- Tailored for Nueva Vizcaya region

---

## 🤝 **Contributing**

Suggestions and improvements are welcome! This app is built to serve the farming community.

### **Future Enhancements**
- [ ] Multi-language support (Tagalog, Ilocano)
- [ ] Weather integration
- [ ] Harvest yield tracking
- [ ] Income vs. expense reports
- [ ] Community features (tips sharing)
- [ ] Print reports

---

## 📧 **Support**

For questions or issues:
1. Check the in-app guide
2. Review this README
3. Test in different browsers
4. Clear cache and try again

---

## 🌾 **Mission**

**"Empowering Bagabag farmers, one step at a time."**

MADB aims to simplify farm management, reduce crop losses through timely reminders, and help farmers maintain better financial records. By digitizing farm management, we support the agricultural community in making data-driven decisions.

---

**Happy Farming! 🌾✨**

