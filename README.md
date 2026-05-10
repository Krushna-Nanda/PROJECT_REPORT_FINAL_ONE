# Abstract

---

**ABSTRACT**

The rapid growth of the global software development community has created a pressing need for a dedicated digital platform that comprehensively addresses the professional, technical, and collaborative requirements of developers. Existing social media platforms such as LinkedIn, Twitter, GitHub, Reddit, and Discord, while individually valuable, are designed for either general audiences or singular purposes, compelling developers to maintain fragmented identities across multiple applications and disrupting their workflow and productivity.

ZingUp is a full-stack, developer-focused social media platform designed to eliminate this fragmentation by providing a unified digital ecosystem where software developers, students, and technical communities can interact, collaborate, and network effectively. The platform is built on the MERN stack — MongoDB, Express.js, React, and Node.js — and is augmented with modern cloud services including Clerk for authentication, ImageKit for cloud media management, Inngest for background job orchestration, and Brevo SMTP for transactional email delivery.

The platform offers a comprehensive suite of developer-centric features including a personalised social feed, native code snippet sharing with syntax highlighting and language tagging, twenty-four-hour ephemeral stories with automated deletion, real-time one-to-one messaging powered by Server-Sent Events, a dual relationship model comprising Follow and Connect, a user discovery system, and comprehensive developer profile pages integrating links to GitHub, LinkedIn, Twitter, Dev.to, Medium, and personal portfolios. The system architecture follows a three-tier model — Presentation, Application, and Data layers — deployed on Vercel's cloud infrastructure with MongoDB Atlas as the managed database service.

ZingUp was developed using the Agile methodology with feature-based sprints, ensuring iterative development, continuous testing, and modular integration across nine functional modules. The platform demonstrates the practical application of advanced full-stack web development principles — including event-driven background processing, SSE-based real-time communication, and CDN-accelerated media delivery — within a production-ready, cloud-deployed application. The project contributes a scalable, technically sophisticated, and genuinely useful social networking solution to the developer community, establishing a strong foundation for future enhancements including AI-based recommendations, collaborative coding environments, and mobile application development.

---

# CHAPTER 1 — INTRODUCTION

## 1.1 Background

In recent years, social networking platforms have transformed the way people communicate, collaborate, and share information across the globe. Applications such as LinkedIn, Twitter, GitHub, Discord, and Reddit have become essential platforms for communication, professional networking, content sharing, and collaboration. However, these platforms mainly focus on either general social interaction or isolated technical collaboration, and they do not completely fulfill the requirements of developers and students in the technology community.

Developers today require a platform where they can not only interact socially but also showcase technical projects, share coding knowledge, communicate in real time, and build professional relationships within a developer-focused ecosystem. Existing platforms lack the integration of developer-centric features such as syntax-highlighted code sharing, technical networking, real-time collaboration, and structured communication in one unified environment.

---

## 1.2 Problem Statement

Modern social networking platforms such as LinkedIn, Twitter, and Instagram are primarily designed for general social interaction and professional networking, but they do not specifically address the collaborative and technical needs of developers and students in the technology community.

1. Developers often face difficulties in:
2. showcasing technical projects effectively,
3. finding meaningful technical connections,
4. sharing development-related content,
5. collaborating in real time,
6. and communicating within a focused developer ecosystem.

Most existing platforms mix technical content with large amounts of unrelated social content, reducing productivity and meaningful engagement. There is a need for a dedicated social platform that combines communication, collaboration, project sharing, and networking specifically for the developer community.

## 1.3 Key Issues in Existing Systems

### 1. Lack of Developer-Centric Features

• Most social platforms are built for general audiences and lack features tailored for developers and technical communities.

### 2. Limited Real-Time Collaboration

• Existing systems focus more on content consumption rather than meaningful technical interaction and communication.

### 3. Content Noise and Irrelevant Feeds

• Developer content often gets mixed with non-technical posts, reducing visibility and engagement.

### 4. Weak Community Discovery

• Finding developers with similar interests, skills, or projects is difficult on traditional platforms.

### 5. Fragmented Communication

• Users frequently rely on multiple platforms for messaging, networking, and content sharing instead of having a unified ecosystem.

### 6. Poor Media and Project Presentation

• Current systems are not optimized for showcasing technical projects, coding achievements, and development workflows.

## 1.4 Proposed Solution

ZingUp is a full-stack developer social network that addresses the gaps present in existing social networking platforms by providing multiple developer-focused features within a single unified ecosystem.

### 1. Native Code Snippet Posts

• Developers can share syntax-highlighted code directly inside posts with programming language tagging support, without depending on external platforms.

### 2. Dual Relationship System

• Users can follow developers for one-way updates similar to Twitter or connect mutually for professional networking similar to LinkedIn.

### 3. Real-Time 1-on-1 Messaging

• The platform provides lightweight real-time communication using Server-Sent Events (SSE) without requiring complex WebSocket infrastructure.

### 4. Ephemeral Stories

• Users can share temporary stories that automatically expire after 24 hours through automated background processing systems.

### 5. Smart Feed

