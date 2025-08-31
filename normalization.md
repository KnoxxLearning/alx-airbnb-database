🚨 Identified Redundancies & Violations

🔁 Repetition of Data

No major repetition of data across tables.

❌ Violations of Normal Forms

1NF Violation: None detected. All fields are atomic.

2NF Violation: None detected. All non-key attributes depend on the whole primary key.

3NF Violation: Potential transitive dependency in Property table — host_id references User, but host_name and host_email are not present, so no violation.

✅ Normalization Steps to Achieve 3NF

🔹 Step 1: First Normal Form (1NF)

Ensure atomicity: All fields are atomic and well-defined.

🔹 Step 2: Second Normal Form (2NF)

Ensure all non-key attributes are fully functionally dependent on the primary key.

Composite keys are avoided; all tables use single-column primary keys.

🔹 Step 3: Third Normal Form (3NF)

Eliminate transitive dependencies:

All attributes are directly dependent on the primary key.

Foreign keys are used appropriately to link related entities.

🧱 Final Normalized Schema

User

  user_id (PK)
  
  first_name
  
  last_name
  
  email
  
  password_hash
  
  phone_number
  
  role
  
  created_at

Property

  property_id (PK)
  
  host_id (FK → User)
  
  name
  
  description
  
  location
  
  pricepernight
  
  created_at
  
  updated_at

Booking

  booking_id (PK)
  
  property_id (FK → Property)
  
  user_id (FK → User)
  
  start_date
  
  end_date
  
  total_price
  
  status
  
  created_at

Payment

  payment_id (PK)
  
  booking_id (FK → Booking)
  
  amount
  
  payment_date
  
  payment_method

Review

  review_id (PK)
  
  property_id (FK → Property)
  
  user_id (FK → User)
  
  rating
  
  comment
  
  created_at

Message

  message_id (PK)
  
  sender_id (FK → User)
  
  recipient_id (FK → User)
  
  message_body
  
  sent_at
