# Hangbiao-Zhao.github.io

<p><a href="/BasicWebDev/Final Assignment: Putting All the Pieces Together.html" target="black">Final Assignment: Putting All the Pieces Together</a></p>
<section class="volunteer-options">
    <h2>Current Opportunities</h2>

    <table class="opportunity-table">
        <thead>
            <tr>
                <th scope="col">Position</th>
                <th scope="col">Time Commitment</th>
                <th scope="col">Skills Needed</th>
                <th scope="col">Location</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Food Pantry Assistant</td>
                <td>4 hrs/week</td>
                <td>None required</td>
                <td>Main Community Center</td>
            </tr>
            <!-- More rows -->
        </tbody>
    </table>

    <form class="volunteer-form">
        <h3>Apply to Volunteer</h3>
        <label for="name">Full Name:</label>
        <input type="text" id="name" name="name" required>

        <label for="email">Email:</label>
        <input type="email" id="email" name="email" required>

        <label for="interest">Area of Interest:</label>
        <select id="interest" name="interest">
            <option value="">Select one...</option>
            <option value="food">Food Pantry</option>
            <!-- More options -->
        </select>

        <fieldset>
            <legend>Availability</legend>
            <input type="checkbox" id="weekday" name="availability" value="weekday">

