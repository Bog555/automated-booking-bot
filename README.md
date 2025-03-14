# automated-booking-bot
Automated bot for monitoring and booking clients for rare slots.
**Automated Bot for Monitoring and Booking Clients for Rare Slots**

### **Problem Description**

The company faced significant challenges in booking clients for online system slots. The main problems included:

- **Rarity and fast disappearance of slots** – available slots were infrequent and filled almost instantly.
- **Strong anti-automation protection** – the website used hidden Google reCAPTCHA, blocking automation tools like Selenium, SeleniumBase, Playwright, and Puppeteer, preventing form filling and access to the user account.
- **Short user sessions** – after logging in, users had limited time before the system automatically logged them out.
- **Account blocking after multiple attempts** – exceeding **three unsuccessful login attempts** resulted in account suspension.
- **Lack of effective monitoring** – the company could not track slot availability and register clients efficiently.

### **Developed Solution**

To automate the monitoring and booking process, a Python-based system was developed that:

1. **Successfully bypassed Google hidden reCAPTCHA, enabling automated login and session maintenance.**
2. **Session maintenance and slot monitoring**

   The system periodically sent **POST and GET requests** with dynamic headers and time delays to prevent premature session termination. However, since frequent requests still triggered server blocking, a method was implemented to retrieve data every **2 seconds** over an extended period without triggering restrictions.
3. **Due to account deletions over a short period, a fully automated system was developed to create new accounts, bypassing CAPTCHA, retrieving the activation code from an email inbox, and activating the account for immediate use.**
4. **Bypassed CAPTCHA and automated client booking**

   When a free slot was detected:
   - The system **sent CAPTCHA challenges to a third-party API for resolution**.
   - Received a token and used it to bypass protection.
   - Automatically booked the client.
5. **Automated client booking process.**
6. **Sent real-time notifications via a Telegram bot, providing clients with slot availability and successful booking confirmations.**

### **Technical Implementation**

#### **Technology Stack**

**Programming Language:** Python\
**Development Environment:** PyCharm\
**Database:** SQLite\
**Main Libraries and Tools:**

- **Parsing and Automation:** `selenium`, `beautifulsoup4`, `requests`, `httpx`
- **Telegram Integration:** `aiogram`, `telethon`
- **Asynchronous Operations:** `asyncio`, `aiosqlite`
- **CAPTCHA Solving:** Third-party API services
- **Web Data Processing:** `lxml`, `cssselect`
- **Proxy and Anti-blocking Measures:** `PySocks`, `proxy-rotation`
- **Logging and Debugging:** `logging`, `pylint`

#### **1. CAPTCHA Bypass**

At the first stage, the system used Selenium to log into the website and successfully bypassed Google hidden reCAPTCHA through an internally developed method, without relying on third-party CAPTCHA-solving services. This innovative approach allowed automated login and session maintenance.

#### **2. Session Maintenance**

The system periodically sent **POST and GET requests** with dynamic headers and delays to prevent premature session termination.

#### **3. Automatic Account Registration**

Since accounts were blocked after a few days, an automated mechanism was developed to:

- Register a new account on the website.
- Retrieve the activation link from the email inbox.
- Confirm account activation.

#### **4. Slot Monitoring**

The system checked for available slots every **2 seconds**, using **optimized parsing techniques** to reduce server load and avoid detection.

#### **5. CAPTCHA Handling and Client Booking**

If a free slot was found:

- The system **sent the CAPTCHA to a third-party API**.
- Retrieved a token and used it to bypass the challenge.
- Automatically booked the client.

#### **6. Telegram Integration**

Clients interacted with the system via a Telegram bot:

- Entering login credentials.
- Receiving notifications about available slots.
- Getting confirmation of successful booking.

### **Conclusion**

The developed tool fully automated the monitoring and booking process for rare slots, significantly improving the company’s efficiency and eliminating manual work. The system successfully handled complex challenges such as **CAPTCHA bypass, session maintenance, proxy rotation, and dynamic blocking prevention**.

