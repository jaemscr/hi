# Relationship Website Mobile V2

A fun and interactive mobile website built with **React, Vite, Tailwind CSS, and Express.js** as seen on social media

## 🚀 Installation

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/rheinatamara/relationship_website_v2.git
cd relationship_website_v2
```

### 2️⃣ Install Dependencies

1. Ensure you have **[Node.js](https://nodejs.org/)** installed.
2. Open 2 terminals and run :

terminal 1:

```bash
cd client
npm install
npm run dev
```

terminal 2:

```bash
cd server
npm install
npm run dev
```

### 3️⃣ Access the Application

Open your browser and navigate to **[http://localhost:5173/](http://localhost:5173/)** to view the application.

- Inspect the browser tab and set the dimensions to any mobile view

---

## 🎨 Making the Page Personal to You

---

### **1. FRONTEND SIDE**

This project allows **full customization** through the `config.js`.

### **1️⃣ Editing Text & Titles**

All customizable text (titles, messages, prompts) is in `config/config.js`. **You can edit:**

- Quiz questions and answers
- Canvas colors or settings

Simply **open `config/config.js`** and edit the values.

### **2️⃣ Adding Personal Pictures or Gifs**

To add your own gifs/images, place them in **`src/assets/`**

📌 **Quiz Gifs** (used in the Quiz page):

- Location: `src/assets/gifs`
- Naming format: `gif1.png`, `gif2.png`, `gif3.png`, etc.

## 🖌️ Styling

This project uses **[Tailwind CSS](https://tailwindcss.com/)** for styling.

- You can modify styles in `tailwind.config.js`
- Add or remove Tailwind classes in `.jsx` files

---

### **2. BACKEND SIDE**

### **1️⃣ Setting Up Environment Variables**

- Go to your **[Google Security Settings](https://myaccount.google.com/security)** page.
- Enable 2-Step Verification if it’s not already enabled.

### **2️⃣ Generate an App Password**

- After enabling 2-Step Verification, go to the **[App Passwords](https://myaccount.google.com/u/3/apppasswords)** section.
- Generate an App Password for the application.

### **3️⃣ Configure .env File**

- Rename the `.env.example` file in the server folder to `.env`
- Open the **.env** file and add your Gmail credentials:

```js
EMAIL=your-email@gmail.com
EMAIL_PASS=your-app-password
PORT=your-port
```

- Replace `your-email@gmail.com` with your Gmail address, `your-app-password` with the app password you generated and `your-port` with your development port

### **4️⃣ Configure Nodemailer**

- go to `app.js` in your server folder
- Change the `to` field in the `mailOptions` object to the email address where you want to receive the files. **For example:**

```js
let mailOptions = {
  from: process.env.EMAIL_USER,
  to: "your-email@gmail.com", // change this to your email
  subject: "Drawings and letter for you",
  text: `${message}\n\n${score}`,
  attachments: attachments,
};
```

## Important notes:

- Make sure your `.env` file contains the correct `EMAIL_USER` and `EMAIL_PASS` (App Password) for the sender email.
- If you’re using Gmail, ensure you’ve enabled **2-Step Verification** and generated an **App Password** as described in the Backend Setup section.

---

## 🚀 **Deployment**

To deploy this project, you’ll need to deploy both the **client (frontend)** and **server (backend)** separately. Below are the general steps:

### **1️⃣ Deploy the Client (Frontend)**

The frontend is built with Vite. You can deploy it using platforms like **[Vercel](https://vercel.com/)** or **[Netlify](https://www.netlify.com/)**.

- Ensure your entire project (including the client and server folders) is pushed to a GitHub repository.
- Sign up for Vercel or Netlify.
- Connect your GitHub repository to the platform.
- During the setup, specify the `client` folder as the root directory for the frontend.
- Follow the deployment steps (usually automatic).
- Your frontend will be live at a provided URL.

**For detailed instructions, refer to the official Vite deployment guide:**

👉 [Vite Deployment Guide](https://vite.dev/guide/static-deploy.html)

---

### **2️⃣ Deploy the Server (Backend)**

The backend is built with Express.js. You can deploy it using platforms like **[Render](https://render.com/)** or **[Railway](https://railway.com/)**.

- Ensure your entire project (including the client and server folders) is pushed to a GitHub repository.
- Sign up for Render or Railway.
- Connect your GitHub repository to the platform.
- During the setup, specify the `server` folder as the root directory for the backend.
- Add your environment variables (from `.env`) in the platform’s settings.
- Follow the deployment steps.
- Your backend will be live at a provided URL.

**For detailed instructions, refer to the official Express.js deployment guide:**

👉 [Express.js Deployment Guide](https://expressjs.com/en/advanced/best-practice-performance.html#deployment)

---

### **3️⃣ Update the API Configuration**

After deploying the backend, update the baseURL in the `config.js` file to point to your live backend URL. For example:

```js
api: {
  baseURL: "https://your-backend-url.com", // Replace with your live backend URL
  sendEmailEndpoint: "/send-email",
},
```

---

## 📜 **Summary**

- Deploy the **frontend** using **[Vercel](https://vercel.com/)** or **[Netlify](https://www.netlify.com/)**, and specify the `client` folder as the root directory.
- Deploy the **backend** using **[Render](https://render.com/)** or **[Railway](https://railway.com/)**, and specify the `server` folder as the root directory.
- Update the `baseURL` in `config.js` to point to your live backend.

---

## 🔧 **Important Notes**

1️⃣ Since the `frontend` and `backend` are in the same repository, you’ll need to specify the correct folder **(client or server)** during deployment.

2️⃣ Ensure your backend is properly deployed and running before updating the `baseURL` in the frontend configuration.

For any questions, **open an issue** on the repository❤️
