<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>UNIVERSITY ADMISSION APPLICATION </title>
    <style>
       
        body {
           font-family: Arial, sans-serif;
           background: linear-gradient(to right, #f7f7f7, #e1e1e1); 
           margin: 0;
           padding: 0;
           display: flex;
           justify-content: center;
           align-items: center;
           height: 100vh;
           box-sizing: border-box;
         }

       
       .form-container {
           background-color: #ffffff;
           padding: 40px;
           border-radius: 8px;
           box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
           width: 450px; 
           box-sizing: border-box;
           max-width: 100%;
          }

       
       h2 {
          text-align: center;
          color: #333;
          font-size: 28px; 
          margin-bottom: 20px;
         }

      
    label {
        font-size: 14px;
        color: #555;
        margin-bottom: 5px;
        display: block;
       }

       input[type="text"], input[type="email"], input[type="date"], input[type="number"], select {
          width: 100%;
          padding: 12px; 
          margin: 10px 0 20px 0; 
          border: 1px solid #ddd;
          border-radius: 4px;
          font-size: 14px;
         }

     
     input[type="submit"] {
         width: 100%;
         padding: 12px;
         background-color: #4CAF50;
         color: white;
         font-size: 16px;
         border: none;
         border-radius: 4px;
         cursor: pointer;
         transition: background-color 0.3s ease;
        }

      input[type="submit"]:hover {
           background-color: #45a049;
          }

      
      .error {
          color: red;
          font-size: 12px;
         }

        
        @media (max-width: 768px) {
        .form-container {
             width: 85%; 
           }
         }

       @media (max-width: 400px) {
       .form-container {
             width: 95%; 
           }
         }

     

    </style>
</head>
<body>

    <div class="form-container">
        <h2>UNIVERSITY ADMISSION APPLICATION </h2>

        <form id="admissionForm" onsubmit="return validateForm()">

            <!-- Personal Information -->
            <label for="name">Full Name:</label>
            <input type="text" id="name" name="name" required>
            <div class="error" id="nameError"></div>

            <label for="dob">Date of Birth:</label>
            <input type="date" id="dob" name="dob" required>
            <div class="error" id="dobError"></div>

            <label for="email">Email Address:</label>
            <input type="email" id="email" name="email" required>
            <div class="error" id="emailError"></div>

            <label for="phone">Phone Number:</label>
            <input type="number" id="phone" name="phone" required>
            <div class="error" id="phoneError"></div>

            <!-- Program Information -->
            <label for="program">Program of Interest:</label>
            <select id="program" name="program" required>
                <option value="">Select Program</option>
                <option value="Computer Science">Computer Science</option>
                <option value="Business Administration">Business Administration</option>
                <option value="Mechanical Engineering">Mechanical Engineering</option>
                <option value="Electrical Engineering">Electrical Engineering</option>
            </select>
            <div class="error" id="programError">

            <!-- Submit Button -->
            <input type="submit" value="Submit Application">

        </form>
    </div>

    <script>
        
        function validateForm() {
            let isValid = true;

            
            document.getElementById("nameError").textContent = "";
            document.getElementById("dobError").textContent = "";
            document.getElementById("emailError").textContent = "";
            document.getElementById("phoneError").textContent = "";
            document.getElementById("programError").textContent = "";

            
            const name = document.getElementById("name").value;
            if (name.trim() === "") {
                document.getElementById("nameError").textContent = "Full Name is required.";
                isValid = false;
            }

            
            const dob = document.getElementById("dob").value;
            if (dob === "") {
                document.getElementById("dobError").textContent = "Date of Birth is required.";
                isValid = false;
            }

            
            const email = document.getElementById("email").value;
            const emailPattern = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$/;
            if (email.trim() === "" || !emailPattern.test(email)) {
                document.getElementById("emailError").textContent = "Please enter a valid email address.";
                isValid = false;
            }

            
            const phone = document.getElementById("phone").value;
            if (phone.trim() === "" || phone.length < 10) {
                document.getElementById("phoneError").textContent = "Please enter a valid phone number.";
                isValid = false;
            }

            
            const program = document.getElementById("program").value;
            if (program === "") {
                document.getElementById("programError").textContent = "Please select a program.";
                isValid = false;
            }

            
            if (isValid) {
                alert("Application submitted successfully!");
                
            }

            return isValid; 
        }
    </script>

</body>
</html>
