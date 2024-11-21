# Complete HTML Form Elements and Attributes Guide

## 1. Form Element Attributes

### Complete Form Element:
```html
<form
    action="/submit"                  <!-- Form submission URL -->
    method="post"                    <!-- HTTP method -->
    enctype="multipart/form-data"    <!-- Encoding type -->
    name="registrationForm"          <!-- Form name -->
    id="registrationForm"            <!-- Form ID -->
    autocomplete="on"                <!-- Enable/disable autocomplete -->
    novalidate                       <!-- Disable browser validation -->
    target="_self"                   <!-- Submission target -->
    accept-charset="UTF-8"           <!-- Character encoding -->
    rel="form"                       <!-- Relationship attribute -->
    onsubmit="return validateForm()" <!-- Submit event handler -->
>
</form>
```

## 2. Complete List of Input Types

### Text-Based Inputs:

1. Text Input:
```html
<input 
    type="text"
    name="username"
    id="username"
    value=""
    placeholder="Enter username"
    maxlength="50"
    minlength="3"
    size="30"
    pattern="[A-Za-z0-9]+"
    required
    readonly
    disabled
    autocomplete="username"
    spellcheck="true"
    autofocus
    form="form1"
    list="datalistId"
>
```

2. Password:
```html
<input 
    type="password"
    name="password"
    id="password"
    placeholder="Enter password"
    minlength="8"
    maxlength="128"
    autocomplete="new-password"
    required
    pattern="^(?=.*[A-Za-z])(?=.*\d)[A-Za-z\d]{8,}$"
>
```

3. Email:
```html
<input 
    type="email"
    name="email"
    id="email"
    placeholder="name@domain.com"
    pattern="[a-z0-9._%+-]+@[a-z0-9.-]+\.[a-z]{2,}$"
    multiple
    required
>
```

4. Search:
```html
<input 
    type="search"
    name="search"
    id="search"
    placeholder="Search..."
    results="5"
    autosave="search_field"
>
```

5. URL:
```html
<input 
    type="url"
    name="website"
    id="website"
    placeholder="https://example.com"
    pattern="https://.*"
    size="30"
>
```

6. Tel:
```html
<input 
    type="tel"
    name="phone"
    id="phone"
    placeholder="(123) 456-7890"
    pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
>
```

### Numeric Inputs:

1. Number:
```html
<input 
    type="number"
    name="quantity"
    id="quantity"
    min="0"
    max="100"
    step="1"
    value="1"
>
```

2. Range:
```html
<input 
    type="range"
    name="rating"
    id="rating"
    min="0"
    max="10"
    step="0.5"
    value="5"
    list="tickmarks"
>
<datalist id="tickmarks">
    <option value="0" label="0">
    <option value="5" label="5">
    <option value="10" label="10">
</datalist>
```

### Date and Time Inputs:

1. Date:
```html
<input 
    type="date"
    name="birthdate"
    id="birthdate"
    min="1900-01-01"
    max="2024-12-31"
    value="2024-01-01"
>
```

2. Time:
```html
<input 
    type="time"
    name="meeting"
    id="meeting"
    min="09:00"
    max="18:00"
    step="900"
>
```

3. DateTime-Local:
```html
<input 
    type="datetime-local"
    name="event"
    id="event"
    min="2024-01-01T00:00"
    max="2024-12-31T23:59"
>
```

4. Month:
```html
<input 
    type="month"
    name="expiry"
    id="expiry"
    min="2024-01"
    max="2030-12"
>
```

5. Week:
```html
<input 
    type="week"
    name="weekNum"
    id="weekNum"
    min="2024-W01"
    max="2024-W52"
>
```

### Selection Inputs:

1. Checkbox:
```html
<input 
    type="checkbox"
    name="interests[]"
    id="sports"
    value="sports"
    checked
>
<label for="sports">Sports</label>
```

2. Radio:
```html
<input 
    type="radio"
    name="gender"
    id="male"
    value="male"
    required
>
<label for="male">Male</label>
```

### File Input:
```html
<input 
    type="file"
    name="document"
    id="document"
    accept=".pdf,.doc,.docx,image/*"
    multiple
    capture="user"
    required
>
```

### Hidden Input:
```html
<input 
    type="hidden"
    name="csrf_token"
    value="abc123xyz"
>
```

### Color Input:
```html
<input 
    type="color"
    name="theme"
    id="theme"
    value="#ff0000"
>
```

### Button Inputs:
```html
<input 
    type="submit"
    value="Submit"
    formaction="/submit"
    formmethod="post"
    formnovalidate
    formtarget="_blank"
>

<input type="reset" value="Reset Form">
<input type="button" value="Click Me" onclick="handleClick()">
<input type="image" src="button.png" alt="Submit">
```

## 3. Select Element

### Basic Select:
```html
<select 
    name="country"
    id="country"
    required
    multiple
    size="4"
    form="form1"
    autofocus
    disabled
>
    <option value="">Choose a country</option>
    <option value="us" selected>United States</option>
    <option value="uk" disabled>United Kingdom</option>
</select>
```

### Grouped Options:
```html
<select name="car">
    <optgroup label="Swedish Cars">
        <option value="volvo">Volvo</option>
        <option value="saab">Saab</option>
    </optgroup>
    <optgroup label="German Cars" disabled>
        <option value="mercedes">Mercedes</option>
        <option value="audi">Audi</option>
    </optgroup>
</select>
```

## 4. Textarea Element

