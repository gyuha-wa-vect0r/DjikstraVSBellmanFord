# Shortest Distance Performance Analysis: Comparison between Dijkstra Algorithm and Bellman-Ford Algorithm

## 📌 Project Overview
This project involves implementing the Dijkstra Algorithm and the Bellman-Ford Algorithm using Python and comparing their performance on the road network of Cheongju, Chungcheongbuk-do, based on OpenStreetMap data.  
Key points of analysis include:

- Accuracy of the shortest path  
- Execution time  
- Memory usage  
- Visual comparison of results  
- Comparison with commercial map services

---

## 🔍 Main Objectives
1. **Routing Algorithm Implementation and Advanced Study**:  
   - Implement and analyze the performance differences of the Dijkstra and Bellman-Ford algorithms.  
   - Verify the time complexity and memory efficiency of the algorithms.

2. **Practical Testing with OpenStreetMap Data**:  
   - Validate the actual operation of the algorithms using the road network data of Cheongju.

3. **Result Visualization and Comparative Analysis**:  
   - Visually represent the paths found by each algorithm and compare them with commercial map services.

---

## 💻 Development Environment
- Operating System: Ubuntu 24.04 (Windows 11 WSL2)  
- Python Version: 3.9.20

### Key Libraries Used
- **osmnx**: Generates network graphs using OpenStreetMap data.  
- **heapq**: Implements a priority queue for the Dijkstra algorithm.  
- **tracemalloc**: Tracks memory usage.  
- **time**: Measures algorithm execution time.

---

## 📊 Summary of Results
### 1️⃣ Algorithm Performance Comparison
| Algorithm     | Execution Time (s) | Memory Usage (MB) | Shortest Distance (m) |
| ------------- | ------------------ | ----------------- | --------------------- |
| Dijkstra      | 0.0416             | 0.8724            | 9548                  |
| Bellman-Ford  | 168.0751           | 0.8711            | 9548                  |

- Dijkstra Algorithm: Operates efficiently with a priority queue (heapq) and executes very quickly.
- Bellman-Ford Algorithm: Iterates over edges repeatedly, resulting in longer execution times, but can handle negative weights.

### 2️⃣ Path Comparison
- Both algorithms yield the same shortest path (9548m).
- Visualization of the path:  
  - Dijkstra path: Red  
  - Bellman-Ford path: Blue  
  - Overlapping segments: Purple

### 3️⃣ Comparison with Commercial Map Services
| Service              | Shortest Distance (m) | Key Differences                         |
| -------------------- | --------------------- | --------------------------------------- |
| Dijkstra/Bellman-Ford| 9548                  | Pure path based only on nodes and edges |
| KakaoMap             | 9600                  | Reflects real-time traffic              |
| Naver Map            | 11000                 | Considers road closures and restricted areas |

---

## 📐 Code Details

**Step 1: Data Preparation and Network Generation**
- Using OpenStreetMap data: Extracted road network data within a 6km radius of the Cheongju City Hall Clock Tower intersection.
- Road network setting: Includes only driveable roads (`network_type="drive"`).
- Network graph generation:  
  - Number of nodes: 7,389  
  - Number of edges: 21,656
- Duplication check: No duplicate nodes or edges.

**Step 2: Algorithm Implementation**
1. **Dijkstra Algorithm**
   - Time Complexity: \\( O((V+E)\log V) \\)
   - Uses a priority queue for efficient shortest path searching.
   - Path retrieval: Backtracks from the destination to the source.

2. **Bellman-Ford Algorithm**
   - Time Complexity: \\( O(V \times E) \\)
   - Repeatedly updates all edges to find the shortest path.
   - Path retrieval: Backtracks from the destination to the source.

---

## 🌟 Key Achievements

**Advanced Understanding and Implementation of Routing Algorithms**
- **Dijkstra Algorithm**: Implemented the process of efficiently finding the shortest path using a priority queue in Python.  
  - Verified the theoretical time complexity \\( O((V+E)\log V) \\) and understood efficient implementation using `heapq`.