• A personalized feed displays posts only from connected users and followed developers, improving content relevance and reducing unnecessary content noise.

### 6. Unified Developer Profile

• A centralized developer profile integrates platforms such as GitHub, LinkedIn, Twitter, Dev.to, Medium, and personal portfolios in one place.

## 1.5 Objectives

1. To build a unified social networking platform exclusively designed for the developer community.

2. To enable sharing of posts with embedded, syntax-highlighted code snippets natively.

3. To implement a real-time messaging system for seamless developer collaboration.

4. To provide a dual relationship model — Follow and Connect — for both public and private networking.

5. To integrate automated background workflows for notifications, story expiry, and user lifecycle management.

6. To deliver a responsive, modern user interface with dark mode support for extended coding sessions.


Here's the compact version:

---

## 1.6 SCOPE OF THE PROJECT

The scope of ZingUp covers the complete design, development, and deployment of a web-based social networking platform built exclusively for the software developer community. The platform targets software developers, MCA and computer science students, open-source contributors, and technology professionals.

**Current Scope includes:**

1. User authentication and secure account management
2. Personalised social feed with native code snippet sharing
3. Twenty-four-hour ephemeral story publishing with auto-deletion
4. Real-time one-to-one messaging using Server-Sent Events
5. Dual social networking through Follow and Connect relationships
6. User discovery and search by name, username, email, and location
7. Comprehensive developer profile with GitHub, LinkedIn, and portfolio links
8. Cloud-based media upload with automatic WebP optimisation via ImageKit
9. Automated email notifications for connection requests and unseen messages
10. Fully responsive UI with dark mode support, deployed on Vercel

**Future Scope includes:**

1. AI-based developer and content recommendations
2. Collaborative online code editor for pair programming
3. Group communities and topic-based technical forums
4. GitHub repository analytics integration within profiles
5. Video communication and screen sharing capabilities
6. Native mobile applications for Android and iOS

---

# CHAPTER 2 SYSTEM ANALYSIS & DESIGN 

---

## 2.1 System Architecture

ZingUp follows a three-tier architecture consisting of:

* Presentation Layer
* Application Layer
* Data Layer

The frontend is developed using React.js and Tailwind CSS. The backend uses Node.js and Express.js for API handling and business logic. MongoDB Atlas is used for database management.

The platform also integrates Clerk Authentication, ImageKit, Inngest, and Server-Sent Events (SSE) for authentication, media handling, background processing, and real-time messaging.

**[Figure 2.1: System Architecture Diagram — Insert diagram here]**
<img width="2752" height="1536" alt="System_Architecture" src="https://github.com/user-attachments/assets/ea330458-f94a-4686-9177-2c91cedbd0e0" />



---

## 2.2 Functional Requirements

The system should allow users to:

* register and log in securely,
* manage profiles,
* create posts and stories,
* upload media and code snippets,
* send real-time messages,
* follow and connect with users,
* and receive notifications.

---

## 2.3 Database Design

MongoDB Atlas is used as the primary database system for ZingUp. The platform uses a document-oriented NoSQL database structure for managing dynamic social networking data.

The major collections used in the system are:

* User
* Post
* Story
* Message
* Connection

The database design provides scalability, flexibility, and efficient handling of user-generated content.

---

## 2.4 Entity Relationship (ER) Diagram

The ER Diagram represents the relationships between major entities such as User, Post, Story, Message, Comment, and Connection.

A User can create posts and stories, send messages, and establish connections with other users. The ER model provides a logical representation of the database structure used within the platform.

**[Figure 2.2: ER Diagram — Insert diagram here]**
<img width="1536" height="1024" alt="erfinal2" src="https://github.com/user-attachments/assets/8f933f97-327a-4194-a4b2-81bfad51aead" />
---

## 2.5 Data Flow Diagram (DFD)

The Data Flow Diagram illustrates the movement of data between users, system processes, and the database.

The Level 0 DFD shows the overall interaction between users and the system, while the Level 1 DFD provides a detailed representation of authentication, post management, messaging, and profile handling processes.

**[Figure 2.3: DFD Level 0 — Insert diagram here]**
<img width="4817" height="1586" alt="Untitled diagram-2026-01-14-181123" src="https://github.com/user-attachments/assets/33c61a36-4119-414d-a94f-5e53bd97d14f" />

**[Figure 2.4: DFD Level 1 — Insert diagram here]**
<img width="6166" height="4189" alt="ImageKit Media Pipeline-2026-01-14-181430" src="https://github.com/user-attachments/assets/bd544ad5-aef3-46de-a685-af44744a5185" />

---

## 2.6 System Workflow

The workflow of ZingUp begins with user authentication and profile initialization. After login, users can create posts, upload stories, send messages, discover developers, and interact with technical content.

Media uploads are processed using ImageKit cloud services, while background tasks and notifications are handled using Inngest functions.

# CHAPTER 3

# SYSTEM PLANNING

---

## 3.1 Introduction

System planning is an important phase in the development of the ZingUp platform. This phase focused on identifying project requirements, selecting suitable technologies, defining system objectives, and planning the overall workflow of the application.

