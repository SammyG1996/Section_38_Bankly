- BUG #1: authUsers() in middleware.js
- Its should not allow authentication if the token is passed in through the query params. This is NOT best practice and as it should be included in the headers for saftey. 


- BUG #2: authUsers() in middleware.js
- It should not just decode the JWT but should verify that the token has not been tampered with by using jwt.verify(). 

- BUG #3: update() in users.js in the Models folder
- The hased PW should not be returned to the user when you update the database. This is unessesary and could pose a risk. 


- BUG #4: update() in users.js in the Models folder
- It should hash the password BEFORE sending it to the database. This is to ensure that in the event someone intercepts, the password is already encypted and cant be read. ****I NEED TO WRITE TESTS FOR THIS ****


- BUG #5: CORS is not implemented in app.js
- CORS should be implemented because in the real world, if this banking application was implemented it could cause errors on the client side and they might be denied access to our server since there are on a different port of origin.   


- BUG #6: router.patch route in routes/users.js
- It would not allow users to update themselves because it had the "requireAdmin" middleware. I removed the middleware and added a simple logic to ensure that only admins can change admin status. 