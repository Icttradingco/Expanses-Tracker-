# 💰 Expense Tracker PWA - Settle & Track

A production-ready, mobile-first Progressive Web App for tracking expenses with advanced paid/unpaid settlement features. Built with React, IndexedDB, and modern web technologies.

## ✨ Key Features

### 🎯 Core Functionality
- **Offline-First Architecture**: Works without internet connection
- **Persistent Storage**: Data stored in IndexedDB, survives browser restarts
- **No Authentication Required**: Privacy-focused, no signup needed
- **PWA Enabled**: Installable on mobile and desktop devices

### 💰 Expense Management
- **Add/Edit/Delete Expenses**: Full CRUD operations
- **Category Organization**: 8 default categories + custom category support
- **Date-based Tracking**: Track expenses by date with calendar picker
- **Notes Support**: Add optional notes to each expense

### 🔄 Settlement System (Core Feature)
- **Paid/Unpaid Status Tracking**: Each expense defaults to "unpaid"
- **Category-based Settlement**: Settle all unpaid expenses by category
- **Automatic Date-based Settlement**: Mark expenses as paid up to a selected date
- **Settlement History**: View when expenses were settled
- **Outstanding Balance**: Real-time tracking of unpaid amounts

### 📊 Dashboard & Analytics
- **Today's Spending**: View current day expenses
- **Monthly Totals**: Track monthly spending patterns
- **Outstanding Balance**: See total unpaid amounts
- **Paid vs Unpaid Summary**: Visual breakdown of settlement status
- **Category-wise Unpaid Balance**: Track outstanding amounts per category

### 🎨 User Experience
- **Mobile-First Design**: Optimized for smartphone use
- **Dark/Light Mode**: Toggle between themes
- **Smooth Animations**: Delightful micro-interactions
- **Clean Fintech UI**: Professional, modern interface
- **Empty State Handling**: Helpful messages when no data exists

### 🔍 Filtering & Views
- **Date Range Filters**: All Time, Today, This Week, This Month
- **Status Filters**: All, Paid, Unpaid
- **Category Filters**: Filter by any category
- **Combined Filters**: Use multiple filters simultaneously

### 📤 Export Features
- **PDF Export**: Professional reports with filters
- **Excel Export (.xlsx)**: Spreadsheet with all data
- **Custom Date Ranges**: Export specific time periods
- **Status-based Export**: Export only paid or unpaid expenses

### ⚙️ Global Settings
- **Currency Selector**: 10+ currencies (symbol-only, no conversion)
- **Category Management**: Add, rename, delete custom categories
- **Theme Toggle**: Switch between dark and light modes
- **Category Icons**: Customize with emojis

## 📱 How It Works

### Settlement Flow (Critical Feature)

1. **View Outstanding Expenses**
   - Dashboard shows unpaid balance by category
   - See oldest and latest unpaid dates

2. **Select Category to Settle**
   - Go to Settlement tab
   - Choose category with unpaid expenses
   - View total amount and expense count

3. **Choose Settlement Date**
   - Select the date expenses were paid
   - All expenses on or before this date will be marked as paid

4. **Confirm Settlement**
   - System automatically:
     - Marks expenses as "paid"
     - Records the settlement date
     - Updates outstanding balance
     - Keeps expenses in history

5. **Post-Settlement**
   - Settled expenses remain visible
   - New expenses start as unpaid
   - Can view settlement dates in expense list

### Data Model

Each expense contains:
```javascript
{
  id: "unique-id",
  amount: 50.00,
  category: "food",
  date: 1704067200000, // timestamp
  note: "Lunch at cafe", // optional
  status: "unpaid" | "paid",
  paidDate: 1704153600000 | null
}
```

## 🚀 Technologies Used

- **React 18**: Component-based UI framework
- **Tailwind CSS**: Utility-first styling
- **IndexedDB**: Client-side database for offline storage
- **jsPDF**: PDF generation
- **SheetJS (xlsx)**: Excel file creation
- **Service Worker**: PWA offline capabilities

## 📦 Default Categories

1. 🍔 Food
2. 🏠 Rent
3. 🛒 Grocery
4. 🚗 Transport
5. 💡 Utilities
6. 🎬 Entertainment
7. 💊 Health
8. 📦 Other

## 🎨 Color Coding

- **Green**: Paid expenses, positive actions
- **Red**: Unpaid expenses, outstanding balance
- **Primary**: Interactive elements, active states

## 📊 Currently Implemented Features

### ✅ Completed Features

1. **Core Expense Management**
   - Add expense with amount, category, date, note
   - Edit existing expenses
   - Delete expenses with confirmation
   - View all expenses in list

2. **Settlement System**
   - Category-wise settlement view
   - Date picker for settlement date
   - Automatic status update for expenses <= paidDate
   - Settlement confirmation dialog
   - Outstanding balance calculation

3. **Dashboard**
   - Today's total spending
   - Monthly total spending
   - Outstanding unpaid balance
   - Paid vs Unpaid summary cards
   - Category-wise unpaid breakdown

4. **Filters & Views**
   - Date range: All, Today, Week, Month
   - Status: All, Paid, Unpaid
   - Category: All + individual categories
   - Real-time filter updates

5. **Export System**
   - PDF export with date range and status filters
   - Excel export with all columns
   - Preview of filtered data
   - Graceful handling of empty exports

6. **Settings**
   - Currency selector (10 currencies)
   - Dark/Light mode toggle
   - Category management (add/edit/delete)
   - Protection: Can't delete categories with expenses

7. **PWA Features**
   - Installable on devices
   - Offline functionality
   - Service worker caching
   - App manifest with icons

