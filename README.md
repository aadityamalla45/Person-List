<!DOCTYPE html>     
<html>
<head>
    <title>Person List</title>
    <!-- (Aaditya Malla) -->
</head>
<body>
    <h1>Add a Person</h1>
   First name: <input type="text" id="firstNameInput" placeholder="First Name"><br>

   Last name <input type="text" id="lastNameInput" placeholder="Last Name"><br>

    <button onclick="addPerson()">Add to list</button>
    <div id="output"></div>

    <script>
        // Array to store person 
        let people = [];

        //  add person object to the array and update the output
        function addPerson() {
            // Get first and last names from input fields
            let firstName = document.getElementById('firstNameInput').value.trim();
            let lastName = document.getElementById('lastNameInput').value.trim();

            // Check if both fields are not empty
            if (firstName !== '' && lastName !== '') {
                // Create person object
                let person = {
                    firstName: firstName,
                    lastName: lastName
                };

                // Add person object to the array
                people.push(person);

                // Update output with JSON string of the person 
                document.getElementById('output').innerHTML += JSON.stringify(person) + '<br>';

                // Clear input fields
                document.getElementById('firstNameInput').value = '';
                document.getElementById('lastNameInput').value = '';
            } else {
                alert('Please enter both first and last names.');
            }
        }
    </script>
</body>
</html>