---

## 3.2 Planning Objectives

The major objectives considered during system planning were:

* developing a developer-focused social networking platform,
* supporting real-time communication,
* enabling secure authentication,
* providing cloud-based media handling,
* and ensuring scalable system architecture.

---

## 3.3 Technology Stack Used

### Frontend Technologies

* React.js (Vite)
* Tailwind CSS
* JavaScript
* HTML & CSS

### Backend Technologies

* Node.js
* Express.js

### Database

* MongoDB Atlas

### Authentication & Security

* Clerk Authentication

### Real-Time Communication

* Server-Sent Events (SSE)

### Cloud & Media Services

* ImageKit
* Inngest

### Development Tools

* Visual Studio Code
* Git & GitHub

---

## 3.4 Hardware and Software Requirements

### Hardware Requirements

* Processor: Intel Core i3 or above
* RAM: Minimum 4 GB
* Storage: Minimum 20 GB free space
* Internet Connectivity

### Software Requirements

* Windows/Linux Operating System
* Visual Studio Code
* Node.js Runtime Environment
* MongoDB Atlas
* Modern Web Browser (Chrome/Edge/Firefox)
* Git & GitHub

---

## 3.5 Development Methodology

The Agile development methodology was followed during the development of ZingUp. The project was divided into smaller modules such as authentication, messaging, stories, and feed management.

Agile methodology supported incremental development, continuous testing, debugging, and feature enhancement throughout the project lifecycle.

---

## 3.6 Deployment Planning

The platform was planned for cloud-based deployment to ensure scalability and accessibility. MongoDB Atlas was used for cloud database hosting, while the frontend and backend services were prepared for deployment on modern hosting platforms.

The system was designed to support responsive access across desktop and mobile devices.

# CHAPTER 4

# CHAPTER 4

# MODULES OF THE SYSTEM

---

# 4.1 User Authentication & Management Module

### Purpose

Handles user accounts, authentication, authorization, and profile management.

### Related Files

```text
models/User.js
controllers/userController.js
middlewares/auth.js
routes/userRotes.js
```

### Features

* User registration
* Login/logout
* JWT/session authentication
* Protected routes
* Profile handling
* User data management

---

# 4.2 Social Feed / Post Module

### Purpose

Allows users to create and interact with posts.

### Related Files

```text
models/Post.js
controllers/postController.js
routes/postRoutes.js
```

### Features

* Create posts
* Upload media posts
* View feed
* Delete/update posts
* Social interaction support

---

# 4.3 Stories Module

### Purpose

Implements temporary story-sharing functionality similar to Instagram/Facebook stories.

### Related Files

```text
models/Story.js
controllers/storyController.js
routes/storyRoutes.js
```

### Features

* Upload stories
* View stories
* Temporary content lifecycle
* Media story handling

---

# 4.4 Messaging / Chat Module

### Purpose

Supports direct communication between users.

### Related Files

```text
models/Message.js
models/Connection.js
controllers/messageController.js
routes/messageRoutes.js
```

### Features

* Send messages
* Receive messages
* Chat history storage
* User-to-user connections
* Conversation management

---

# 4.5 Connection / Relationship Module

### Purpose

Manages relationships between users.

### Related Files

```text
models/Connection.js
```

### Features

* User connections/friends
* Following/follower logic
* Social graph management

---

# 4.6 Media Upload Module

### Purpose

Handles file uploads and media processing.

### Related Files

```text
configs/multer.js
```

### Features

* Image upload handling
* Multipart form processing
* File validation
* Upload middleware integration

---

# 4.7 Cloud Media Storage Module

### Purpose

Stores and manages uploaded media in cloud infrastructure.

### Related Files

```text
configs/imageKit.js
```

### Features

* Cloud image hosting
* CDN delivery
* Media optimization
* Image storage management

---

# 4.8 Email Notification Module

### Purpose

Handles email-based communication.

### Related Files

```text
configs/nodeMailer.js
```

### Features

* Email sending
* OTP emails
* Password reset emails
* Notification emails

---

# 4.9 Authentication Middleware Module

### Purpose

Secures APIs and validates user access.

### Related Files

```text
middlewares/auth.js
```

### Features

* Token verification
* Protected route security
* Authorization validation
* Request authentication

---

# 4.10 Database Management Module

### Purpose

Establishes and manages database connectivity.

### Related Files

```text
configs/db.js
```

### Features

* MongoDB connection
* Database initialization
* Connection management
* Environment configuration

---

# 4.11 API Routing Module

### Purpose

Organizes backend endpoints.

### Related Files

```text
routes/
├── messageRoutes.js
├── postRoutes.js
├── storyRoutes.js
└── userRotes.js
```

### Features

* REST API endpoint management
* Route separation
* Feature-based routing

---

# 4.12 Backend Server Module

### Purpose

Main backend execution and API initialization.

### Related Files

```text
server.js
```

### Features

* Express app initialization
* Middleware loading
* Route mounting
* Server startup

---

# 4.13 Frontend UI Module

### Purpose

Provides user interface and client-side functionality.

### Related Files

