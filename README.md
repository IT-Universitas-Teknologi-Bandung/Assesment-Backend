## **Studi Kasus 1: E-Learning Management System**

### **Deskripsi:**
Bangun sistem manajemen e-learning sederhana untuk mengelola kursus, siswa, dan progress pembelajaran.

### **Database Distribution:**
- **Database 1 (academic_db):** 
  - Table: courses, enrollments, assignments
- **Database 2 (users_db):** 
  - Table: users, user_profiles, user_sessions

### **Fitur yang Harus Diimplementasikan:**
1. **Authentication System**
   - Register (student/instructor)
   - Login dengan role-based access
   - JWT token management
   - Password reset functionality

2. **Course Management**
   - CRUD courses (instructor only)
   - Enroll/unenroll students
   - View course list dengan filtering
   - Progress tracking

3. **Assignment System**
   - Create assignments (instructor)
   - Submit assignments (student)
   - Grade assignments
   - Assignment history

### **Endpoint Requirements:**
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/courses` (dengan pagination & filter)
- `POST /api/courses` (instructor only)
- `POST /api/courses/{id}/enroll`
- `GET /api/assignments/my-submissions`
- `POST /api/assignments/{id}/submit`

### **Security Requirements:**
- Role-based middleware (student/instructor)
- File upload validation untuk assignments
- Rate limiting untuk submissions
- Input sanitization

---

## **Studi Kasus 2: Multi-Tenant Inventory Management**

### **Deskripsi:**
Sistem inventory multi-tenant untuk berbagai toko yang bisa mengelola produk, stok, dan transaksi.

### **Database Distribution:**
- **Database 1 (inventory_db):** 
  - Table: products, categories, stock_movements
- **Database 2 (business_db):** 
  - Table: tenants, users, transactions, suppliers

### **Fitur yang Harus Diimplementasikan:**
1. **Multi-Tenant Authentication**
   - Register tenant (business)
   - User registration per tenant
   - Login dengan tenant validation
   - API key management per tenant

2. **Product & Stock Management**
   - CRUD products per tenant
   - Stock in/out tracking
   - Low stock alerts
   - Category management

3. **Transaction System**
   - Record sales transactions
   - Purchase orders
   - Stock adjustment
   - Reports (daily/monthly)

### **Endpoint Requirements:**
- `POST /api/tenant/register`
- `POST /api/auth/login`
- `GET /api/products` (tenant-scoped)
- `POST /api/products`
- `PUT /api/products/{id}/stock`
- `GET /api/transactions/reports`
- `POST /api/transactions/sale`

### **Security Requirements:**
- Tenant isolation middleware
- API key authentication
- Transaction logging
- Data encryption untuk sensitive info

---

## **Studi Kasus 3: Event Booking & Ticketing System**

### **Deskripsi:**
Platform booking tiket event dengan sistem pembayaran sederhana dan manajemen kapasitas.

### **Database Distribution:**
- **Database 1 (events_db):** 
  - Table: events, venues, tickets, bookings
- **Database 2 (customers_db):** 
  - Table: users, profiles, payments, notifications

### **Fitur yang Harus Diimplementasikan:**
1. **User & Authentication**
   - Customer registration
   - Event organizer registration
   - Social login simulation
   - Profile management

2. **Event Management**
   - Create events (organizer only)
   - Set ticket types & pricing
   - Venue management
   - Event publishing/draft

3. **Booking System**
   - Browse events dengan filter
   - Ticket booking dengan seat selection
   - Payment processing simulation
   - Booking confirmation & QR code
   - Booking history

### **Endpoint Requirements:**
- `POST /api/auth/register`
- `POST /api/auth/login`
- `GET /api/events` (dengan location, date, category filter)
- `POST /api/events` (organizer only)
- `POST /api/bookings`
- `GET /api/bookings/my-tickets`
- `PUT /api/bookings/{id}/cancel`
- `GET /api/organizer/events/analytics`

### **Security Requirements:**
- QR code generation untuk tickets
- Payment webhook validation
- Booking concurrency handling
- Fraud detection untuk multiple bookings

---

## **Kriteria Penilaian untuk Ketiga Studi Kasus:**

### **Technical Implementation (40%)**
- Repository-Service pattern implementation
- Multi-database connection management
- Custom JWT without library
- OOP principles & SOLID

### **API Design & Security (30%)**
- RESTful endpoint design
- Proper HTTP status codes
- Authentication & authorization
- Input validation & sanitization
- Rate limiting implementation

### **Database & Architecture (20%)**
- Database schema design
- Query optimization
- Transaction handling
- Error handling & logging

### **Testing & Documentation (10%)**
- Postman collection completeness
- API documentation
- Docker setup
- Git workflow

**Durasi Assessment:** 4-6 jam per studi kasus
**Deliverables:** Source code, Postman collection, Docker setup, README documentation
