![Screenshot (554)](https://github.com/user-attachments/assets/ad7715e4-e8ea-4285-942b-f4c7e2d76e23)![Screenshot (548)](https://github.com/user-attachments/assets/026c8cd4-928a-401f-9655-0d865ed9029b)# gadot_game_development_beginners


# Godot Game Development – Crash Course for Beginners

Welcome to this engaging crash course on creating your own platformer game with **Godot 4.0**! This beginner-friendly guide is perfect for those new to game development who want to learn the ins and outs of the **Godot** game engine.

## Course Overview
This crash course will guide you through:

1. **Setting up Godot 4.0**
2. **Creating your first 2D scene**
3. **Animating the player**
4. **Designing a parallax background**
5. **Implementing a simple AI enemy**
6. **Adding UI elements**
7. **Saving and loading game data**
8. **Working with collectibles**
9. **Creating a main menu and game navigation**

By the end of this course, you'll have a solid foundation in **Godot 4.0** and the skills to create your very own captivating platformer game!

## Table of Contents
1. [Downloading and Installing Godot](#downloading-and-installing-godot)
2. [Setting Up the Godot Project](#setting-up-the-godot-project)
3. [Your First 2D Scene](#your-first-2d-scene)
4. [Player Animation](#player-animation)
5. [Parallax Background](#parallax-background)
6. [Simple AI Enemy](#simple-ai-enemy)
7. [UI with Control Nodes](#ui-with-control-nodes)
8. [Saving and Loading Game Data](#saving-and-loading-game-data)
9. [Main Menu Script](#main-menu-script)
10. [Collectibles and Timers](#collectibles-and-timers)

---

## Downloading and Installing Godot
1. Go to the [official Godot website](https://godotengine.org/download).
   ![Screenshot (544)](https://github.com/user-attachments/assets/66b6ab7a-77c7-4191-a6f7-6f6ad097b3f0)
2. Download **Godot 4.3** (or the latest stable version).
3. Extract the downloaded zip file.
4. Launch `Godot 4` executable. You’re ready to begin!
   ![Screenshot (545)](https://github.com/user-attachments/assets/e4b611f8-6288-48fa-a638-6c8eaaf80a2d)
   

## Setting Up the Godot Project
1. Open Godot and create a new project.
2. Choose a location and name the project, e.g., `PlatformerGame`.
3. Select **Mobile** for a 2D game.
4. Leave version control as **None**.
5. Click **Create and Edit**.
   ![Screenshot (547)](https://github.com/user-attachments/assets/e6ac40ce-f679-4f98-9e92-3b664d858c70)

## Your First 2D Scene
1. Click on **2D Scene** and rename it to `Main`.
   ![Screenshot (548)](https://github.com/user-attachments/assets/3c15269b-88dd-45bc-b974-9173a2ccf7ad)
   ![Screenshot (549)](https://github.com/user-attachments/assets/24b7d2fc-e94d-4a2c-b42e-092cb0acb561)
   ![Screenshot (550)](https://github.com/user-attachments/assets/59dc61d7-b56c-4383-8e7d-461da20d26a2)
2. Save the scene using `Ctrl + S`.
   ![Screenshot (551)](https://github.com/user-attachments/assets/0a702361-0615-40c8-9ed6-408e184e8dba)
## Create buttons in 2D Scene 
1. Create new node
   ![Screenshot (552)](https://github.com/user-attachments/assets/2a51c867-e905-432c-a39d-6394e9d25c8a)
2. Now search for button and click create
   ![Screenshot (554)](https://github.com/user-attachments/assets/5ea4d077-d1ca-431b-93a6-bd03218439c3)
   ![Screenshot (555)](https://github.com/user-attachments/assets/46930b43-1cc5-43e0-958b-240da6e1a4ae)
3. In create tab you can enter the text display for the button , type play and you can see in display
   ![Screenshot (556)](https://github.com/user-attachments/assets/3917b231-4230-4346-9268-87ebabec7176)
4. Similarly create another button with `Quit` display
   ![Screenshot (558)](https://github.com/user-attachments/assets/b6006576-fd88-4d0d-8db9-23b43e3cf331)
## Create script
1. Click on add script
   ![Screenshot (558)](https://github.com/user-attachments/assets/1cdae3d3-4c41-4d08-834d-ff3117bab91d)
   ![Screenshot (559)](https://github.com/user-attachments/assets/bc037a98-1cb4-4762-8b3f-f4fd010de359)

## Player Animation
### Steps:
1. Add an **AnimatedSprite** node to your scene.
2. Attach a sprite sheet and set up animations for idle, run, and jump.
3. Use the **AnimationPlayer** node for more complex animations.

### Physics:
- Use **Rigidbody2D** and **CollisionShape2D** nodes to add physics.

## Parallax Background
1. Add a **ParallaxBackground** node.
2. Add a **ParallaxLayer** as a child.
3. Set up a repeating background for a scrolling effect.

## Simple AI Enemy
1. Add an **Area2D** node to create an enemy.
2. Attach a simple script to control enemy behavior.
3. Use signals to detect when the player collides with the enemy.

## UI with Control Nodes
1. Add a **Control** node as the parent for UI elements.
2. Create buttons for **Play** and **Quit**.
3. Attach scripts to handle button actions.

### Example Script for Quit Button:
```gdscript
extends Button

func _on_pressed():
    get_tree().quit()
```

## Saving and Loading Game Data
1. Use Godot’s built-in file system to save game progress.
2. Create a JSON file to store player data.
3. Use dictionaries to manage and write data.

### Example Script for Saving Data:
```gdscript
var save_data = {
    "player_score": 100,
    "level": 2
}

func save_game():
    var file = File.new()
    file.open("user://save_file.json", File.WRITE)
    file.store_string(to_json(save_data))
    file.close()
```

## Main Menu Script
1. Create a main menu scene with buttons.
2. Add scripts to navigate between scenes.

### Example Navigation Script:
```gdscript
func _on_play_button_pressed():
    get_tree().change_scene("res://scenes/Game.tscn")
```

## Collectibles and Timers
1. Add a **Timer** node to handle timed events.
2. Create collectibles using **Area2D** nodes.
3. Use signals to detect when the player collects an item.

### Example Collectible Script:
```gdscript
extends Area2D

signal collected

func _on_body_entered(body):
    if body.name == "Player":
        emit_signal("collected")
        queue_free()
```

---

## Repository Structure
```
Godot-Game-Development-Crash-Course/
├── assets/               # Folder for assets used in the game (images, sounds, etc.)
├── scenes/               # Godot scenes for the game
├── scripts/              # GD scripts for player, enemies, etc.
├── README.md             # Project documentation
└── LICENSE               # License file
```

---

## Final Thoughts
Congratulations on completing this crash course! You now have a working knowledge of **Godot 4.0** and the tools to create your own 2D platformer game. Feel free to explore more advanced features and share your creations with the community!

Happy Game Development!

---

## License
This project is licensed under the MIT License.

## Acknowledgments
Special thanks to **Omar Zaki** for creating this course.

## Contact
For questions or suggestions, feel free to open an issue or submit a pull request.