```text
client/src/
├── App.jsx
├── main.jsx
└── index.css
```

### Features

* UI rendering
* Client-side routing
* State handling
* API interaction
* Responsive design

---

# 4.14 Styling & Design Module

### Purpose

Controls application styling and responsiveness.

### Related Files

```text
tailwind.config.js
index.css
```

### Features

* Responsive UI
* Utility-first styling
* Theme consistency

---

# 4.15 Deployment & Hosting Module

### Purpose

Handles deployment configuration.

### Related Files

```text
client/vercel.json
server/vercel.json
```

### Features

* Frontend deployment
* Backend deployment
* Hosting configuration

---

# 4.16 Background Workflow / Event Processing Module

### Purpose

Handles asynchronous workflows and background jobs.

### Related Files

```text
inngest/index.js
```

### Features

* Background task processing
* Event-driven workflows
* Story expiration handling
* Notification workflow management


# CHAPTER 5

# SYSTEM IMPLEMENTATION

---

## 5.1 Introduction

System implementation is the phase in which the planned design and functionalities of the ZingUp platform were converted into a working web application. The implementation process focused on frontend development, backend API integration, database management, authentication, real-time communication, and cloud-based media handling.

---

## 5.2 Frontend Implementation

The frontend of ZingUp was developed using React.js and Tailwind CSS. React.js was used to build reusable UI components and manage dynamic user interactions, while Tailwind CSS was used for responsive and modern interface design.

The frontend includes:

* authentication pages,
* developer profiles,
* social feed,
* messaging interface,
* stories section,
* and notification components.

---

## 5.3 Backend Implementation

The backend was implemented using Node.js and Express.js. REST APIs were developed for handling authentication, post management, messaging, profile handling, and social interactions.

The backend also manages:

* API routing,
* middleware processing,
* database communication,
* and server-side business logic.

---

## 5.4 Database Implementation

MongoDB Atlas was used for database management. Collections such as User, Post, Story, Message, and Connection were implemented to manage platform data efficiently.

The document-oriented database structure supports flexible and scalable storage of user-generated content and social networking data.

---

## 5.5 Authentication Implementation

Secure authentication and session management were implemented using Clerk Authentication. The authentication system manages:

* user registration,
* login,
* session handling,
* and protected route access.

This implementation improves security and simplifies authentication workflows within the platform.

---

## 5.6 Real-Time Messaging Implementation

Real-time messaging functionality was implemented using Server-Sent Events (SSE). This allows users to send and receive messages with lightweight real-time communication support.

The messaging system supports:

* one-to-one communication,
* message updates,
* and notification handling.

---

## 5.7 Media Upload and Cloud Storage Implementation

Media uploads were handled using Multer middleware and ImageKit cloud services. ImageKit was used for cloud-based image storage, optimization, and delivery.

The implementation supports:

* profile image uploads,
* post media uploads,
* story media handling,
* and optimized image delivery.

---

## 5.8 Background Task Implementation

Background tasks and asynchronous workflows were implemented using Inngest. These tasks include:

* automatic story expiration,
* notification processing,
* and scheduled background operations.

This implementation improved system automation and workflow management.

---

## 5.9 User Interface Implementation

The user interface was designed using a responsive layout approach to support both desktop and mobile devices. Tailwind CSS was used to maintain consistency, responsiveness, and modern visual design throughout the platform.

# CHAPTER 6

# SYSTEM MAINTENANCE, EVALUATION AND COST BENEFIT ANALYSIS

---

## 6.1 System Maintenance

System maintenance is important for ensuring the stability, security, and performance of the ZingUp platform after deployment. Maintenance activities include bug fixing, performance optimization, database monitoring, and feature enhancement.

The modular architecture of the platform simplifies future updates and maintenance processes. Cloud-based services such as MongoDB Atlas, Clerk Authentication, and ImageKit also improve system reliability and scalability.

---

## 6.2 System Evaluation

The ZingUp platform was evaluated based on functionality, performance, responsiveness, and usability. Testing confirmed that the system successfully supports authentication, real-time messaging, story handling, media uploads, and developer networking features.

The platform provides a responsive user interface, secure authentication system, and efficient communication workflow suitable for developer-focused collaboration and social interaction.

---

## 6.3 Cost Analysis

The development cost of ZingUp was minimized by using open-source technologies and cloud-based services. Technologies such as React.js, Node.js, Express.js, and MongoDB Atlas reduced software licensing costs.

Development tools such as Visual Studio Code and GitHub were also freely available for project development and version control.

---

## 6.4 Benefit Analysis

ZingUp provides a unified ecosystem for developers by integrating networking, communication, technical content sharing, and collaboration into a single platform.

The project demonstrates the practical implementation of full-stack web development, real-time communication systems, cloud services, and scalable software architecture. The modular design also supports future scalability and feature enhancement.

# CHAPTER 7

# TESTING AND RESULTS

---

## 7.1 Unit Testing

Unit testing was performed to verify the functionality of individual modules of the ZingUp platform independently.

### Examples:

