****GET /loginfailtotal****

**Functional cases:**

1.  Validate that the endpoint returns data for all users when no parameters are specified.
    
2.  Verify that the endpoint returns data for the specified user.
    
3.  Ensure that only users with failed login attempts above the specified fail\_count are returned.
    
4.  Ensure that endpoint returns no more than fetch\_limit entities.
    
5.  Test with very high values for fetch\_limit to check the system has validation for this parameter.
    
6.  Test using a combination of parameters to verify that the endpoint correctly applies multiple filters.
    

**Error handling and negative tests:**

1.  Test with invalid (not existing) user\_name to ensure the system handles it correctly.
    
2.  Test with negative or non-integer values for fail\_count and fetch\_limit to verify that the endpoint responds with appropriate error messages.
    
3.  Tests with very high values for fetch\_limit, fetch\_count - more than int32 to make sure the endpoint responds with appropriate error messages.
    

**Security tests:**

1.  Verify that the endpoint has proper security measures in place to prevent unauthorized access.
    
2.  Test for SQL injection vulnerability through the user\_name parameter.
    

****PUT /resetloginfailtotal****

**Functional cases:**

1.  Validate that the failed login count is reset for the specified user.
    
2.  After resetting, a subsequent GET request should confirm that the failed login count has been reset.
    

**Error handling and negative tests:**

1.  Attempt to reset the failed login count without specifying a Username to verify that the endpoint does not proceed with the action and returns a suitable error message.
    
2.  Test with invalid (not existing) user\_name to ensure the system handles it correctly.
    

**Security tests:**

1.  Verify that the endpoint has proper security measures in place to prevent unauthorized access.
    
2.  Test for SQL injection vulnerability through the Username parameter.
