<div class="container">
  <h1 id="project-campus-jam">Project: Musicians of Manoa</h1>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/musicians-of-manoa-logo.png" alt="Musicians of Manoa Logo" style="width: 50%;">
  </div>
  <div style="display: flex; justify-content: center;">
    <a href="https://github.com/musicians-of-manoa/musicians-of-manoa/actions/workflows/ci.yml">
      <img src="https://github.com/musicians-of-manoa/musicians-of-manoa/actions/workflows/ci.yml/badge.svg" alt="musiciansofmanoa">
    </a>
  </div>


  <h2>Table of Contents</h2>
  <ul>
    <li><a href="#overview">Overview</a></li>
    <li><a href="#team">Development Team</a></li>
    <li><a href="#approach">Approach</a></li>
    <li><a href="#guide">User Guide</a></li>
    <li><a href="#dev-guide">Developer Guide</a></li>
    <li><a href="#history">Development History</a></li>
    <li><a href="#feedback">Community Feedback</a></li>
    <li><a href="#quality-assurance">Quality Assurance</a></li>
    <li><a href="#enhancements">Possible Enhancements</a></li>
  </ul>

  <h2 id="overview">Overview<a class="anchorjs-link " aria-label="Anchor" data-anchorjs-icon="" href="#overview" style="font: 1em / 1 anchorjs-icons; margin-left: 0.1875em; padding-right: 0.1875em; padding-left: 0.1875em;"></a></h2>

  <p><em>The problem:</em> Many UH students have musical talents, but there is no easy way for them to find others with similar tastes and compatible musical abilities. Thus, they cannot experience the fun of informal jam sessions which could progress into performing musical groups.</p>

  <p><em>The solution:</em>  The Campus Jam application allows students to login and create a profile indicating their musical tastes, their musical capabilities, and their musical goals (from occasional, informal jam sessions to performing bands). The profile can also include links to YouTube videos or SoundCloud tracks with examples of their musicianship.</p>

  <h2 id="team">Development Team<a class="anchorjs-link " aria-label="Anchor" data-anchorjs-icon="" href="#team" style="font: 1em / 1 anchorjs-icons; margin-left: 0.1875em; padding-right: 0.1875em; padding-left: 0.1875em;"></a></h2>

  <b>
  Dominic Deuz <br>
  Josh Hicks <br>
  Christian Iha <br>
  Dahyun Kwon <br>
  Samantha Limon <br>
  </b>
  <hr>

  <a href="/img/Musicians%20of%20Manoa%20-%20Team%20Contract.pdf"><b>Team Contract</b></a>
  <br>
  <a href="/img/Musicians%20of%20Manoa%20-%20Team%20Bonding.pdf"><b>Team Bonding</b></a>
  <br>
  <a href="https://github.com/musicians-of-manoa"><b>Github Organization</b></a>

  <h2 id="approach">Approach<a class="anchorjs-link " aria-label="Anchor" data-anchorjs-icon="" href="#approach" style="font: 1em / 1 anchorjs-icons; margin-left: 0.1875em; padding-right: 0.1875em; padding-left: 0.1875em;"></a></h2>

  <p>Once a profile is created, others can browse the profiles filtered by specific tastes, capabilities, and goals to find compatible musicians to contact.</p>

  <p>Students can also set up notifications to find out automatically when a profile is created that satisfies criteria that they specify.</p>

  <p>Admins can monitor the site for inappropriate content, and create new categories of musical tastes, capabilities, and goals.</p>

  <p>Note: if you choose this idea for your final project, you cannot name it “Campus Jam”.  Come up with a different name for your final project.</p>

  <h2 id="guide">Website Guide<a class="anchorjs-link " aria-label="Anchor" data-anchorjs-icon="" href="#guide" style="font: 1em / 1 anchorjs-icons; margin-left: 0.1875em; padding-right: 0.1875em; padding-left: 0.1875em;"></a></h2>

  <h3>Landing Page</h3>
  <p>The landing page is presented to users when they visit the top-level URL to the site. This page presents basic information about the project and buttons that will take them to other commonly used pages.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/landing-1.png" alt="Landing Page 1">
  </div>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/landing-2.png" alt="Landing Page 2">
  </div>

  <h3>Sign In/Sign Up</h3>
  <p>Click on the "Login" button in the upper right corner of the navbar, then select "Sign in" if you already have an account created, if not you can create an account by clicking "Sign up" instead.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/signin.png" alt="Sign In Page">
  </div>
  
  <p>The "Sign up" page allows the user to customize their profile by providing attributes such as their musical goals, instruments & experience levels, and musical tastes.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/signup(creatinguser).png" alt="Creating User Page">
  </div>
  <br />
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/selectmusicaltaste.png" alt="Creating User Page: Select Musical Taste">
  </div>

  <h3>View/Edit Profile Page</h3>
  <p>Click on the "View/Edit Profile" button in the upper right corner of the navbar after logging in, User can see their own Profile page and can edit their information.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/view-profile.png" alt="View/Edit Profile Page">
  </div>

  <h3>Upcoming Jams Page</h3>
  <p>After logging in, there are more links shown in the navbar: "Feed", "Create a Jam", and "Search". Hitting the "Feed" link will take you to the Upcoming Jams Page, where you can see the upcoming jam sessions available.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/upcoming-jams.png" alt="Upcoming Jams Page">
  </div>

  <h3>Search Page</h3>
  <p>There is also a "Search" link in the navbar. Hitting this link will take you to the Search page, where you can search for other profiles or jam sessions.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/search.png" alt="Search Page">
  </div>

