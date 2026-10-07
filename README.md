# TeletexTUI
Lightweight terminal-based RSS reader

## Base Repository Structure

```
teletextui/
├── CMakeLists.txt
├── .gitignore
├── README.md
└── src/
    ├── main.cpp
    │
    ├── core/
    │   └── models.h
    │
    ├── db/
    │   ├── database.h
    │   └── database.cpp
    │
    ├── daemon/
    │   ├── network.h
    │   ├── network.cpp
    │   ├── parser.h
    │   └── parser.cpp
    │
    └── tui/
        ├── app.h
        └── app.cpp
```
