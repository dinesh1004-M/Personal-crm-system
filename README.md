# Personal-crm-system
A web-based Personal CRM System for managing contacts, customers, leads, tasks, follow-ups, and communication history.
<!DOCTYPE html>
<html>
<head>
    <title>Personal CRM System</title>
    <style>
        body{
            font-family:Arial,sans-serif;
            background:#f4f4f4;
            margin:20px;
        }

        .container{
            max-width:900px;
            margin:auto;
            background:white;
            padding:20px;
            border-radius:10px;
        }

        h1{
            text-align:center;
        }

        input{
            width:100%;
            padding:10px;
            margin:8px 0;
        }

        button{
            padding:10px 20px;
            background:#007bff;
            color:white;
            border:none;
            cursor:pointer;
        }

        table{
            width:100%;
            margin-top:20px;
            border-collapse:collapse;
        }

        th,td{
            border:1px solid #ddd;
            padding:10px;
        }

        th{
            background:#007bff;
            color:white;
        }
    </style>
</head>
<body>

<div class="container">

<h1>Personal CRM System</h1>

<h3>Add Contact</h3>

<input type="text" id="name" placeholder="Customer Name">

<input type="email" id="email" placeholder="Email">

<input type="text" id="phone" placeholder="Phone Number">

<button onclick="addContact()">Add Contact</button>

<table>
<thead>
<tr>
<th>Name</th>
<th>Email</th>
<th>Phone</th>
</tr>
</thead>

<tbody id="contactTable">
</tbody>
</table>

</div>

<script>

let contacts = [];

function addContact(){

    const name =
    document.getElementById("name").value;

    const email =
    document.getElementById("email").value;

    const phone =
    document.getElementById("phone").value;

    if(name === "" || email === "" || phone === ""){
        alert("Please fill all fields");
        return;
    }

    contacts.push({
        name,
        email,
        phone
    });

    displayContacts();

    document.getElementById("name").value="";
    document.getElementById("email").value="";
    document.getElementById("phone").value="";
}

function displayContacts(){

    let table =
    document.getElementById("contactTable");

    table.innerHTML="";

    contacts.forEach(contact => {

        table.innerHTML += `
        <tr>
            <td>${contact.name}</td>
            <td>${contact.email}</td>
            <td>${contact.phone}</td>
        </tr>
        `;
    });
}

</script>

</body>
</html>
