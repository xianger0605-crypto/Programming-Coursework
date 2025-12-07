Banking System User Guide

Student Name: CHIK XIANG ER

Student ID: 36271144

1. Menu & Session
   
  Features Implemented:
  
    •	Six Operations Available:
       1. Create New Bank Account
       2. Delete Bank Account
       3. Deposit Funds
       4. Withdraw Funds
       5. Transfer Money
       6. Check Account Balance
       7. Exit System
      
    •	Menu Navigation:
       o Supports numbered selections (1-7)
       o Clean, simple interface without keyword support to avoid complexity
       o Menu loops continuously until user selects Exit (Option 7)
      
    •	Session Information: 
       o System displays current date/time when started
       o Shows count of loaded accounts from database
       o Welcome message with system initialization status
      
    •	Transaction Logging:
       o All actions are recorded in database/bank_activities.log
       o Each entry includes timestamp, action type, and details
       o Log file is created automatically in "database" directory
      
2. Create New Bank Account
   
Process:

  1.	Select Option 1 from main menu
     
  2.	Input Requirements:
     
     o Customer Name: Any string (accepts spaces and special characters)
     o Identification Number: Any string format (no strict validation)
     o Account Type: "Savings" or "Current" (case-sensitive)
     o Security Code: 4-digit PIN (exactly 4 digits)
    
  3.	Account Generation:
     
     o System generates random 7-digit account number (5000000-8999999)
     o Initial balance set to RM 0.00 automatically
     o No confirmation dialog required - account created immediately
    
  4.	File Storage:
     
     o Account information saved in database/acc_XXXXXXX.txt
     o Account number added to database/accounts_list.txt
     o Transaction logged as "NEW_ACCOUNT_OPENED"
    
  5.	Confirmation:
     
     o System displays success message with new account number
     o Shows account details: number, name, type, and balance
     o Automatically returns to main menu
    
3. Delete Bank Account
   
Process:

  1.	Select Option 2 from main menu
     
  2.	Authentication Required:
     
    o	Enter account number to delete
    o	Enter 4-digit security code (PIN)
    o	Enter last 4 digits of ID number
    
  3.	Verification:
     
    o	System checks if account exists
    o	Validates security code matches stored PIN
    o	Compares last 4 digits of provided ID with stored ID
    o	No attempt limit - single attempt only
    
  4.	Deletion Process:
     
    o	Account file (acc_XXXXXXX.txt) is permanently deleted
    o	Account number removed from accounts list
    o	Transaction logged as "ACCOUNT_CLOSED"
    
  5.	Confirmation:
     
    o	Success/failure message displayed
    o	Returns to main menu automatically
    
4. Deposit Money
   
Process:

  1.	Select Option 3 from main menu
     
  2.	Account Selection:
     
     o Enter account number (must exist in system)
     o Enter 4-digit security code for authentication
    
  3.	Amount Validation:
     
     o Deposit amount must be > RM 0
     o Maximum deposit: RM 50,000 per transaction
     o Invalid amounts prompt re-entry
    
  4.	Transaction Processing:
     
     o System verifies security code
     o Updates account balance
     o Saves changes to account file
     o Transaction logged as "FUNDS_ADDED"
    
  5.	Confirmation:
      
     o ows new balance after deposit
     o Success message displayed
     o Returns to main menu
    
5. Withdraw Money
   
Process:

  1.	Select Option 4 from main menu
     
  2.	Account Authentication:
     
     o Enter account number
     o Enter 4-digit security code
    
  3.	Balance Check:
     
     o System displays current balance
     o Enter withdrawal amount
     o Amount must be ≤ current balance
     o Maximum withdrawal: RM 50,000
    
  4.	Validation Rules:
     
     o Amount must be > RM 0
     o Cannot withdraw more than available balance
     o Invalid amounts prompt re-entry
    
  5.	Transaction Processing:
      
     o Updates account balance
     o Saves changes to account file
     o Transaction logged as "FUNDS_WITHDRAWN"
    
  6.	Confirmation:
      
     o Shows remaining balance
     o Success message displayed
     o Returns to main menu
    
6. Transfer Money
   
Process:

  1.	Select Option 5 from main menu
     
  2.	Sender Authentication:
     
     o Enter sender's account number
     o Enter sender's 4-digit security code
  
  3.	Receiver Selection:
     
     o Enter recipient's account number
     o Cannot transfer to same account
     o Both accounts must exist
    
  4.	Transfer Rules:
     
     o Transfer amount: RM 0.01 to RM 50,000
     o Must have sufficient balance including fees
     o Service fees apply for cross-type transfers:
         Savings → Current: 2% fee
         Current → Savings: 3% fee
         Same type transfers: No fee
      
  5.	Transaction Processing:
      
     o Calculates total deduction (amount + fee)
     o Updates both accounts' balances
     o Saves changes to both account files
     o Transaction logged as "MONEY_TRANSFER"
    
  6.	Confirmation:
      
     o Shows transfer details
     o Displays any service fees charged
     o Shows sender's updated balance
     o Returns to main menu
    
7. Check Account Balance (NEW FEATURE)
   
Process:

  1.	Select Option 6 from main menu

  2.	Account Authentication:
     
     o Enter account number
     o Enter 4-digit security code
    
  3.	Information Display:
     
     o Shows account holder name
     o Displays account number
     o Shows ID number
     o Indicates account type (Savings/Current)
     o Displays current balance in formatted box
    
  4.	Balance Insights:
     
     o If balance is RM 0.00: Suggests making first deposit
     o If balance < RM 100.00: Warns about minimum balance
     o If balance > RM 10,000.00: Suggests premium savings
    
  5.	Transaction Logging:
      
     o Activity logged as "BALANCE_CHECKED"
     o Includes timestamp of check
    
  6.	Navigation:
      
     o Press Enter to return to main menu
     o Information stays displayed until user continues
    