### Complete Textarea:
```html
<textarea 
    name="description"
    id="description"
    rows="4"
    cols="50"
    maxlength="500"
    minlength="10"
    placeholder="Enter description..."
    wrap="hard"
    required
    readonly
    disabled
    autofocus
    spellcheck="true"
    form="form1"
    dirname="description.dir"
></textarea>
```

## 5. Button Element

### Complete Button Types:
```html
<!-- Submit button -->
<button 
    type="submit"
    name="submit"
    value="submit"
    formmethod="post"
    formaction="/submit"
    formnovalidate
    formtarget="_blank"
    form="form1"
    disabled
>
    Submit Form
</button>

<!-- Reset button -->
<button 
    type="reset"
    name="reset"
    disabled
>
    Reset Form
</button>

<!-- Regular button -->
<button 
    type="button"
    name="action"
    value="save"
    onclick="handleClick()"
    disabled
>
    Save Draft
</button>
```

## 6. Field Organization Elements

### Fieldset and Legend:
```html
<fieldset 
    name="personalInfo"
    form="form1"
    disabled
>
    <legend>Personal Information</legend>
    <!-- Form fields -->
</fieldset>
```

### Label Element:
```html
<label 
    for="username"
    form="form1"
>
    Username:
    <input type="text" id="username" name="username">
</label>
```

### Output Element:
```html
<output 
    name="result"
    for="num1 num2"
    form="form1"
>
    0
</output>
```

### Datalist Element:
```html
<input list="browsers" name="browser">
<datalist id="browsers">
    <option value="Chrome">
    <option value="Firefox">
    <option value="Safari">
    <option value="Edge">
</datalist>
```

## 7. Complete Form Example

```html
<form id="completeForm" action="/submit" method="post" enctype="multipart/form-data">
    <!-- Personal Information -->
    <fieldset>
        <legend>Personal Information</legend>

        <!-- Text inputs -->
        <div class="form-group">
            <label for="fullName">Full Name:</label>
            <input type="text" id="fullName" name="fullName" required>
        </div>

        <div class="form-group">
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
        </div>

        <!-- Date input -->
        <div class="form-group">
            <label for="birthdate">Birth Date:</label>
            <input type="date" id="birthdate" name="birthdate">
        </div>

        <!-- Select input -->
        <div class="form-group">
            <label for="country">Country:</label>
            <select id="country" name="country" required>
                <option value="">Select country</option>
                <optgroup label="North America">
                    <option value="us">United States</option>
                    <option value="ca">Canada</option>
                </optgroup>
            </select>
        </div>
    </fieldset>

    <!-- Preferences -->
    <fieldset>
        <legend>Preferences</legend>

        <!-- Checkboxes -->
        <div class="form-group">
            <label>Interests:</label>
            <input type="checkbox" id="sports" name="interests[]" value="sports">
            <label for="sports">Sports</label>
            <input type="checkbox" id="music" name="interests[]" value="music">
            <label for="music">Music</label>
        </div>

        <!-- Radio buttons -->
        <div class="form-group">
            <label>Newsletter:</label>
            <input type="radio" id="subscribe" name="newsletter" value="yes">
            <label for="subscribe">Subscribe</label>
            <input type="radio" id="unsubscribe" name="newsletter" value="no">
            <label for="unsubscribe">Don't Subscribe</label>
        </div>

        <!-- Range input -->
        <div class="form-group">
            <label for="satisfaction">Satisfaction Level:</label>
            <input type="range" id="satisfaction" name="satisfaction" min="0" max="10">
        </div>

        <!-- Color input -->
        <div class="form-group">
            <label for="favColor">Favorite Color:</label>
            <input type="color" id="favColor" name="favColor">
        </div>
    </fieldset>

    <!-- Additional Information -->
    <fieldset>
        <legend>Additional Information</legend>

        <!-- File upload -->
        <div class="form-group">
            <label for="photo">Profile Photo:</label>
            <input type="file" id="photo" name="photo" accept="image/*">
        </div>

        <!-- Textarea -->
        <div class="form-group">
            <label for="bio">Biography:</label>
            <textarea id="bio" name="bio" rows="4" cols="50"></textarea>
        </div>

        <!-- Hidden input -->
        <input type="hidden" name="formId" value="registration">
    </fieldset>

    <!-- Form Controls -->
    <div class="form-controls">
        <button type="submit">Submit Form</button>
        <button type="reset">Reset Form</button>
        <button type="button" onclick="saveDraft()">Save Draft</button>
    </div>
</form>
```

## 8. Form Validation Attributes

```html
<!-- Input validation attributes -->
<input 
    required
    pattern="[A-Za-z0-9]+"
    minlength="3"
    maxlength="20"
    min="0"
    max="100"
    step="1"
    title="Please enter a valid value"
>

<!-- Custom validation message -->
<input 
    oninvalid="this.setCustomValidity('Please enter a valid value')"
    oninput="this.setCustomValidity('')"
>
```

## 9. Form Events

```html
<form
    onsubmit="return validateForm()"
    onreset="return confirmReset()"
    oninput="calculateTotal()"
    onchange="handleChange()"
>
```

## 10. Accessibility Attributes

```html
<!-- ARIA attributes -->
<input 
    aria-label="Search"
    aria-required="true"
    aria-invalid="false"
    aria-describedby="hint"
>

<!-- Role attributes -->
<div role="group" aria-labelledby="groupTitle">
    <h3 id="groupTitle">Contact Information</h3>
    <!-- Form fields -->
</div>
```

