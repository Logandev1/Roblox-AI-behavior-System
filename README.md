# AI Behavior System

## Overview
This project is a modular AI Behavior System designed for Roblox NPCs. It uses a state machine architecture to create intelligent, reactive NPC behavior with clean, scalable code.

The system includes the following behaviors:
- Idle
- Patrol
- Chase
- Attack
- Search
- Flee
- Full animation support (Idle, Walk, Attack, Search, Flee)

---

## Features

### Modular State Machine
Each behavior is isolated into its own state with OnEnter, OnExit, and OnUpdate functions.

### Dynamic Target Detection
NPCs automatically detect the nearest player and evaluate distance and line of sight.

### Search Behavior
When the NPC loses sight of the target, it rotates and scans the area before returning to patrol.

### Flee Behavior
NPC retreats to a random safe location when health drops below a threshold.

### Animation Controller
Supports Idle, Walk, Attack, Search, and Flee animations through a unified animation loader.

### Patrol System
NPC moves between predefined patrol points with configurable timing.

### Expandable Architecture
New states can be added easily (Guard, Investigate, Cover, etc.).

---

## File Structure

ReplicatedStorage
│
├── AIBehaviorSystem (ModuleScript)
│
ServerScriptService
│
├── AIControllerExample (Script)
│
Workspace
│   ├── EnemyNPC (Model)
│   ├── PatrolPoints (Folder with Parts)



---

## Configuration

### AI Settings
Inside AIControllerExample, configure the AI system:

```lua
local ai = AIBehaviorSystem.new(npcModel, {
    MaxChaseDistance = 80,
    AttackRange = 8,
    MaxReturnDistance = 120,

    Animations = {
        Idle = "rbxassetid://IDLE_ANIM_ID",
        Walk = "rbxassetid://WALK_ANIM_ID",
        Attack = "rbxassetid://ATTACK_ANIM_ID",
        Search = "rbxassetid://SEARCH_ANIM_ID",
        Flee = "rbxassetid://FLEE_ANIM_ID",
    }
})

