# Hospital Management System — DSA Showcase

A console-based hospital management system built to demonstrate practical applications of core data structures and algorithms.

This is a learning/portfolio project focused on implementing and applying DSA fundamentals in a realistic domain, rather than a production system.

## Overview

The system models hospital roles (doctors, patients, pharmacists) and city-wide emergency logistics (hospitals, ambulances, routing) through a text-menu interface. All data lives in memory for the duration of a session — there is no persistence layer.

The point of the project is the data structures underneath it: rather than leaning on Python's built-in containers, it implements its own linked list, queue, stack, hash map, graph, binary search tree, and trie, and puts each one to a concrete use.

## Tech Stack

- **Language:** Python
- **Visualization:** `networkx`, `matplotlib` (for rendering the live city graph)

## Data Structures

- **`LinkedList`** — singly linked list with insert/delete/display
- **`Queue`** and **`Stack`** — model a doctor's patient queue and visit history respectively
- **`HashMap`** — custom hash table with chaining, used for route history lookups
- **`Graph`** — adjacency-list graph supporting weighted, directed edges, with:
  - **Dijkstra's algorithm** for shortest-path routing between locations
  - **A\* search** for allocating the nearest ambulance to a patient
  - Live visualization of the city graph (hospitals, ambulances, routes) via `networkx`/`matplotlib`
- **`DrugTree`** — a binary search tree storing the pharmacy's drug inventory, sorted by ID
- **`Trie`** — prefix tree powering autocomplete for drug name search

## Simulated Roles

- **Doctor** — manages a patient queue (`Queue`) and a history of completed visits (`Stack`)
- **Patient** — books or cancels appointments with a doctor
- **Pharmacist** — adds, deletes, and searches drugs via the `DrugTree`, with prefix-based autocomplete via the `Trie`
- **Emergency Management** — adds/removes hospitals and ambulances, allocates the nearest ambulance to a patient using A*, and visualizes the resulting city graph in real time

## Running It

```bash
git clone https://github.com/iiamsepehr/Hospital_Program.git
cd Hospital_Program/version-without-database

pip install networkx matplotlib
python main.py
```

The menu preloads sample doctors, patients, drugs, hospitals, and ambulances, so you can explore every role immediately without manual setup.

## Project Structure

```
version-without-database/
  DataStructures.py   # LinkedList, Queue, Stack, HashMap, Graph, DrugTree, Trie
  main.py              # Role menus, emergency management, preload data
```

## Roadmap

- Add a `requirements.txt` for reproducible installs
- Add automated tests for the custom data structures (`LinkedList`, `Graph`, `DrugTree`, `Trie`) — none currently exist
- Add input validation on the console menus (e.g. numeric fields currently assume well-formed input)
- Consider persisting state between sessions, if the project moves beyond a DSA demonstration

## License

MIT — see [LICENSE](LICENSE).
>>>>>>> 1e6d51b (README updated)
