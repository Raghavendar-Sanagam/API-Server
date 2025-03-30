### Bank Branch GraphQL API

This project provides a **GraphQL API** to query bank branch details using **Flask**, **Graphene**, and **SQLAlchemy**. The API allows users to fetch bank details based on IFSC, city, branch, and other attributes.

## Features
- Retrieve **all bank branches**.
- Search for a **bank by IFSC code**.
- Filter banks based on **city, district, state, and other attributes**.
- Uses **GraphQL** for flexible and efficient data retrieval.
- **Flask** is used as the web framework, and **SQLite** as the database.
- Data is preloaded from a CSV file.
- **Publicly accessible** using **ngrok**.

## Installation

### Prerequisites
Ensure you have the following installed:
- Python (>=3.7)
- Flask
- Flask-GraphQL
- Flask-SQLAlchemy
- Graphene
- Pandas
- Pyngrok

### Steps to Install & Run
**1. Clone the Repository**
   sh
   git clone https://github.com/Raghavendar-Sanagam/API-Server.git
   cd bank-graphql-api
   
**2. Install Dependencies**
   sh
   pip install -r requirements.txt
   
**3. Run the Application**
   sh
   python app.py
   
**4. Access the GraphQL API via Public Server**
   - The application will generate a **public URL** using **ngrok**.
   - Copy the **public URL** printed in the console (e.g., `https://f2a1-34-106-117-212.ngrok-free.app/gql'.
   - Open it in your browser to access the GraphQL interface.

## GraphQL Queries

### Get All Banks
graphql
query {
  banks {
    ifsc
    bankId
    branch
    address
    city
    district
    state
    bankName
  }
}


### Get Bank by IFSC
graphql
query {
  ifsc(ifsc: "ABHY0065009") {
    ifsc
    bankId
    branch
    address
    city
    district
    state
    bankName
  }
}


### Get Banks by City
graphql
query {
  city(city: "MUMBAI") {
    ifsc
    bankId
    branch
    address
    district
    state
    bankName
  }
}

### Get Banks by Bank_Id
query {
  bankId(bankId: 11) {
    ifsc
    bankId
    branch
    address
    city
    district
    state
    bankName
  }
}

### Get Banks by Branch
query {
  branch(branch: "WADALA") {
    ifsc
    bankId
    address
    city
    district
    state
    bankName
  }
}

### Get Banks by Address
query {
  address(address: "GR. FLOOR, MADHURAM HALL, HARISHANKAR JOSHI ROAD, DAHISAR (E), MUMBAI - 400 068") {
    ifsc
    bankId
    branch
    city
    district
    state
    bankName
  }
}

### Get Banks by District
query {
  district(district: "GREATER MUMBAI") {
    ifsc
    bankId
    branch
    address
    city
    state
    bankName
  }
}

### Get Banks by State
query {
  state(state: "WEST BENGAL") {
    ifsc
    bankId
    branch
    address
    city
    district
    bankName
  }
}

### Get Banks by Bank_Name
query {
  bankName(bankName: "ALLAHABAD BANK") {
    ifsc
    bankId
    branch
    address
    city
    district
    state
  }
}


## File Structure
├── app.py                 
├── bank_branches.csv      
├── requirements.txt       
├── README.md            


## License
This project is licensed under the MIT License.

## Contributors
- **Raghavendar Sanagam** - [GitHub Profile](https://github.com/Raghavendar-Sanagam))

## Contact
For any queries, email: `raghavendarsangam@gmail.com`

