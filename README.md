# OTT Platforms Portfolio
## Table of Contents

- [Introduction](#introduction)
- [Objectives](#objectives)
- [System Design](#system-design)
  - [Key Users](#key-users)
  - [Architecture](#architecture)
  - [Process](#process)
- [Business Cases](#business-cases)
- [Business Cases with Data Structures and Algorithms](#business-cases-with-data-structures-and-algorithms)
- [Efficiency Analysis](#efficiency-analysis)
## Introduction

<img src="data:image/jpeg;base64,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" style="display: block; margin: auto;" />
Over-The-Top (OTT) platforms have revolutionized the way we consume media by providing content directly over the internet. Unlike traditional broadcasting, OTT platforms allow users to access a wide range of content, including movies, TV shows, and live events, on-demand. This shift has empowered viewers with greater control over what, when, and how they watch content. Major OTT players like Netflix, Amazon Prime Video, and Disney+ have set new standards for content delivery, quality, and user experience. Programming plays a critical role in the operation and evolution of OTT platforms. It involves the development of algorithms and data structures to manage vast libraries of content and provide seamless, personalized user experiences.

## Objectives
- Identify Key Functionalities of OTT Platforms.
- Study Algorithms Utilized in OTT Platforms.
- Conduct Efficiency Analysis of OTT Algorithms.

## System Design

### Key Users:
- **End Users:** Individuals using various devices to access and stream content.
- **Content Providers:** Entities uploading and managing content on the platform.
- **Administrators:** Personnel managing the backend systems, content ingestion, user management, and system health monitoring.
- **Advertisers:** Businesses placing ads on the platform targeting specific user segments.

### Architecture:
![plot](./hld.avif)
#### Client Layer:
- **Devices:** Smart TVs, laptops, mobile phones, tablets, etc.
- **User Interface (UI):** Responsive and intuitive UI for content browsing, searching, and playback.

#### Content Delivery Network (CDN):
- **Third-Party CDNs:** Akamai, Cloudflare, etc., used for global content distribution.
- **Custom CDN:** Platform’s own CDN for optimized delivery, caching, and redundancy.

#### Backend Layer:
- **Content Management System (CMS):** Handles content ingestion, metadata tagging, and organization.
- **Transcoding and Encoding:** Converts video files into various formats and resolutions.
- **Distributed Storage:** Stores video content and metadata across multiple data centers.
- **User Management:** Manages user accounts, authentication, and profiles.
- **Recommendation Engine:** Provides personalized content suggestions using machine learning.
- **Analytics and Monitoring:** Tracks user interactions and system performance.

#### Scalability and Performance:
- **Microservices Architecture:** Decomposed services for flexibility and independent scaling.
- **Load Balancing:** Distributes requests to prevent server overload.
- **Elastic Compute:** Cloud-based resources for dynamic scaling.

#### Security and Compliance:
- **Data Encryption:** Protects user data and content in transit and at rest.
- **Digital Rights Management (DRM):** Secures content against piracy and unauthorized use.
- **Regulatory Compliance:** Ensures adherence to GDPR, COPPA, CCPA, and other regulations.

### Process:
#### Content Ingestion:
1. **Upload:** Content creators upload video files to the platform.
2. **Processing:** Files are transcoded and encoded into various formats and resolutions.
3. **Metadata Tagging:** Content is tagged with relevant metadata for organization and search optimization.
4. **Storage:** Processed content is stored in distributed storage for redundancy and quick access.

#### Content Distribution:
1. **Caching:** Content is cached on CDN nodes globally.
2. **Streaming:** When a user hits play, the content is delivered from the nearest CDN node.

#### User Interaction:
1. **Registration/Login:** Users create accounts or log in to access personalized features.
2. **Browsing/Search:** Users browse or search for content using the UI.
3. **Recommendations:** Personalized content recommendations are provided based on user behavior and preferences.
4. **Playback:** Users stream selected content on their devices.

#### Analytics and Optimization:
1. **Tracking:** User interactions and streaming performance are tracked.
2. **Analysis:** Data is analyzed to gain insights into user behavior, content popularity, and system performance.
3. **Optimization:** Continuous improvements are made to enhance user experience, streaming quality, and system efficiency.

## Business Cases
1. **Content Recommendation Engine**
2. **Search Optimization**
3. **User Watch History Management**
4. **Subscription Plan Optimization**
5. **Content Delivery Network (CDN) Optimization**
6. **Ad Placement Strategy**
7. **Content Popularity Prediction**
8. **User Segmentation**
9. **Load Balancing**
10. **Content Caching**
11. **User Session Management**
12. **Content Categorization**
13. **Personalized Notifications**
14. **Recently Viewed Content**
15. **Multi-Device Streaming**
16. **Transcoding**

## Business Cases with Data Structures and Algorithms
1. **Content Recommendation**
   - **Method:** ML techniques
   - **Algorithm:** K-Nearest Neighbours
   - **Description:** Recommends content based on user preferences and behavior patterns.

2. **Search Optimization**
   - **Data Structure:** Trie
   - **Algorithm:** Trie traversal algorithms (like <a href="https://github.com/Sushant-A-K/APS_Codes/blob/main/dfs.cpp">DFS</a> or <a href="https://github.com/Sushant-A-K/APS_Codes/blob/main/bfs.cpp">BFS</a>)
   - **Description:** Optimizes search queries to quickly retrieve relevant results.

3. **User Watch History Management**
   - **Data Structure:** <a href="https://github.com/Sushant-A-K/APS_Codes/blob/main/sll.c">Singly Linked List</a>
   - **Algorithm:** Insertion and deletion operations for maintaining watch history
   - **Description:** Tracks and manages the sequence of content watched by users.

4. **Subscription Plan Optimization**
   - **Data Structure:** Decision Tree
   - **Algorithm:** Decision tree algorithms (like ID3 or C4.5)
   - **Description:** Analyzes user data to recommend optimal subscription plans based on usage patterns.
     ![plot](./sub.png)

5. **Content Delivery Network (CDN) Optimization**
   - **Data Structure:** Min-Heap (for prioritizing content delivery)
   - **Algorithm:** Dijkstra's Algorithm (for shortest path in CDN routing)
   - **Description:** Optimizes CDN resource allocation and routing for efficient content delivery.

6. **Ad Placement Strategy**
   - **Data Structure:** Interval Tree (for managing ad slots)
   - **Algorithm:** Interval scheduling algorithms (like Greedy Algorithm)
   - **Description:** Places ads strategically to maximize revenue based on user engagement and content relevance.

7. **Content Popularity Prediction**
   - **Data Structure:** Hash Map (for counting content views)
   - **Algorithm:** Exponential Smoothing or Time Series Analysis
   - **Description:** Predicts future popularity of content based on historical viewing data.

8. **User Segmentation**
   - **Data Structure:** Clustering (like K-means)
   - **Algorithm:** K-means clustering algorithm
   - **Description:** Groups users into segments based on behavior and preferences for targeted marketing and content recommendations.

9. **Load Balancing**
   - **Data Structure:** Queue (for managing incoming requests)
   - **Algorithm:** Round Robin or Weighted Round Robin
   - **Description:** Distributes incoming traffic across servers to optimize resource utilization and response times.

10. **Content Caching**
    - **Data Structure:** LRU Cache (Least Recently Used)
    - **Algorithm:** LRU Cache eviction policy
    - **Description:** Stores frequently accessed content closer to users for faster retrieval and reduced server load.

11. **User Session Management**
    - **Data Structure:** Hash Table (for storing session IDs and user details)
    - **Algorithm:** Session expiration and renewal algorithms
    - **Description:** Manages user sessions to maintain login state and personalized experiences.

12. **Content Categorization**
    - **Data Structure:** Tree (for hierarchical categorization)
    - **Algorithm:** Tree traversal algorithms (like DFS or BFS)
    - **Description:** Organizes content into categories and subcategories for structured browsing and search.

13. **Personalized Notifications**
    - **Data Structure:** Priority Queue (for managing notification priorities)
    - **Algorithm:** Notification scheduling algorithms (like Delayed Notification Queue)
    - **Description:** Sends timely notifications to users based on their preferences and activities.
      ![plot](./notif.avif)

14. **Recently Viewed Content**
    - **Data Structure:** Stack (for storing recently viewed items)
    - **Algorithm:** Stack operations (push, pop)
    - **Description:** Displays a list of recently viewed content items for quick access.

15. **Multi-Device Streaming**
    - **Algorithm:** Streaming protocols (like HLS or MPEG-DASH)
    - **Description:** Enables seamless streaming across different devices while maintaining playback synchronization.

16. **Transcoding**
    - **Algorithm:** Transcoding algorithms like FFmpeg
    - **Description:** Converts media content into different formats to ensure compatibility across various devices and bandwidth conditions.

## Efficiency Analysis

| Algorithm / Data Structure              | Time Complexity (Worst Case)           | Space Complexity (Worst Case)    |
|-----------------------------------------|----------------------------------------|----------------------------------|
| Singly Linked List (SLL)                | Access: O(n)<br>Search: O(n)<br>Insert: O(1)<br>Delete: O(1) | O(n)                           |
| Depth-First Search (DFS)                | O(V + E)                               | O(V)                             |
| Breadth-First Search (BFS)              | O(V + E)                               | O(V)                             |
| Dijkstra's Algorithm                    | O((V + E) log V)                       | O(V)                             |
| K-means Clustering                      | O(n * k * I * d)<br>where:<br>n = number of data points<br>k = number of clusters<br>I = number of iterations<br>d = dimensionality of data | O(n * k)                         |
| k-Nearest Neighbors (kNN)               | O(n * d)<br>where:<br>n = number of data points<br>d = dimensionality of data | O(n)                             |
| Round Robin Scheduling                  | O(1) per time quantum                  | O(n)                             |
| Stack (Push and Pop operations)         | O(1) for both push and pop             | O(n)                             |
| Interval Scheduling Algorithm           | O(n log n)                             | O(n)                             |
| Hash Map (Average Case)                 | Insert: O(1)<br>Search: O(1)<br>Delete: O(1) | O(n)                             |
| Least Recently Used (LRU) Cache         | O(1) for both get and put operations   | O(capacity)                      |

**Notes:**
- **SLL (Singly Linked List)**: Operations are listed for worst-case complexities.
- **DFS and BFS**: V is the number of vertices, and E is the number of edges.
- **Dijkstra's Algorithm**: Depends on the implementation (e.g., using a Fibonacci heap can improve the time complexity for dense graphs).
- **K-means Clustering**: I is the number of iterations until convergence, and d is the dimensionality of the data.
- **Interval Scheduling Algorithm**: Assumes sorting intervals by their end times.
- **LRU Cache**: Capacity denotes the maximum number of items the cache can hold.
