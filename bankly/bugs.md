#Bugs

1.test for 'POST /auth/login' did not check for admin login & access denial; added tests to check for login with admin/incorrect credentials & updated corresponding route to 'await' authentication credentials
2.test suite for 'GET /users/:username did not check for querying non-existing user; added test and 'throw' clause to corresponding User#get method
3.test suite for 'PATCH /:username' does not test for a user trying to update their own information; removed middleware requireAdmin.
4.test suite for 'PATCH /:username' does not filter out change request for 'admin' fields; added statement to throw 'unauthorized' error when users try to change the admin status
5.test suite for 'DELETE /:username' does not test case when an admin tries to delete a non-existant user; added test and corresponding route to 'await' asynchronous User#delete method