* Login module tested with valid and invalid credentials
* Post creation module tested with text, image, and code snippet uploads
* Story upload functionality tested successfully
* Real-time messaging tested using SSE connections
* API endpoints tested using Postman

---

## 7.2 Integration Testing

Integration testing ensured that different modules of the system worked together correctly.

### Examples:

* User login → Feed loaded successfully
* Post upload → Data stored and displayed correctly
* Message sent → Receiver updated in real time
* Story upload → Media stored successfully using ImageKit
* Authentication → Protected API access verified

---

## 7.3 System Testing

System testing evaluated the complete ZingUp platform against the specified requirements.

### Checked Areas:

* Real-time messaging performance
* Feed rendering and responsiveness
* Database storage and retrieval
* Authentication and access control
* Media upload and cloud storage
* Overall system stability

---

## 7.4 User Acceptance Testing (UAT)

User Acceptance Testing was conducted to evaluate the platform from the user perspective.

### Feedback Includes:

* Ease of navigation and interaction
* Responsiveness of the user interface
* Performance of real-time messaging
* Simplicity of developer networking features
* Overall user experience and accessibility

---

## 7.5 Sample Test Case Table

| Test Case ID | Module                | Input                  | Expected Output              | Result |
| ------------ | --------------------- | ---------------------- | ---------------------------- | ------ |
| TC01         | Authentication System | Valid credentials      | User logged in successfully  | Pass   |
| TC02         | Authentication System | Invalid password       | Error message displayed      | Pass   |
| TC03         | Post Management       | Create post with media | Post uploaded successfully   | Pass   |
| TC04         | Messaging Module      | Send message           | Real-time message delivered  | Pass   |
| TC05         | Story Module          | Upload story           | Story displayed successfully | Pass   |
| TC06         | Database Storage      | User data              | Data stored correctly        | Pass   |
| TC07         | Feed Module           | Live post data         | Feed updated successfully    | Pass   |
| TC08         | API Endpoint          | Authenticated request  | Valid response returned      | Pass   |
| TC09         | Session Management    | User login/logout      | Session handled correctly    | Pass   |

---

## 7.6 Results

The ZingUp platform was successfully tested across all major modules and produced the expected results.

### Key Outcomes:

* All core functionalities operated correctly
* Real-time messaging worked efficiently using SSE
* Authentication and session handling functioned securely
* Media uploads and cloud storage worked successfully
* Database operations were accurate and reliable
* The platform maintained responsive performance across devices
* Overall system workflow operated smoothly and efficiently

# APPLICATION SCREENSHOT 
<img width="1366" height="768" alt="Screenshot (1122)" src="https://github.com/user-attachments/assets/b06da625-0632-4d6c-8b78-6f5411e199e9" />
<img width="1366" height="768" alt="Screenshot (1102)" src="https://github.com/user-attachments/assets/e14f4976-1db8-4ab4-9007-0f33fd3d9271" />
<img width="1366" height="768" alt="Screenshot (1103)" src="https://github.com/user-attachments/assets/2c0c308a-2b86-4332-bbd2-c5e0c5779f21" />
<img width="1366" height="768" alt="Screenshot (1104)" src="https://github.com/user-attachments/assets/75501f13-0d27-448a-bd0f-1444876d8a16" />
<img width="1366" height="768" alt="Screenshot (1105)" src="https://github.com/user-attachments/assets/3f6b3d10-db02-4485-8394-ed502c72af15" />
<img width="1366" height="768" alt="Screenshot (1106)" src="https://github.com/user-attachments/assets/af25d3bd-1955-451b-a918-7c055cfd88cb" />
<img width="1366" height="768" alt="Screenshot (1107)" src="https://github.com/user-attachments/assets/191c1524-dea0-4907-a593-e6469b0f11e1" />
<img width="1366" height="768" alt="Screenshot (1110)" src="https://github.com/user-attachments/assets/302fd73d-e03b-4ddc-b7b3-fbb852ff4f30" />
<img width="1366" height="768" alt="Screenshot (1111)" src="https://github.com/user-attachments/assets/ae0df552-e755-4231-8627-36973c8c9234" />




# Project Code
## frontend
##### client/src/main.jsx — App Entry Point
import { createRoot } from 'react-dom/client'
import './index.css'
import App from './App.jsx'
import {BrowserRouter} from 'react-router-dom'
import { ClerkProvider } from '@clerk/clerk-react'
import { Provider } from 'react-redux'
import { store } from './app/store.js'
import { ThemeProvider } from './context/ThemeContext'

// Import your Publishable Key
const PUBLISHABLE_KEY = import.meta.env.VITE_CLERK_PUBLISHABLE_KEY

if (!PUBLISHABLE_KEY) {
  throw new Error('Missing Publishable Key')
}

createRoot(document.getElementById('root')).render(
  <ClerkProvider publishableKey={PUBLISHABLE_KEY}>
    <BrowserRouter>
     <Provider store={store}>
      <ThemeProvider>
        <App />
      </ThemeProvider>
     </Provider>  
    </BrowserRouter>    
  </ClerkProvider>
)

