This application presents Innovatech Solutions as a modern digital agency, highlighting core services and providing a contact form for potential clients. The layout includes a sticky navigation header, main content area with page-level sections, and a footer with company and technology information.

Tech Stack
React with functional components and hooks (useState, useReducer, useCallback)

Tailwind CSS for utility-first responsive styling

Lucide React icon set for consistent vector icons

Simple client-side “routing” managed via component state instead of a routing library

Core Features
Sticky, responsive header with desktop navigation and mobile hamburger menu

Home page hero section with bold headline, supporting copy, and primary call-to-action button

“Why Choose Us?” section highlighting key value propositions (performance, scalability, accessibility)

Services grid showcasing multiple offerings with icons, descriptions, and “Learn More” actions

Contact page with interactive form, loading state, success state, and error handling

Theming with indigo and gray tones, card-like panels, and soft drop shadows for a modern look​

Application Structure
App
Root component that manages which page is displayed using currentPage state. It renders the shared Header and Footer components and the selected page (HomePage, ServicesPage, or ContactPage) inside a flex column layout.

Header
Displays the company name and navigation items (Home, Services, Contact). On larger screens, links appear in a horizontal menu. On smaller screens, a Menu/X button toggles a collapsible mobile menu. The current page is visually highlighted.

Footer
Shows the current year, company name, and a short message indicating that the site is built with React and Tailwind CSS. It anchors the page with a dark background and centered text.

HomePage
Contains:

A hero section with a large heading “Future-Proof Your Business. Today.”, descriptive paragraph, and “Explore Our Solutions” button.

A “Why Choose Us?” row with three cards describing performance, scalability, and accessibility, each with an emoji icon and supporting copy.​

ServicesPage
Presents a heading, intro text, and a responsive CSS Grid of service cards. Each card includes:

An icon (using Lucide components)

Service title

Short description

“Learn More →” button placeholder for future interactions

ContactPage
Implements a contact form using a useReducer-based state machine. It includes:

Fields for full name, email address, and message

Required validation that ensures no field is left empty

A simulated asynchronous API call that sets isSubmitting and then switches to a success state

Error message display on validation failure or simulated network error

Success view with confirmation icon, success text, and a “Send Another Message” button that resets the form

State Management
useState

currentPage in App controls which page component is displayed.

isOpen in Header toggles the mobile navigation menu.

useReducer

formReducer in ContactPage manages a more complex form state including:

Input values: name, email, message

Request status: isSubmitting

Success flag: submissionSuccess

Error message: error

Supported actions:

CHANGE for updating individual fields

SUBMIT_START for starting a submission

SUBMIT_SUCCESS to clear inputs and show success state

SUBMIT_ERROR to record an error message

RESET to restore the initial form state

useCallback
Wraps handleChange in ContactPage to avoid unnecessary re-creations of the handler on re-renders, which is helpful when passing it to input elements.

Styling and Layout
Layout uses Tailwind’s container and responsive paddings/margins (px-4, sm:px-6, lg:px-8, py-12) to ensure consistent spacing across different screen sizes.

Cards and panels use rounded corners, subtle border, and shadows (rounded-xl, shadow-lg, shadow-xl) for a polished look.

Responsive behavior:

Header switches from inline navigation to mobile menu.

Services grid shifts from 1 column on small screens to up to 4 columns on extra-large screens.

The main layout ensures the footer stays at the bottom by using min-h-screen and flex flex-col.

Accessibility Considerations
ARIA attributes:

aria-label="Main Navigation" on the desktop nav

aria-expanded and aria-controls for the mobile menu button

aria-current="page" on the active navigation item for screen reader awareness

role="alert" on the contact form error message

Form fields are associated with labels via htmlFor and id.

Focus outlines and focus rings are preserved and enhanced using Tailwind’s focus:ring and focus:outline-none classes.

Project Setup Instructions
Initialize a React project (for example with Vite or Create React App).

Install dependencies:

React and React DOM (if not included by scaffolding)

Tailwind CSS, PostCSS, and Autoprefixer, then configure Tailwind with the recommended setup

lucide-react for icons

Add the provided code into App.jsx (or App.tsx with minor TypeScript adaptations).

Ensure Tailwind is imported into the main CSS (index.css) and that your build pipeline processes Tailwind directives.

Run the development server and open the app in a browser to view the Innovatech Solutions landing site
