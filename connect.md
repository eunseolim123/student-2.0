<script>
const apiUrl = 'http://127.0.0.1:8086'; // Replace with the actual API URL
        // Make an HTTP GET request to the API
fetch(apiUrl)
    .then(response => response.json()) // Parse the JSON response
    .then(data => {
        // Organize the data into a dictionary
        const organizedData = {
            Login_api: {
                url_prefix: '/api/Login',
                LoginAPI: {
                    get: {
                        description: 'Retrieve all Logins from the database',
                        url: '/api/Login',
                        method: 'GET',
                        data: data, // Include the retrieved data here
                        mode: "cors"
                    },
                },
            },
            LoginListAPI: {
                LoginListAPI: {
                    get: {
                        description: 'Retrieve all Logins from the database',
                        url: '/api/Login',
                        method: 'GET',
                        data: data, // Include the retrieved data here
                        mode: "cors"
                    },
                },
            },
        };
        // Now, you have the organized data in the "organizedData" dictionary
        Data = organizedData.Login_api.LoginAPI.get.data; //data[id].Login_name, image whatever u may need,
</script>