<h3>Profile Search Page</h3>
  <p>Clicking the "Profiles" card on the Search Page will take you to the "Profile Search Page", where users can search for other user profiles.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/search-profiles.png" alt="Profile Search Page">
  </div>

  <h3>User's Profile and Review Creation Page</h3>
  <p>Clicking the "View Profile" Button on the Search Profiles Page will take you to the "Profile Page", where users can see detailed Profile Information and Reivews and can leave review to the user.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/review-creation.png" alt="Profile Page">
  </div>
  
  <h3>Jam Search Page</h3>
  <p>Clicking the "Jam" card on the Search Page will take you to the "Jam Search Page", where users can search for jam sessions hosted by other users. Also, users can attend a jam session by clicking "Attend Jam".</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/search-jams.png" alt="Jam Search Page">
  </div>

  <h3>Attending Jams Page</h3>
  <p>Once the user clicks the "Attend Jam" button on the Jam Information Card, their jam is saved onto the "Attending Jams Page." The user can also delete this Jam session if they decide to not attend it anymore or if it's a past Jam session.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/attending-jams.png" alt="Attending Jams Page">
  </div>

  <h3>Jam Information Page</h3>
  <p>Hitting the "Create a Jam" link will take you to the Jam Information page, where you can fill in information for a musical jam session which will be posted to the website for other musicians to view.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/jam-information.png" alt="Jam Information Page">
  </div>

  <h3>Edit Musical Goals / Tastes / Experience Pages</h3>
  <p>Musical goals, musical tastes, and musical experience levels are all pieces of information acquired from users when creating their account. This allows jam organizers and fellow musicians to find musicians with specific skills and inclinations. For simplicity, the options for each are limited by site administrators and can be edited on this page.</p>
  <div style="display: flex; justify-content: space-around; padding-bottom: 1rem">
    <img src="/img/editGoal.png" alt="Edit Goals Page">
  </div>
  <div style="display: flex; justify-content: space-around; padding-bottom: 1rem">
    <img src="/img/editTaste.png" alt="Edit Tastes Page">
  </div>
  <div style="display: flex; justify-content: space-around; padding-bottom: 1rem">
    <img src="/img/editExperience.png" alt="Edit Experience Page">
  </div>

<h3>Admin Dashboard Page</h3>
  <p>By clicking on the "Admin" tab in the navbar, Admins have the ability to edit experience levels, musical goals, and musical tastes. They can also view all of the signed in users.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/admin-dashboard.png" alt="Admin Dashboard Page">
  </div>

