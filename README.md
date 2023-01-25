# moleculer-fetch
A simple moleculer fetch wrapper module

Fetch request

```javascript
const requestOptions = {
    method: 'POST',
    headers: { 'Content-Type': 'application/json' },
    body: JSON.stringify({ title: 'Native Fetch POST Request Example' })
};
fetch('https://jsonplaceholder.typicode.com/posts', requestOptions)
    .then(async response => {
        const data = await response.json();

        // check for error response
        if (!response.ok) {
            // get error message from body or default to response status
            const error = (data && data.message) || response.status;
            return Promise.reject(error);
        }

        console.log('Success!', data);
    })
    .catch(error => {
        console.error('There was an error!', error);
    });
```