8. **Data Persistence**
   - IndexedDB for all data
   - Survives browser restart
   - Automatic data loading
   - Error handling for DB operations

## 🔧 Functional Entry URIs

### Main Routes
- `/` - Main application (all tabs accessed via bottom nav)

### Bottom Navigation Tabs
1. **Home (Dashboard)** - Default view
2. **List (Expenses)** - View and manage expenses
3. **Settle (Settlement)** - Settlement center
4. **Export** - Export to PDF/Excel
5. **Settings** - App configuration

### Modals/Overlays
- **Add Expense**: Triggered via floating action button (+)
- **Edit Expense**: Inline editing in expense list

## ⚠️ Edge Cases Handled

1. **No Unpaid Expenses**: Shows "All settled!" message in settlement tab
2. **Empty Export**: Graceful message when no data matches filters
3. **Currency Change**: Updates display immediately, doesn't alter saved amounts
4. **Delete Category**: Prevents deletion if category has expenses
5. **Browser Restart**: Data persists and loads automatically
6. **Offline Mode**: Full functionality without internet
7. **Date Validation**: Can't select future dates for expenses
8. **Settlement Date**: Can only settle up to current date

## 🚫 What's NOT Included (By Design)

- ❌ User authentication/signup
- ❌ Cloud sync/backup
- ❌ Backend server
- ❌ Partial payments (only full settlement)
- ❌ Exchange rate conversion
- ❌ Multi-user support
- ❌ Demo data

## 📱 Browser Compatibility

- ✅ Chrome/Edge (Chromium)
- ✅ Safari (iOS/macOS)
- ✅ Firefox
- ✅ Samsung Internet
- ⚠️ Requires modern browser with IndexedDB support

## 🔒 Privacy & Security

- **No Data Transmission**: Everything stored locally
- **No Tracking**: Zero analytics or tracking scripts
- **No Cookies**: Uses IndexedDB only
- **User Controlled**: Complete data ownership
- **No External Dependencies**: Works completely offline

## 💡 Usage Tips

1. **Regular Settlement**: Settle expenses weekly/monthly for accurate tracking
2. **Use Notes**: Add notes to remember expense details
3. **Custom Categories**: Create categories matching your spending habits
4. **Export Regularly**: Keep backups via Excel export
5. **Check Outstanding**: Review unpaid balance before settling

## 🎯 Recommended Next Steps

### Phase 2 Enhancements
1. **Recurring Expenses**: Auto-create monthly recurring expenses
2. **Budget Limits**: Set spending limits per category
3. **Charts & Graphs**: Visual spending trends with Recharts
4. **Search Functionality**: Search expenses by note/amount
5. **Bulk Actions**: Select and delete/settle multiple expenses
6. **Data Import**: Import expenses from CSV/Excel
7. **Backup/Restore**: Export/import entire database
8. **Multiple Currencies in Single Expense**: Foreign transaction tracking
9. **Tags System**: Add custom tags to expenses
10. **Expense Splitting**: Split expenses between categories

### Phase 3 Advanced Features
1. **Income Tracking**: Track income alongside expenses
2. **Savings Goals**: Set and track savings targets
3. **Bill Reminders**: Notifications for upcoming bills
4. **Receipt Photos**: Attach photos to expenses (camera integration)
5. **Multi-language Support**: Internationalization
6. **Reports Dashboard**: Advanced analytics and insights
7. **Category Budgets**: Set monthly budget per category
8. **Expense Trends**: AI-powered spending insights

## 🛠️ Technical Implementation

### Data Storage Structure

```
IndexedDB: ExpenseTrackerDB
├── expenses (Object Store)
│   ├── Indexes: date, category, status
│   └── Records: { id, amount, category, date, note, status, paidDate }
├── categories (Object Store)
│   └── Records: { id, name, icon }
└── settings (Object Store)
    └── Records: { key, value }
```

### State Management
- **React Context API**: Global app state
- **useState Hooks**: Component-level state
- **useMemo Hooks**: Computed values and filtering
- **useEffect Hooks**: Data loading and persistence

### Performance Optimizations
- Memoized calculations for dashboard stats
- Efficient IndexedDB queries with indexes
- Lazy loading of expense lists
- Debounced filter updates
- Optimized re-renders with React.memo patterns

## 📄 Files Structure

```
/
├── index.html          # Main app with React components
├── manifest.json       # PWA manifest
├── sw.js              # Service worker
└── README.md          # This file
```

## 🚀 Deployment

This is a static PWA - simply upload all files to any web hosting:
- GitHub Pages
- Netlify
- Vercel
- Firebase Hosting
- Any static hosting service

To deploy, go to the **Publish tab** in your development environment.

## 🐛 Known Limitations

1. **Browser Storage Limits**: IndexedDB has storage quotas (usually 50MB+)
2. **No Cloud Sync**: Data only on current device
3. **Manual Backup**: Must export regularly for backups
4. **Full Settlement Only**: Can't partially settle a category
5. **Single Currency Display**: No real-time exchange rates

## 📞 Support & Issues

Since this is a standalone PWA with no backend:
- Check browser console for errors
- Ensure IndexedDB is enabled
- Try clearing browser cache if issues persist
- Export data before troubleshooting

## 🎓 Learning Resources

This app demonstrates:
- Progressive Web App development
- IndexedDB usage patterns
- React Context API
- Offline-first architecture
- Client-side data export
- Mobile-first responsive design
- Dark mode implementation

## 📝 License

This is a production-ready personal expense tracker. Feel free to use and modify as needed.

---

**Built with ❤️ for personal finance management**

*Version 1.0 - Offline-First Expense Tracker with Settlement Tracking*