<h3>Edit Jam Information (Admin)</h3>
  <p>Only admins have the ability to edit Jam information. They can do so by clicking the "Admin" tab in the navbar, and going to the "Edit Jams" section. Once they click on the "Edit" button, they are redirected to the "Edit Jam Information" form, which edits the existing form data.</p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/admin-edit-jams.png" alt="Admin Jam Edit Page">
  </div>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/edit-jams.png" alt="Edit Jam Information Page">
  </div>
  
  <h2 id="dev-guide">Developer Guide<a class="anchorjs-link " aria-label="Anchor" data-anchorjs-icon="" href="#dev-guide" style="font: 1em / 1 anchorjs-icons; margin-left: 0.1875em; padding-right: 0.1875em; padding-left: 0.1875em;"></a></h2>

  <p>This section provides information of interest to Next developers wishing to use this code as a basis for their own development tasks.</p>

  <h3>Deployment</h3>
  <p>You can find a live deployment of the website at this link <a  href="https://musicians-of-manoa.vercel.app/">https://musicians-of-manoa.vercel.app</a>.</p>

  <h3>Installation</h3>
  First, make sure you have <a href="https://nodejs.org/en">Node</a> installed.
  <br>
  Second, visit the <a href="https://github.com/musicians-of-manoa/musicians-of-manoa">Musicians of Manoa</a> GitHub page, and click the "Use this template" button to create your own repository initialized with a copy of this application. Alternatively, you can download the sources as a zip file or make a fork of the repo. However you do it, download a copy of the repo to your local computer.
  <br>
  Third, after having installed your local copy of the application, cd into the musicians-of-manoa directory with a command terminal and install libraries with:
  <br>
  <code>$ npm install</code>
  <br>
  Fourth, run the system with: 
  <br>
  <code>$ npm run dev</code>

  If everything was successful, you will be able to view the application at <a href="http://localhost:3000">http://localhost:3000</a>

  <h2 id="history">Development History<a class="anchorjs-link " aria-label="Anchor" data-anchorjs-icon="" href="#history" style="font: 1em / 1 anchorjs-icons; margin-left: 0.1875em; padding-right: 0.1875em; padding-left: 0.1875em;"></a></h2>
  <p>The development process for the Musicians of Manoa project conformed to <a href="https://courses.ics.hawaii.edu/ics314f24/morea/project-management/reading-guidelines-idpm.html">Issue Driven Project Management</a> practices. These practices include:</p>

  <ul>
    <li><b>Frequent Meetings:</b> Teams should meet at least twice a week to review progress and update tasks, with face-to-face meetings preferred for better coordination.</li>
    <li><b>Task Decomposition:</b> Work should be divided into small tasks taking approximately 72 hours to complete. Longer tasks must be broken into subtasks.</li>
    <li><b>Task Documentation and Ownership:</b> Each task is documented as a GitHub issue with a single owner responsible for its completion. Collaboration is possible, but accountability remains with the designated owner.</li>
    <li><b>Branch-based Task Execution:</b> Each task is associated with its own branch, named using the issue number ("issue-XX"), to reduce conflicts and ensure clear tracking. Completed branches are merged back into the main branch.</li>
    <li><b>Milestone Organization:</b> Tasks are grouped into milestones spanning 7-10 days, each producing a concrete deliverable. Each GitHub issue is assigned to exactly one milestone.</li>
    <li><b>Active Issues Per Member:</b> Each team member should have at least two active issues in the current milestone to ensure steady progress and task availability.</li>
    <li><b>Progress Tracking via GitHub Projects:</b> A GitHub Project board with columns for ToDo, In Progress, and Done is created for each milestone to manage tasks visually and systematically.</li>
    <li><b>Effort Estimation:</b> Effort is estimated in hours for each issue, based on task complexity, dependencies, and resources. Estimates are refined as experience grows.</li>
  </ul>

  <p>The following sections document the development history of BowFolios</p>
  <h3>Milestone 1</h3>
  <p>The goal of Milestone 1 was to create as many mockup pages as possible of the necessary pages for our project, the group deciding building the pages using Nextjs from the start to be the easiest approach.<p>
  <p>Milestone 1 was managed using <a href="https://github.com/orgs/musicians-of-manoa/projects/1">Musicians of Manoa Project Board M1</a></p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/M1Board.png" alt="M1 Project Board 24 hours before Milestone 1 was due.">
  </div>

<h3>Milestone 2</h3>
  <p>The goal of Milestone 2 is to connect as many mockup pages as possible to a PostgreSQL database. For forms, this involves ensuring that form data is correctly stored in the Prisma schema tables. For edit forms, this requires verifying that they can retrieve previously entered data and allow modifications as needed.</p>
  <p>The pages currently connected to the database include the Jam Search(read), Jam Creation(write), Edit Jam(read and write), and Edit Goals(read) pages.</p>
  <p>Milestone 2 was managed using <a href="https://github.com/orgs/musicians-of-manoa/projects/3">Musicians of Manoa Project Board M2</a></p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/M2Board.png" alt="M2 Project Board">
  </div>

  <h3>Milestone 3</h3>
  <p>The goal of Milestone 3 is to refine the database connections and clean up the overall UI. <p>
  <p>Milestone 3 was managed using <a href="https://github.com/orgs/musicians-of-manoa/projects/5">Musicians of Manoa Project Board M3</a></p>
  <div style="display: flex; justify-content: space-around;">
    <img src="/img/M3Board.png" alt="M3 Project Board">
  </div>

