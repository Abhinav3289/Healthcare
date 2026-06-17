# Prescripto - Doctor Appointment Web App

**Prescripto** is a full-stack web application designed to make healthcare more accessible by simplifying the process of booking doctor appointments. It offers three levels of login: **Patient**, **Doctor**, and **Admin**, each with distinct features tailored to their roles. The app integrates **online payment gateways (Stripe and Razorpay)** to facilitate seamless and secure payments. Built using the **MERN stack** (MongoDB, Express.js, React.js, and Node.js), Prescripto provides an efficient, user-friendly experience for both patients and healthcare providers.

## 🛠️ Tech Stack

- **Frontend**: React.js
- **Backend**: Node.js, Express.js
- **Database**: MongoDB
- **Payment Gateways**: Stripe, Razorpay
- **Authentication**: JSON Web Token (JWT)

## 🔑 Key Features

-### 👤 Patient Portal
- **Authentication:** Secure sign-up and login with encrypted passwords.
- **Profile Management:** View and edit personal data (Name, Phone, Address, Gender, Date of Birth) and upload custom profile pictures.
- **Booking Engine:** Search and filter doctors by medical specialties, view calendar slot availability, and real-time double-booking prevention.
- **Flexible Payments:** Checkout securely using Stripe Checkout Sessions, Razorpay Orders, or select Cash on Delivery.
- **Appointment Tracking:** Monitor upcoming or past logs with instant slot-release capabilities upon cancellation.

### 🩺 Doctor Portal
- **Dedicated Dashboard:** Review overall calculated financial earnings, total unique patients treated, and a real-time list of upcoming bookings.
- **Schedule Controls:** Toggle general availability status on or off instantly.
- **Appointment Management:** Review comprehensive patient profiles and mark appointments as completed or canceled.
- **Profile Customization:** Independently adjust consulting fees, clinic addresses, and professional biographies.

### 🔑 Admin Control Panel
- **Doctor Onboarding:** Create new medical profiles, handle security configurations, and upload credentials/avatars to the cloud storage pipeline.
- **Global Dashboard Analytics:** Inspect platform counters including global user registration tallies, total operational doctors, and complete booking counts.
- **System Overrides:** Review the master directory of global bookings with permissions to issue overarching appointment cancellations.

## 🏠 Home Page

- Features a user-friendly layout where users can:
  - **Search for doctors** based on specialties.
  - **View top doctors** and their profiles.
  - Explore additional sections: About Us, Delivery Information, Privacy Policy, and Get in Touch.
- **Footer** includes navigation links: Home, About Us, Delivery Info, Privacy Policy, Contact Us.

## 🩺 All Doctors Page

- Lists all available doctors.
- Users can **filter doctors by specialty**.
- Clicking on a doctor's profile redirects to the **Doctor Appointment Page**.

## 📄 About Page

- Provides information about **Prescripto’s vision** and mission.
- **Why Choose Us** section highlights:
  - **Efficiency**: Streamlined appointment process.
  - **Convenience**: Online booking and payment.
  - **Personalization**: Tailored experience based on user preferences.
- Footer section with additional links.

## 📞 Contact Page

- Contains **office address** and contact details.
- Section to explore job opportunities.
- Footer navigation links.

## 📅 Doctor Appointment Page

- Displays detailed information about the selected doctor:
  - **Profile picture, qualification, experience**, and a brief description.
  - **Appointment booking form**: Choose date, time, and payment method.
  - Online payment options: **Cash, Stripe, or Razorpay**.
  - **Related doctors** section at the bottom.
- Users need to **create an account or log in** before booking an appointment.

## 👤 User Profile

- Accessible after login.
- Users can view and edit their profile:
  - **Upload profile picture**.
  - Update **name, email, address, gender, and birthday**.
- View list of upcoming and past appointments.
- **Logout** option available.

## 🗄️ Admin Panel

- **Dashboard**:
  - Displays statistics: **Number of doctors**, **appointments**, **patients**, and **latest bookings**.
  - Option to **cancel bookings** if needed.
- **Add Doctor**:
  - Form to add a new doctor profile (image, specialty, email, password, degree, address, experience, fees, description).
- **Doctor List**:
  - View all registered doctors with options to edit or delete profiles.
- **Appointments**:
  - List of all appointments including patient name, age, date, time, doctor name, fees.
  - Admin actions: **Cancel** or **Mark as Completed**.

## 🩺 Doctor Dashboard

- **Earnings Overview**:
  - Total earnings from completed appointments.
- **Appointments List**:
  - View detailed list of patient appointments (name, age, date, time, payment mode, status).
  - Actions: **Mark appointment as completed** or **Cancel appointment**.
- **Profile Management**:
  - Doctors can update their **profile information**, including description, fees, address, and availability status.

## 💳 Payment Integration

- Supports multiple payment methods:
  - **Cash Payment**
  - **Stripe Integration**
  - **Razorpay Integration**
- Ensures a secure and smooth payment experience for users.


## Backend Architecture Diagram
The application establishes transactional reliability by using Data Snapshots. When an appointment is booked, the system injects static object duplicates of both the userData and docData directly into the appointment ledger. This guarantees historic transactional receipts remain completely accurate even if a doctor changes their fees, address, or profile picture in the future.

## 🌐 Project Setup

To set up and run this project locally:

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-username/prescripto.git
   cd prescripto
   ```

2. **Install Dependencies**:
   ```bash
   npm install
   cd client
   npm install
   ```

3. **Environment Variables**:
   - Create a `.env` file in the root directory and add the following:
     ```env
     
     JWT_SECRET=your_jwt_secret
     # Database Link
     MONGODB_URI=mongodb+srv://<username>:<password>@cluster.mongodb.net
 
     # Static Administrative Credentials
     ADMIN_EMAIL=admin@prescripto.com
     ADMIN_PASSWORD=your_secure_admin_password

     # Cloudinary Asset Keys
     CLOUDINARY_NAME=your_cloudinary_cloud_name
     CLOUDINARY_API_KEY=your_cloudinary_api_key
     CLOUDINARY_SECRET_KEY=your_cloudinary_api_secret
     STRIPE_API_KEY=your_stripe_api_key
     RAZORPAY_API_KEY=your_razorpay_api_key
     ```

4. **Run the Application**:
   ```bash
   npm run dev
   ```

## 📦 Folder Structure

```plaintext
prescripto/
├── client/              # Frontend Architecture (React.js SPA)
├── server/              # Backend Architecture (Node.js & Express.js)
│   ├── config/          # Database & Cloudinary service initializations
│   ├── controllers/     # Core Business logic handlers (Admin, Doctor, User)
│   ├── middleware/      # JWT Identity verification & Multer file parsers
│   ├── models/          # Mongoose Schemas (User, Doctor, Appointment)
│   └── routes/          # Express API Endpoint mappings
└── .env                 # Application Environment flags
```

## 🤝 Contributing

We welcome contributions! Please feel free to submit issues, fork the repository, and open pull requests.


## 🌟 Acknowledgements

- Thanks to the developers and contributors of MongoDB, Express.js, React.js, Node.js, Stripe, and Razorpay for their fantastic tools and libraries.

---

