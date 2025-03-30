# Bank Branch GraphQL API

This project provides a **GraphQL API** to query bank branch details using **Flask**, **Graphene**, and **SQLAlchemy**. The API now supports **edges and nodes** structure for better pagination, along with **limit and offset** for optimized data retrieval.

## Features
- Retrieve **all bank branches**.
- Search for a **bank by IFSC code**.
- Filter banks based on **city, district, state, and other attributes**.
- **Pagination support** using `edges`, `nodes`, `limit`, and `offset`.
- Uses **GraphQL** for flexible and efficient data retrieval.
- **Flask** as the web framework, and **SQLite** as the database.
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
cd API-Server


**2. Install Dependencies**
sh
pip install -r requirements.txt


**3. Run the Application**
sh
python app.py


**4. Access the GraphQL API via Public Server**
- The application will generate a **public URL** using **ngrok**.
- Copy the **public URL** printed in the console (e.g., `https://f2a1-34-106-117-212.ngrok-free.app/gql`).
- Open it in your browser to access the GraphQL interface.

## GraphQL Queries with Edges & Nodes

### Get All Banks 
graphql
query {
  banks(limit: 5, offset: 10) {
    edges {
      node {
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
  }
}


### Get Bank by IFSC
graphql
query {
  ifsc(ifsc: "ABHY0065009") {
    edges {
      node {
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
  }
}

### Get Banks by Bank_Id
query {
  bankId(bankId: 11, limit: 8) {
    edges {
      node {
        ifsc
        bank_id
        branch
        address
        city
        district
        state
        bank_name
      }
    }
  }
}

### Get Banks by Branch
query {
  branch(branch: "THANE", limit: 9) {
    edges {
      node {
        ifsc
        bank_id
        branch
        address
        city
        district
        state
        bank_name
      }
    } 
  }
}

### Get Banks by Address
query {
  address(address: "KMSPM'S SCHOOL, WADIA ESTATE, BAIL BAZAR-KURLA(W), MUMBAI-400070") {
    edges {
      node {
        ifsc
        bank_id
        branch
        address
        city
        district
        state
        bank_name
      }
    }
    
  }
}


### Get Banks by City
graphql
query {
  city(city: "MUMBAI", limit: 3) {
    edges {
      node {
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
  }
}


### Get Banks by State
graphql
query {
  state(state: "WEST BENGAL", limit: 4, offset: 2) {
    edges {
      node {
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
  }
}

### Get Banks by Bank_Name
query {
  bankName(bankName: "THE AKOLA DISTRICT CENTRAL COOPERATIVE BANK",limit : 10,offset:4) {
    edges {
      node {
        ifsc
        bank_id
        branch
        address
        city
        district
        state
        bank_name
      }
    }
    
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
- **Raghavendar Sangam** - [GitHub Profile](https://github.com/Raghavendar-Sanagam)

## Contact
For any queries, email: `raghavendarsangam@gmail.com`