<h2 id="feedback">Community Feedback<a class="anchorjs-link " aria-label="Anchor" data-anchorjs-icon="" href="#team" style="font: 1em / 1 anchorjs-icons; margin-left: 0.1875em; padding-right: 0.1875em; padding-left: 0.1875em;"></a></h2>
We are interested in your experience using Musicians of Manoa! If you have any suggestions on how we can improve the application, feel free to fill out our feedback form : <a href="https://docs.google.com/forms/d/e/1FAIpQLSev62PmoiMksL4z72u7VoMeBEaRiqLEF4Jr759wk5Lv6m7qew/viewform?usp=sf_link">Feedback Form (Google Form)</a>

<br>

<p>Here are some suggestions we've gotten so far from community members who have used Musicians of Manoa.</p>

<p>Person 1</p>
<ul>
    <li>We were told that the overall design of the application was visually appealing. They found the Profile Info Cards in Search Page to be clear and informative. As a suggestion for improvement, they recommended adding a filter option button next to the search bar on the search pages for enhanced functionality. </li>
</ul>

<p>Person 2</p>
<ul>
    <li>I liked the color scheme of the website! Sticking to UH Manoa colors. The home page is well designed and looks cool. I think the user's profile could use some work, maybe if this is for musicians you could link to the person's music somehow. I like search page as well, being able to see all the profiles and events. </li>
</ul>

<p>Person 3</p>
<ul>
    <li>It's a cool website. I tried messing with the login stuff and it was a little broken at times, like the signing up it was a little hard to select the genres I liked. Beside that though I can see the potential in this site, it's cool. Maybe add more ways users could interact with each other like a social media website or something?</li>
</ul>

<p>Person 4</p>
<ul>
  <li>I really like the color scheme of the website and how well it is organized. I think adding a calendar to the Feed page would make the Jam Event Feed more clear and user-friendly.</li>
</ul>

<p>Person 5</p>
<ul>
  <li>It would be cool if users can add videos of their past jam sessions to show their skill. That makes their profiles more interesting. Overall, the website looks easy to use and fun to explore.</li>
</ul>

<h2 id="quality-assurance">Quality Assurance<a class="anchorjs-link " aria-label="Anchor" data-anchorjs-icon="" href="#quality-assurance" style="font: 1em / 1 anchorjs-icons; margin-left: 0.1875em; padding-right: 0.1875em; padding-left: 0.1875em;"></a></h2>
<h3>ESLint</h3>
<p>Musicians of Manoa includes a <a href="https://github.com/bowfolios/bowfolios/blob/main/app/.eslintrc">.eslintrc</a> file to define the coding style adhered to in this application. You can invoke ESLint from the command line as follows:</p>

<code>npm run lint</code>

<p>Here is sample output indicating that no ESLint errors were detected:</p>


> PS E:\ICS314\musicians-of-manoa> npm run lint
> 
> \> nextjs-application-template-1@0.1.0 lint
>
> \> next lint
> 
> =============
>
> WARNING: You are currently running a version of TypeScript which is not officially supported by @typescript-eslint/typescript-estree.
> 
> You may find that it works just fine, or you may not.
> 
> SUPPORTED TYPESCRIPT VERSIONS: >=4.7.4 <5.6.0
> 
> YOUR TYPESCRIPT VERSION: 5.6.3
> 
> Please only submit bug reports when using the officially supported version.
> 
> =============
> ✔ No ESLint warnings or errors

<p>
ESLint should run without generating any errors.

It's significantly easier to do development with ESLint integrated directly into your IDE (such as IntelliJ).
</p>

<h3>End to End Testing</h3>

<p>
Musicians of Manoa uses <a href="https://playwright.dev/">Playwright</a> to provide automated end-to-end testing.
<br>
To run the end-to-end tests in development mode, you must first start up a Musicians of Manoa instance by invoking `npm run dev` in one console window.
Then, in another console window, start up the end-to-end tests with:
</p>
<code>npm playwright test</code>

<p>
If the tests finish successfully, you should see the following in your second console window:
</p>

> PS E:\ICS314\musicians-of-manoa> npx playwright test                    
> 
> Running 6 tests using 6 workers
>  6 passed (8.4s)
> 
> To open last HTML report run:
> 
> npx playwright show-report

  <h2 id="enhancements">Possible Enhancements<a class="anchorjs-link " aria-label="Anchor" data-anchorjs-icon="" href="#enhancements" style="font: 1em / 1 anchorjs-icons; margin-left: 0.1875em; padding-right: 0.1875em; padding-left: 0.1875em;"></a></h2>

  <p>Here are ideas for more advanced features:</p>

  <ul>
    <li>Support the organization of jam sessions. Provide information on scheduled jam sessions, including location, time, musical type, desired capabilities, and organizer contact information.</li>
    <li>Support a network of “who’s played with who”.</li>
    <li>Support reviews of musicians.</li>
  </ul>
