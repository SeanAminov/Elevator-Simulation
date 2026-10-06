# Elevator Simulation

An event-driven elevator simulator in Java with a JavaFX view. I built it with a team of three in my high school Java application development class (Sep to Dec 2022) and worked on the backend.

## How it works

- Each elevator is a finite state machine with seven states: stop, move to floor, open door, offload, board, close door and move one floor.
- Passengers arrive over time from a CSV file and wait in queues on each floor, split by direction. If they wait too long, they give up.
- A call manager picks the floor each elevator serves next, and the building advances every elevator one tick at a time.
- The JavaFX view animates the elevator, its doors and the passengers as the simulation runs.

## Configuration

`ElevatorSimConfig.csv` sets up a run:

| Setting | Example | What it controls |
|---|---|---|
| numFloors | 6 | Floors in the building |
| numElevators | 1 | Elevators in the building |
| passCSV | ElevatorTest.csv | File of passenger arrivals |
| capacity | 15 | Passengers an elevator can hold |
| floorTicks | 5 | Ticks to travel one floor |
| doorTicks | 2 | Ticks to open or close the doors |
| passPerTick | 3 | Passengers who can board or leave per tick |

## Tests

The `BuildingFSM*Test` and `BuildingFullElevatorTests` classes run scenarios for basic moves, capacity, passengers giving up, call policy and full runs, and log each run so it can be checked against the expected output.

## Run it

It's a Java project with a Gradle build file. Run `ElevatorSimulation` with JavaFX available.

## Built with

Java, JavaFX, Gradle
