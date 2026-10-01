# MUSLIM DRESS LK 👗🇱🇰
> **Sri Lanka’s Premier Dedicated Multi-Vendor Muslim & Modest Clothing Marketplace**

A production-ready full-stack multi-vendor e-commerce platform engineered specifically and exclusively for authentic Muslim and modest apparel.

---

## 🌟 1. Project Overview & Marketplace Rules

- **Strict Modesty Focus**: Exclusively restricted to Muslim and modest clothing (Abayas, Shalwar Kameez, Lehengas, Modest Long Dresses, Muslim Wedding/Nikah Dresses, Party Wear, Casual Wear, Girls/Boys Islamic Wear, Family Matching Eid Sets, Saudi Thobes, Emirati Jubbahs, and Pure Linen Kurtas).
- **No Unrelated Products**: Strict category moderation prevents non-clothing items from entering the catalog.
- **Multi-Vendor Architecture**: Multiple approved Sri Lankan boutiques manage their storefronts, catalogs, size variants, stock, and orders.
- **Unified Multi-Vendor Checkout**: Customers can purchase dresses from multiple sellers in a single order with automatic order splitting and commission deduction.
- **Multi-Language Architecture**: Ready with English (`en`), Tamil (`ta`), and Sinhala (`si`) UI translations.
- **Sri Lanka-Tailored Logistics**: Islandwide Cash on Delivery (COD) across all 25 districts, LKR currency formatting, and sizing standards.

---

## 🛠️ 2. Technology Stack

### Frontend
- **Framework**: Next.js 14 with TypeScript & React 18
- **Styling**: Tailwind CSS with custom luxury Muslim fashion palette (Gold `#D4AF37`, Emerald Forest Green `#0D2818`, Luxury Cream `#FAF8F5`)
- **Icons**: Lucide React
- **HTTP Client**: Axios with automatic JWT and guest session interceptors
- **State Management**: React Context (`AuthContext`, `CartContext`, `WishlistContext`, `LanguageContext`)

### Backend
- **Runtime & Server**: Node.js & Express.js with TypeScript
- **ORM & Database**: Prisma ORM with SQLite (zero-config instant run) and MySQL production schema compatibility
- **Security**: Helmet, CORS, Express Rate Limit, bcryptjs password hashing, JWT authentication & RBAC middleware
- **File Uploads**: Multer image storage with Cloudinary-ready architecture

---

## 👥 3. User Roles & Pre-Seeded Demo Accounts

| Role | Email | Password | Access / Functionality |
|---|---|---|---|
| **👑 Admin** | `admin@muslimdress.lk` | `admin123` | Dashboard metrics, Approve/Reject sellers, Moderate products, Manage commissions, Banners, Global orders |
| **🏪 Seller (Noor Abaya)** | `noor@abaya.lk` | `password123` | Seller Dashboard, Product CRUD, Variant & Stock management, Order fulfillment, Shop profile |
| **🏪 Seller (Modest LK)** | `info@modestfashion.lk` | `password123` | Boutique management, order item tracking, earnings breakdown |
| **👤 Customer** | `customer@muslimdress.lk` | `password123` | Browse catalog, Filter by size/colour, Wishlist, Cart, COD Checkout, Live Order Tracking, Reviews |

---

## 🚀 4. Quick Start & Setup Guide

### Prerequisites
- Node.js (v18+ or v22+)
- npm (v9+)

### 1. Install Dependencies
```bash
# Backend dependencies
cd backend
npm install

# Frontend dependencies
cd ../frontend
npm install
```

### 2. Initialize Database & Seed Sample Data
```bash
cd backend
npm run db:push
npm run db:seed
```

### 3. Run the Development Servers
In two separate terminals:

**Terminal 1 (Backend API - Port 5000):**
```bash
cd backend
npm run dev
```

**Terminal 2 (Frontend Web App - Port 3000):**
```bash
cd frontend
npm run dev
```

Open your browser at **`http://localhost:3000`** to experience **MUSLIM DRESS LK**.

---

## 📂 5. Directory Structure

```
muslim-dress-lk/
├── backend/
│   ├── prisma/
│   │   └── schema.prisma           # Prisma schema (SQLite / MySQL)
│   ├── src/
│   │   ├── config/                 # App and Prisma configuration
│   │   ├── controllers/            # Auth, User, Seller, Product, Cart, Order, Admin controllers
│   │   ├── database/               # Database seeder (seed.ts)
│   │   ├── middleware/             # JWT Auth, RBAC, ErrorHandler, Multer Upload
│   │   ├── routes/                 # REST API route definitions
│   │   ├── utils/                  # JWT helpers, standard response formatters
│   │   └── server.ts               # Express server entry point
│   ├── uploads/                    # Local image storage
│   ├── .env                        # Backend environment configuration
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── home/               # HeroBanner, CategoryGrid, FeaturedSellers
│   │   │   ├── layout/             # Navbar, MobileNav, Footer, Layout
│   │   │   └── product/            # ProductCard with quick-add
│   │   ├── context/                # AuthContext, CartContext, WishlistContext, LanguageContext
│   │   ├── pages/                  # Pages router (/shop, /categories, /product/[slug], /seller/[slug], /cart, /checkout, /seller/dashboard, /admin/dashboard, etc.)
│   │   ├── services/               # Axios API client
│   │   ├── styles/                 # Global Tailwind CSS and fonts
│   │   ├── translations/           # English, Tamil, Sinhala dictionaries
│   │   └── types/                  # TypeScript interfaces
│   ├── tailwind.config.ts          # Luxury Gold & Emerald color tokens
│   └── package.json
│
├── database/
│   └── schema/
│       └── schema.mysql.prisma     # Production MySQL schema
└── README.md
```

---

## 💳 6. Marketplace Commission Logic

- Configurable global commission (default: **10.0%**)
- When an order item of **Rs. 5,000** is fulfilled:
  - **Marketplace Fee**: Rs. 500 (10%)
  - **Seller Earnings**: Rs. 4,500 (90%)
- Admin can adjust the marketplace commission at any time via the Admin Panel (`/admin/dashboard`).

---

## 🇱🇰 7. Multi-Language Support

Switch between English, Tamil, and Sinhala using the language selector on the top navigation bar:
- **English (`en`)**: Discover Muslim Fashion
- **Tamil (`ta`)**: முஸ்லிம் நாகரீக ஆடைகளைக் கண்டறியுங்கள்
- **Sinhala (`si`)**: මුස්ලිම් විලාසිතා ගවේෂණය කරන්න

---

## 🔒 8. Security Features

- Secure BCrypt password hashing (10 salt rounds)
- Stateless JWT token authentication with role verification
- Role-based authorization (`CUSTOMER`, `SELLER`, `ADMIN`)
- Helmet security HTTP headers
- Rate limiting protection against abuse
- SQL injection protection via Prisma parameterized queries
