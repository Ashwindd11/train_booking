<!DOCTYPE html>
<html>
<head>
    <title>Train Ticket Booking</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .container {
            max-width: 600px;
            margin: 0 auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            background-color: #f9f9f9;
        }
        h2 {+
            text-align: center;
        }
        label, input {
            display: block;
            width: 100%;
            margin: 10px 0;
        }
        button {
            display: block;
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            background-color: #28a745;
            color: #fff;
            border: none;
            border-radius: 5px;
        }
        table {
            width: 100%;
            margin: 20px 0;
            border-collapse: collapse;
        }
        th, td {
            padding: 10px;
            border: 1px solid #ddd;
        }
        th {
            background-color: #f2f2f2;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Train Ticket Booking</h2>
        <form id="bookingForm">
            <label for="name">Name:</label>
            <input type="text" id="name" required>

            <label for="age">Age:</label>
            <input type="number" id="age" required>

            <label for="train">Train:</label>
            <input type="text" id="train" required>

            <label for="departure">Departure:</label>
            <input type="text" id="departure" required>

            <label for="destination">Destination:</label>
            <input type="text" id="destination" required>

            <button type="submit">Book Ticket</button>
        </form>

        <h2>Booked Tickets</h2>
        <table id="ticketsTable">
            <thead>
                <tr>
                    <th>Name</th>
                    <th>Age</th>
                    <th>Train</th>
                    <th>Departure</th>
                    <th>Destination</th>
                </tr>
            </thead>
            <tbody>
                <!-- Booked tickets will appear here -->
            </tbody>
        </table>
    </div>

    <script>
        document.getElementById('bookingForm').addEventListener('submit', function(event) {
            event.preventDefault();

            const name = document.getElementById('name').value;
            const age = document.getElementById('age').value;
            const train = document.getElementById('train').value;
            const departure = document.getElementById('departure').value;
            const destination = document.getElementById('destination').value;

            const ticketsTable = document.getElementById('ticketsTable').getElementsByTagName('tbody')[0];
            const newRow = ticketsTable.insertRow();

            const cell1 = newRow.insertCell(0);
            const cell2 = newRow.insertCell(1);
            const cell3 = newRow.insertCell(2);
            const cell4 = newRow.insertCell(3);
            const cell5 = newRow.insertCell(4);

            cell1.innerText = name;
            cell2.innerText = age;
            cell3.innerText = train;
            cell4.innerText = departure;
            cell5.innerText = destination;

            document.getElementById('bookingForm').reset();
        });
    </script>
</body>
</html>