- **Bellman-Ford Algorithm**: Implemented the structure of repeatedly updating edges.  
  - Experienced the \\( O(V \times E) \\) complexity firsthand, recognizing inefficiencies in large-scale graphs.  
  - Confirmed the usefulness in certain conditions due to its ability to handle negative edge weights.

**Practical Test Environment using OpenStreetMap Data**
- Generated a network graph using OSM data from a 6km radius around Cheongju’s City Hall Clock Tower intersection.
- Analyzed the structure of nodes and edges, visually representing road intersections and connecting roads.
- Verified data integrity by checking for duplicate nodes and edges, ensuring a reliable graph.
- Handled a large-scale dataset with 7,389 nodes and 21,656 edges, gaining experience with real urban data.

**Comparison and Visualization of Algorithm Results**
- **Performance Comparison**:  
  - Dijkstra Algorithm: Confirmed efficiency and short execution time due to the priority queue.  
  - Bellman-Ford Algorithm: Longer execution time in large graphs but more flexible in handling negative weights.  
  - Both algorithms produced the same shortest path (9548m), validating theoretical accuracy.
- **Visualization**:  
  - Displayed both algorithms' paths on the graph, showing how they overlap into a purple line where the paths coincide (red for Dijkstra and blue for Bellman-Ford).  
  - Highlighted the main route against a gray background network with small nodes.
- **Comparison with Commercial Map Services**:  
  - Examined differences with KakaoMap (9600m) and Naver Map (11000m), noting that commercial services incorporate real-time data and reflect more complex route conditions.

---

## 🛠️ Future Improvements

**Enhancing Realism with Real-Time Data Integration**
- Currently, the algorithms rely on static road data and do not incorporate dynamic information such as real-time traffic or road closures.
- Improvement directions:  
  - Utilize KakaoMap and Naver Map APIs to collect real-time data and integrate it into the graph’s weights.  
  - Example: Dynamically increase weights of heavily congested roads to reroute towards more optimal paths.
- Expected Benefits:  
  - Evolve into a more practical route-finding algorithm.  
  - Improve user experience and distinguish from commercial services.

**Introducing Advanced Algorithms**
- To overcome the limitations of traditional algorithms (Dijkstra, Bellman-Ford), explore **Graph Neural Networks (GNN)** or reinforcement learning-based pathfinding.  
- Graph Neural Networks (GNN):  
  - Represent road networks as graphs and learn relationships between nodes to predict the optimal path.  
  - Reflect real-time data during the learning process for dynamic path updates.
- Reinforcement Learning:  
  - Learn from user-chosen routes to provide personalized path recommendations.  
  - Continuously improves by rewarding user-satisfying routes.
- Expected Benefits:  
  - Significantly enhance accuracy and efficiency of AI-based route finding.  
  - Offer personalized features.

**Personalized Route Recommendations**
- Current algorithms only consider the road structure, without factoring in user driving habits, preferences, or destination characteristics.
- Improvement directions:  
  - Incorporate user-preferred road types (highways, quiet roads, etc.) or prioritize certain regions.  
  - Analyze past route choices to deliver personalized recommendations.
- Expected Benefits:  
  - Provide user-optimized routes.  
  - Increase user satisfaction and practicality.

**Integrated Comparative Study with Commercial Map Services**
- Conduct in-depth analysis of route optimization standards employed by commercial map services such as KakaoMap and Naver Map.  
- Understand how they incorporate traffic, road closures, and restricted areas.  
- Evaluate the algorithm’s practical performance through comparative experiments using commercial service APIs.

---

## 📚 References

- [Official OpenStreetMap Documentation](https://wiki.openstreetmap.org)  
- [OSMnx Documentation](https://osmnx.readthedocs.io)  
- [GeeksforGeeks: Dijkstra Algorithm](https://www.geeksforgeeks.org/dijkstras-shortest-path-algorithm-using-priority_queue-stl)  
- [GeeksforGeeks: Bellman-Ford Algorithm](https://www.geeksforgeeks.org/bellman-ford-algorithm-simple-implementation/)  
- [Python tracemalloc Official Documentation](https://docs.python.org/3/library/tracemalloc.html)
