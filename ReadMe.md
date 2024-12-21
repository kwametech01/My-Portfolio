# Personal Portfolio Project

## Project Overview
This is a personal portfolio website designed to showcase my skills, projects, and experiences as a front-end web developer and hyper-realism pencil artist. The site includes various sections such as About, Projects, Contact, and more, with an emphasis on both functionality and aesthetics.

## Features
1. **Responsive Design**:
   - The website is fully responsive and adapts seamlessly to different screen sizes, providing an optimal user experience on desktops, tablets, and mobile devices.

2. **Interactive Elements**:
   - Smooth scrolling for navigation.
   - Scroll-triggered animations to reveal content dynamically.
   - A responsive navigation menu with a toggle button for mobile views.

3. **Dynamic Content**:
   - Current year automatically updates in the footer.
   - Form validation for the Contact section.

4. **Enhanced User Experience**:
   - Custom animations for project images and text.
   - User-friendly contact form with built-in validation.

## Recent Changes and Updates
### 1. **Smooth Scrolling**:
   - Implemented smooth scrolling for navigation links using JavaScript. This improves navigation and creates a more polished feel when users click on links in the navbar.

### 2. **Responsive Navbar**:
   - Added a toggle button for the navbar to ensure proper navigation functionality on smaller screens.

### 3. **Scroll Animations**:
   - Added JavaScript functionality to reveal elements as users scroll down the page. This enhances the visual appeal and draws attention to important content.

### 4. **Form Validation**:
   - Included validation logic for the contact form to ensure users enter valid data before submission. The validation checks for non-empty name and message fields and a properly formatted email address.

### 5. **Footer Year Update**:
   - JavaScript was added to dynamically display the current year in the footer, ensuring the site remains up-to-date.

### 6. **Bug Fixes**:
   - Fixed a bug causing a `TypeError: Cannot read properties of null` by ensuring DOM elements are properly queried before adding event listeners.
   - Resolved a 404 error for missing image files by verifying file paths and ensuring assets are correctly referenced.

## Code Explanation
### JavaScript Functionalities
#### 1. **Scroll Animations**
```javascript
const revealElements = document.querySelectorAll('.reveal');
const handleScroll = () => {
    revealElements.forEach(el => {
        const rect = el.getBoundingClientRect();
        if (rect.top < window.innerHeight - 100) {
            el.classList.add('visible');
        }
    });
};
window.addEventListener('scroll', handleScroll);
handleScroll();
```
- This code dynamically adds a `visible` class to elements with the `.reveal` class when they come into the viewport. This triggers CSS animations for a more engaging user experience.

#### 2. **Smooth Scrolling**
```javascript
document.querySelectorAll('nav ul li a').forEach(anchor => {
    anchor.addEventListener('click', function (e) {
        e.preventDefault();
        const targetId = this.getAttribute('href').substring(1);
        document.getElementById(targetId).scrollIntoView({
            behavior: 'smooth'
        });
    });
});
```
- This ensures smooth transitions when navigating between sections using anchor links.

#### 3. **Responsive Navbar**
```javascript
const navToggle = document.querySelector('.nav-toggle');
const navMenu = document.querySelector('nav ul');
if (navToggle) {
    navToggle.addEventListener('click', () => {
        navMenu.classList.toggle('show');
    });
}
```
- The navbar becomes collapsible on smaller screens, allowing users to toggle its visibility using a button.

#### 4. **Footer Year Update**
```javascript
const footerYear = document.querySelector('footer p');
const currentYear = new Date().getFullYear();
footerYear.innerHTML = `&copy; ${currentYear} Augustine Chima`;
```
- Automatically updates the footer year to the current year.

#### 5. **Form Validation**
```javascript
document.getElementById('contactForm').addEventListener('submit', function (e) {
    e.preventDefault();
    const name = document.getElementById('name').value.trim();
    const email = document.getElementById('email').value.trim();
    const message = document.getElementById('message').value.trim();
    if (name === '') {
        alert('Please enter your name.');
        return;
    }
    if (email === '' || !validateEmail(email)) {
        alert('Please enter a valid email address.');
        return;
    }
    if (message === '') {
        alert('Please enter your message.');
        return;
    }
    alert('Form submitted successfully!');
    this.submit();
});
function validateEmail(email) {
    const re = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6}$/;
    return re.test(email);
}
```
- Validates the name, email, and message fields in the contact form to ensure proper input before submission.

### HTML and CSS Updates
- Added `reveal` classes to elements for scroll animations.
- Updated navbar HTML to include a toggle button for mobile views.
- Improved the layout and design with CSS enhancements for a consistent and appealing style.

## Folder Structure
```
project-root/
├── index.html
├── assets/
│   ├── css/
│   │   └── styles.css
│   ├── js/
│   │   └── script.js
│   ├── images/
│   │   └── web-project5.jpg
```

## How to Run the Project
1. Clone or download the repository.
2. Open `index.html` in a browser to view the portfolio.
3. Use a live server for better navigation experience if testing locally.

## Future Improvements
- Add more interactivity and animations.
- Integrate a backend for storing contact form submissions.
- Enhance the Projects section with filtering options.

## Author
**Augustine Chima**
- Front-End Developer
- Hyper-Realism Pencil Artist

