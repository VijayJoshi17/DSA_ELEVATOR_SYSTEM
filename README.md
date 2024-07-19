# Elevator Management System

## Overview

The Elevator Management System is a simple console-based application written in C that simulates an elevator's operations in a building. The system allows users to manage the elevator's floor requests, handle the number of people in the elevator, and adjust the elevator's direction and movement based on the requests.

## Features

- **Add People to the Elevator**: Users can specify the floors where they want to go. The elevator will record these requests in a linked list.
- **Remove People from the Elevator**: When the elevator reaches a floor, people wanting to get off are removed from the list.
- **Dynamic Direction Management**: The elevator automatically determines the direction (up or down) based on the floor requests and the current position.
- **Overflow Handling**: The elevator has a maximum capacity of 10 people. It will skip floors if it is full.
- **Movement Control**: The elevator changes direction when it reaches the top or bottom of the building.

## Code Breakdown

### Structures

- **`struct floor`**: Defines a node in a linked list that stores the target floor number and a pointer to the next node.

### Functions

- **`struct floor *add(struct floor *head, int no_people, int pos)`**: Adds new floor requests to the linked list, excluding the current floor.
- **`struct floor *remove_people(struct floor *head, int pos)`**: Removes all nodes with the current floor number from the linked list.
- **`void print_link_list(struct floor *head)`**: Prints the list of floors where people want to go.
- **`int count_people(struct floor *head)`**: Counts the number of people currently in the elevator.
- **`bool fetch_direction(struct floor *head, bool direction, int pos)`**: Determines the direction the elevator should move based on the floor requests.
- **`int fetch_till(struct floor *head, bool direction)`**: Determines the floor at which the elevator should stop based on its current direction.

### Main Function

1. **Initialization**: Reads the building height and the initial position of the elevator.
2. **Loop**: Continuously processes requests and updates the elevator’s position until the user decides to stop:
   - Removes people from the current floor.
   - Adds new people to the elevator.
   - Determines and updates the elevator's direction and stopping point.
   - Handles the elevator’s movement between floors.

## Usage

1. **Compile the Program**: Use a C compiler like `gcc` to compile the program.
   ```sh
   gcc -o elevator elevator.c

2. **Run the Program**:
   ```sh
   ./elevator
   
