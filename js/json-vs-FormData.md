# Passing Data: JSON Format or FormData Objects?

In a React project, data transmission between the frontend and backend commonly employs two different approaches: JSON format and FormData objects. There are distinct differences in how data is passed between them, and below I will explain these differences in detail.
# JSON Format
JSON (JavaScript Object Notation) is a lightweight data interchange format commonly used for data transmission between frontend and backend.

In React projects, JSON format is typically used to transmit structured data objects. You can use JSON.stringify() to convert JavaScript objects into JSON strings and JSON.parse() to parse JSON strings into JavaScript objects.

- Pros:
  - Structured data: JSON format is suitable for transmitting structured data such as objects, arrays, etc.
  - Easy parsing: JSON strings can be easily parsed into JavaScript objects, making data processing on the frontend more flexible.
- Cons: 
  - Unable to transmit files directly: JSON format cannot directly transmit file data. If file transmission is required, you need to convert the file into Base64 encoding or use other methods.
# FormData Objects
FormData is an object used to construct form data, commonly used for implementing file uploads and other form-related functionalities.
- Pros:
  - Supports file uploads: FormData objects can easily handle file uploads without manually encoding file data.
  - Suitable for form data: FormData objects are commonly used to handle form data, making it easy to process complex form data.
- Cons: 
  - Not suitable for non-form data: FormData objects are primarily used for handling form data and are not suitable for structured JSON data.

In summary, JSON format is suitable for transmitting structured data objects and is convenient for frontend parsing and 
handling, while FormData objects are suitable for transmitting form data, especially for file uploads. 