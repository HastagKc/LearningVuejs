# Form in Vue
Creating forms in Vue.js with `<script setup>` syntax provides a modern and efficient way to handle user inputs, validation, and form submissions. This guide explains how to set up a basic form component, validate inputs, and submit data using the `<script setup>` syntax in Vue 3.

## Step-by-Step Guide to Creating a Form in Vue.js with `<script setup>`

### 1. Set Up a New Vue Component

Create a new file for your component, such as `FormComponent.vue`, and define the basic structure of your form.

```vue
<template>
  <form @submit.prevent="handleSubmit">
    <div>
      <label for="name">Name:</label>
      <input type="text" id="name" v-model="formData.name" />
      <span v-if="errors.name">{{ errors.name }}</span>
    </div>

    <div>
      <label for="email">Email:</label>
      <input type="email" id="email" v-model="formData.email" />
      <span v-if="errors.email">{{ errors.email }}</span>
    </div>

    <div>
      <label for="message">Message:</label>
      <textarea id="message" v-model="formData.message"></textarea>
      <span v-if="errors.message">{{ errors.message }}</span>
    </div>

    <button type="submit">Submit</button>
  </form>
</template>

<script setup>
import { reactive } from 'vue';

const formData = reactive({
  name: '',
  email: '',
  message: ''
});

const errors = reactive({
  name: '',
  email: '',
  message: ''
});

const validateForm = () => {
  errors.name = formData.name ? '' : 'Name is required.';
  errors.email = formData.email && /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(formData.email) ? '' : 'Valid email is required.';
  errors.message = formData.message ? '' : 'Message is required.';

  return !errors.name && !errors.email && !errors.message;
};

const handleSubmit = () => {
  if (validateForm()) {
    alert('Form submitted successfully!');
    console.log('Submitted Data:', formData);
    Object.keys(formData).forEach(key => formData[key] = '');
  }
};
</script>
```

### Explanation of the Code

#### Template Section

- The `@submit.prevent="handleSubmit"` directive prevents the default form submission (page reload) and calls the `handleSubmit` function.
- Each input field uses `v-model` to bind to `formData`, a reactive object that holds the values of each form field.
- Error messages are conditionally displayed using `v-if`, which checks if there is a corresponding error message in the `errors` object.

#### Script Section

1. **Imports**: 
   - Import `reactive` from Vue to create reactive state objects that store form data and validation errors.
   
2. **Form Data (`formData`)**: 
   - The `formData` object is defined with `reactive` to keep track of form field values and automatically update when inputs change.
   
3. **Error Handling (`errors`)**: 
   - Another reactive object, `errors`, is defined to store error messages for each field.
   
4. **Validation (`validateForm`)**: 
   - This function checks the validity of each field. If a field is invalid, it sets an error message in the `errors` object.
   
5. **Form Submission (`handleSubmit`)**: 
   - If validation passes (`validateForm` returns `true`), the form data is logged or submitted. 
   - You can replace `console.log` with an API call to send form data to a server.
   - After successful submission, the form is reset by clearing each property in `formData`.

### Additional Features

1. **Custom Styling**: 
   - Add a `<style scoped>` block to include CSS specific to this component, ensuring that styles do not bleed into other components.

2. **Asynchronous Submission**: 
   - Wrap the submission logic in an `async` function if you need to submit data to a server. Using `await` ensures asynchronous operations complete before proceeding.
   - Example:
     ```javascript
     const handleSubmit = async () => {
       if (validateForm()) {
         try {
           await submitFormData(formData); // Replace with actual API call
           alert('Form submitted successfully!');
         } catch (error) {
           console.error('Submission failed', error);
         }
       }
     };
     ```

3. **Form Reset Functionality**: 
   - You can also create a separate `resetForm` function to clear all input fields without submitting the form.
   - Example:
     ```javascript
     const resetForm = () => {
       Object.keys(formData).forEach(key => formData[key] = '');
     };
     ```

By using the `<script setup>` syntax, Vue 3 allows for more concise, efficient, and scalable form components that include reactive form handling, validation, and submission capabilities.