##### client/src/pages/Login.jsx — Login Page
import React from 'react'
import { assets } from '../assets/assets'
import { Star } from 'lucide-react'
import { SignIn } from '@clerk/clerk-react'
import TypeWriter from '../components/TypeWriter'

const Login = () => {
  return (
    <div className='min-h-screen flex flex-col md:flex-row bg-white dark:bg-gray-900 relative overflow-hidden'>
      {/* Background Image - Full Coverage */}
      <img src={assets.bgImage} alt="" className='absolute top-0 left-0 w-full h-full object-cover opacity-35' />

     
      <div className='flex-1 flex flex-col items-start justify-between p-6 md:p-10 lg:pl-40 relative z-10'>
        <img src={assets.logo} alt="Logo" className='h-12 object-contain' />
        <div>
          <div className='flex items-center gap-3 mb-4 max-md:mt-10'>
            <img src={assets.group_users} alt="Users" className='h-8 md:h-10' />
            <div>
              <div className='flex'>
                {Array(5).fill(0).map((_, i) => (<Star key={i} className='size-4 md:size-4.5 text-transparent fill-amber-500' />))}
              </div>
              <p className='text-gray-700 dark:text-gray-300 text-sm'>Used by 10k+ developers</p>
            </div>
          </div>

          {/* Enhanced Hero Headline - Modern & Premium */}
          <div className='mt-6 md:mt-8'>
            <h1 style={{ lineHeight: '1.0' }}>
              <span
                className='block text-gray-900 dark:text-white'
                style={{ fontSize: 'clamp(2.25rem, 5vw, 3.75rem)', fontWeight: 750, letterSpacing: '-0.04em' }}
              >
                Build. Code.
              </span>
              <span className='block mt-1' style={{ fontSize: 'clamp(2.75rem, 6.5vw, 5rem)' }}>
                <TypeWriter
                  text="Collaborate."
                  speed={80}
                  className='hero-gradient-text'
                  style={{
                    fontWeight: 800,
                    letterSpacing: '-0.045em',
                  }}
                />
              </span>
            </h1>
          </div>

          {/* Modern Tagline - Clean & Professional */}
          <p className="mt-6 md:mt-7 text-gray-600 dark:text-gray-300 text-lg leading-relaxed font-medium tracking-tight">
            Where developers{" "}
            <span className="relative font-semibold text-gray-900 dark:text-white">
              build the future
              <span className="absolute left-0 -bottom-1 h-[2px] w-full bg-gradient-to-r from-violet-500 to-pink-500 rounded-full"></span>
            </span>{" "}
            together.
          </p>
        </div>
        <span className='md:h-10'></span>
      </div>

      {/* Right side: Login Form */}
      <div className='flex-1 flex items-center justify-center p-6 sm:p-10 relative z-10'>
        <SignIn />
      </div>
    </div>
  )
}

export default Login


##### client/src/pages/Profile.jsx — Profile Page

import React, { useState } from 'react'
import { Link, useParams } from 'react-router-dom'
import { dummyPostsData, dummyUserData } from '../assets/assets'
import { useEffect } from 'react'
import Loading from '../components/Loading'
import UserProfileInfo from '../components/UserProfileInfo'
import PostCard from '../components/PostCard'
import moment from 'moment'
import ProfileModal from '../components/ProfileModal'
import { useAuth } from '@clerk/clerk-react'
import api from '../api/axios'
import toast from 'react-hot-toast'
import { useSelector } from 'react-redux'
import { Pencil } from 'lucide-react'

