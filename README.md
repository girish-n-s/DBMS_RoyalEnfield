# Royal Enfield Bike Purchase Portal

A dynamic web-based portal to browse and view Royal Enfield bikes available across different branches. The platform showcases bikes with specifications, allows users to view branch and manager information, and is backed by a MySQL database.

---

## 📌 Features

- Display of Royal Enfield branches with location and manager details
- View bikes available in a specific branch
- Show bike specs like name, color, engine CC, price, and photo
- Backend powered by Flask and MySQL
- Organized code structure with Flask templating (Jinja2)
- Responsive frontend using HTML, CSS, and optional JavaScript

---

## 🛠 Tech Stack

- **Frontend:** HTML, CSS, JavaScript
- **Backend:** Python (Flask)
- **Database:** MySQL
- **Templating Engine:** Jinja2

---

## 🚀 How to Run the Project Locally

```bash
# Step 1: Clone this repository
git clone https://github.com/yourusername/royal-enfield-portal.git
cd royal-enfield-portal

# Step 2: Create and activate virtual environment (optional)
python -m venv venv
source venv/bin/activate  # or venv\Scripts\activate on Windows

# Step 3: Install dependencies
pip install -r requirements.txt

# Step 4: Import the database
# Open MySQL and run the SQL script
mysql -u root -p
> SOURCE royal_enfield.sql;

# Step 5: Run the Flask app
python app.py


#Project Structure
royal-enfield-portal/
│
├── static/
│   ├── css/
│   │   └── style.css
│   ├── js/
│   │   └── script.js  # if any
│   └── images/
│       └── sample_bike.jpg  # optional: use URLs instead
│
├── templates/
│   ├── index.html          # Homepage with branches
│   └── branch_bikes.html   # Bikes under a selected branch
│
├── royal_enfield.sql       # DB schema & sample data
├── app.py                  # Flask application
├── requirements.txt        # Python packages
└── README.md               # This file

🧱 Database Schema

1. branch

Field	Type	Description
branch_ID	INT (PK)	Unique branch ID
branch_name	VARCHAR(100)	Name of the branch
location	VARCHAR(100)	Branch location
manager_id	INT (FK)	Links to employee table

2. employee

Field	Type	Description
employee_ID	INT (PK)	Employee ID
first_name	VARCHAR(50)	Manager's first name
last_name	VARCHAR(50)	Manager's last name
email	VARCHAR(100)	Manager email
ph_no	VARCHAR(15)	Phone number


3. bike

Field	Type	Description
bike_ID	INT (PK)	Unique ID
name	VARCHAR(100)	Name of the bike
colour	VARCHAR(50)	Color
CC	INT	Engine capacity
MRP	DECIMAL(10, 2)	Price
image	VARCHAR(255)	Image filename or URL
branch_id	INT (FK)	Linked to the branch