const Profile = () => {

  const currentUser = useSelector((state) => state.user.value)

  const {getToken} = useAuth()
  const {profileId} = useParams()
  const [user, setUser] = useState(null)
  const [posts, setPosts] = useState([])
  const [activeTab, setActiveTab] = useState('posts')
  const [showEdit, setShowEdit] = useState(false)

  const fetchUser = async (profileId) => {
    const token = await getToken()
    try {
      const { data } = await api.post(`/api/user/profiles`, {profileId}, {
        headers: {Authorization: `Bearer ${token}`}
      })
      if(data.success){
        setUser(data.profile)
        setPosts(data.posts)
      }else{
        toast.error(data.message)
      }
    } catch (error) {
      toast.error(error.message)
    }
  }

  useEffect(()=>{
    if(profileId){
      fetchUser(profileId)
    }else{
      fetchUser(currentUser._id)
    }
  },[profileId, currentUser])

  return user ? (
    <div className='relative h-full overflow-y-scroll bg-gray-50 p-6'>
      <div className='max-w-3xl mx-auto'>
        {/* Profile Card */}
        <div className='bg-white rounded-2xl shadow overflow-hidden'>
          {/* Cover Photo */}
          <div className='group/cover relative h-40 md:h-56 bg-gradient-to-r from-indigo-200 via-purple-200 to-pink-200 overflow-hidden'>
            {user.cover_photo && <img src={user.cover_photo} alt='' className='w-full h-full object-cover'/>}
            {!profileId && (
              <button onClick={() => setShowEdit(true)} className='absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2 bg-black/50 hover:bg-black/70 text-white p-3 rounded-full opacity-0 group-hover/cover:opacity-100 transition-all duration-200 cursor-pointer'>
                <Pencil className='w-6 h-6'/>
              </button>
            )}
          </div>
          {/* User Info */}
          <UserProfileInfo user={user} posts={posts} profileId={profileId} setShowEdit={setShowEdit}/>
        </div>

        {/* Tabs */}
        <div className='mt-6'>
          <div className='bg-white rounded-xl shadow p-1 flex max-w-md mx-auto'>
            {["posts", "media", "likes"].map((tab)=>(
              <button onClick={()=> setActiveTab(tab)} key={tab} className={`flex-1 px-4 py-2 text-sm font-medium rounded-lg transition-colors cursor-pointer ${activeTab === tab ? "bg-indigo-600 text-white" : "text-gray-600 hover:text-gray-900"}`}>
                  {tab.charAt(0).toUpperCase() + tab.slice(1)}
              </button>
            ))}
          </div>
          {/* Posts */}
          {activeTab === 'posts' && (
            <div className='mt-6 flex flex-col items-center gap-6'>
              {posts.map((post)=> <PostCard key={post._id} post={post}/>)}
            </div>
          )}

        {/* Media */}
          {activeTab === 'media' && (
            <div className='flex flex-wrap mt-6 max-w-6xl'>
              {
                posts.filter((post)=>post.image_urls.length > 0).map((post)=>(
                  <>
                  {post.image_urls.map((image, index)=>(
                    <Link target='_blank' to={image} key={index} className='relative group'>
                      <img src={image} key={index} className='w-64 aspect-video object-cover' alt="" />
                      <p className='absolute bottom-0 right-0 text-xs p-1 px-3 backdrop-blur-xl text-white opacity-0 group-hover:opacity-100 transition duration-300'>Posted {moment(post.createdAt).fromNow()}</p>
                    </Link>
                  ))}
                  </>
                ))
              }
            </div>
          )}
        
        </div>
      </div>
      {/* Edit Profile Modal */}
      {showEdit && <ProfileModal setShowEdit={setShowEdit}/>}
    </div>
  ) : (<Loading />)
}

export default Profile

# client/src/pages/ChatBox.jsx — Real-Time Chat

import { useState } from "react"

const ChatBox = () => {

  const [text, setText] = useState("")
  const [messages, setMessages] = useState([])

  const sendMessage = () => {
    if (!text) return

    setMessages([...messages, text])
    setText("")
  }

  return (
    <div>
      
      <div>
        {messages.map((msg, i) => (
          <p key={i}>{msg}</p>
        ))}
      </div>

      <input
        type="text"
        value={text}
        placeholder="Message"
        onChange={(e) => setText(e.target.value)}
        onKeyDown={(e) => e.key === "Enter" && sendMessage()}
      />

      <button onClick={sendMessage}>
        Send
      </button>

    </div>
  )
}

export default ChatBox

##### client/src/api/axios.js — API Config
import axios from 'axios';

const api = axios.create({
    baseURL: import.meta.env.VITE_BASEURL
})

export default api

# Backend

#### server/server.js — Server Entry Point
import express from 'express';
import cors from 'cors';
import 'dotenv/config';
import connectDB from './configs/db.js';
import {inngest, functions} from './inngest/index.js'
import {serve} from 'inngest/express'
import { clerkMiddleware } from '@clerk/express'
import userRouter from './routes/userRotes.js';
import postRouter from './routes/postRoutes.js';
import storyRouter from './routes/storyRoutes.js';
import messageRouter from './routes/messageRoutes.js';

const app = express();

await connectDB();

app.use(express.json());
app.use(cors());
app.use(clerkMiddleware());

app.get('/', (req, res)=> res.send('Server is running'))
app.use('/api/inngest', serve({ client: inngest, functions }))
app.use('/api/user', userRouter)
app.use('/api/post', postRouter)
app.use('/api/story', storyRouter)
app.use('/api/message', messageRouter)

const PORT = process.env.PORT || 4000;

app.listen(PORT, ()=> console.log(`Server is running on port ${PORT}`))

#### server/configs/db.js — Database Connection
import mongoose from 'mongoose';

const connectDB = async () => {
    try {
        mongoose.connection.on('connected', ()=> console.log('Database connected'))
        await mongoose.connect(`${process.env.MONGODB_URI}/pingup`)
    } catch (error) {
        console.log(error.message)
    }
}

export default connectDB

#### server/middlewares/auth.js — Auth Middleware
export const protect = async (req, res, next) => {
    try {
        const {userId} = await req.auth();
        if(!userId){
            return res.json({success: false, message: "not authenticated"  })
        }
        next()
    } catch (error) {
        res.json({success: false, message: error.message  })
    }
}

#### server/models/User.js — User Schema

import mongoose from 'mongoose';

const userSchema = new mongoose.Schema({
    _id: {type: String, required: true },
    email: {type: String, required: true },
    full_name: {type: String, required: true },
    username: {type: String, unique: true },
    bio: {type: String, default: 'Hey there! I am using ZingUp.' },
    profile_picture: {type: String, default: '' },
    cover_photo: {type: String, default: '' },
    location: {type: String, default: '' },
    social_media: {
        linkedin: {type: String, default: ''},
        twitter: {type: String, default: ''},
        github: {type: String, default: ''},
        devto: {type: String, default: ''},
        medium: {type: String, default: ''},
        portfolio: {type: String, default: ''}
    },
    followers: [{type: String, ref: 'User' }],
    following: [{type: String, ref: 'User' }],
    connections: [{type: String, ref: 'User' }],
},{timestamps: true, minimize: false})

const User = mongoose.model('User', userSchema)

export default User

#### server/models/Connection.js — Connection Schema

import mongoose from 'mongoose';

const connectionSchema = new mongoose.Schema({
    from_user_id: {type: String, ref: 'User', required: true,},
    to_user_id: {type: String, ref: 'User', required: true,},
    status: {type: String, enum: ['pending', 'accepted'], default: 'pending'},
},{timestamps: true})

const Connection = mongoose.model('Connection', connectionSchema)

export default Connection

#### server/controllers/messageController.js — Messaging + SSE

import Message from "../models/Message.js"

const clients = {}

export const sse = (req, res) => {

  const { userId } = req.params

  res.setHeader("Content-Type", "text/event-stream")

  clients[userId] = res

  req.on("close", () => {
    delete clients[userId]
  })
}

export const sendMessage = async (req, res) => {

  const { userId } = req.auth()
  const { to_user_id, text } = req.body

  const message = await Message.create({
    from_user_id: userId,
    to_user_id,
    text
  })

  if (clients[to_user_id]) {
    clients[to_user_id].write(`data: ${JSON.stringify(message)}\n\n`)
  }

  res.json({ success: true, message })
}

export const getMessages = async (req, res) => {

  const { userId } = req.auth()
  const { to_user_id } = req.body

  const messages = await Message.find({
    $or: [
      { from_user_id: userId, to_user_id },
      { from_user_id: to_user_id, to_user_id: userId }
    ]
  })

  res.json({ success: true, messages })
}

Here's your References/Bibliography — paste directly:

---

# Conclusion
Here's your Conclusion — paste directly:

---

**CONCLUSION**

ZingUp represents a significant step towards addressing the long-standing fragmentation problem faced by the global software developer community. By integrating social networking, native code sharing, real-time messaging, ephemeral stories, and professional profile management into a single unified platform, ZingUp eliminates the need for developers to maintain multiple accounts across disconnected services and provides a focused, productive, and technically enriched environment for collaboration and networking.

The development of ZingUp successfully demonstrates the practical application of modern full-stack web technologies including React, Node.js, Express.js, and MongoDB, complemented by industry-grade cloud services such as Clerk for authentication, ImageKit for media management, Inngest for background job orchestration, and Brevo SMTP for transactional email delivery. The implementation of Server-Sent Events for real-time messaging, automated story deletion through background jobs, and a dual Follow-and-Connect relationship model collectively reflect a technically sophisticated and thoughtfully engineered system.

The project was developed following the Agile methodology across nine feature-based sprints, ensuring modular implementation, continuous testing, and incremental integration throughout the development lifecycle. All nine modules of the platform were successfully implemented, tested, and deployed on Vercel's cloud infrastructure, confirming the technical feasibility, operational stability, and scalability of the system.

In conclusion, ZingUp stands as a complete, production-deployed, and genuinely useful social media platform purpose-built for developers. It fulfils all defined objectives, demonstrates advanced software engineering principles, and establishes a strong foundation for future enhancements including AI-based recommendations, collaborative coding environments, and native mobile applications.

---

**REFERENCES**

1. Flanagan, D. (2020). *JavaScript: The Definitive Guide* (7th ed.). O'Reilly Media.

2. Banks, A., & Porcello, E. (2020). *Learning React: Modern Patterns for Developing React Apps* (2nd ed.). O'Reilly Media.

3. Chodorow, K. (2013). *MongoDB: The Definitive Guide* (2nd ed.). O'Reilly Media.

4. Cantelon, M., & Harter, M. (2014). *Node.js in Action*. Manning Publications.

5. React Official Documentation. (2024). Retrieved from https://react.dev

6. Node.js Official Documentation. (2024). Retrieved from https://nodejs.org/en/docs

7. Express.js Official Documentation. (2024). Retrieved from https://expressjs.com

8. MongoDB Official Documentation. (2024). Retrieved from https://www.mongodb.com/docs

9. Tailwind CSS Official Documentation. (2024). Retrieved from https://tailwindcss.com/docs

10. Clerk Authentication Documentation. (2024). Retrieved from https://clerk.com/docs

11. ImageKit Documentation. (2024). Retrieved from https://imagekit.io/docs

12. Inngest Documentation. (2024). Retrieved from https://www.inngest.com/docs

13. MDN Web Docs — Server-Sent Events. (2024). Retrieved from https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events

14. Redux Toolkit Documentation. (2024). Retrieved from https://redux-toolkit.js.org

15. Vercel Deployment Documentation. (2024). Retrieved from https://vercel.com/docs

---

