[![TargetingArrow2D Godot Asset Library page](https://img.shields.io/static/v1?logo=godotengine&label=TargetingArrow2D&color=478CBF&message=Latest)](https://godotengine.org/asset-library/asset/5219)
![GitHub Downloads](https://img.shields.io/github/downloads/antoinecharruel/TargetingArrow2D/total)
[![Patreon](https://img.shields.io/badge/Patreon-Vivensoft-F96854?logo=patreon&logoColor=white)](https://www.patreon.com/c/vivensoft/)  
[![Bitcoin](https://img.shields.io/static/v1?logo=bitcoin&label=Bitcoin&color=F7931A&message=Donation)](https://bitaps.com/bc1qz8g4mcmynmnt0fla5aweyl0jnncp959qnshhyd)
[![Vivensoft on Itch.io](https://img.shields.io/badge/Itch.io-Vivensoft-FF5E5B?logo=itch.io&logoColor=white)](https://vivensoft.itch.io/)
[![Instagram](https://img.shields.io/badge/Instagram-VSFT%20GameDev-E4405F?logo=instagram&logoColor=white)](https://www.instagram.com/vsftgamedev/)
[![Join the Discord](https://img.shields.io/static/v1?logo=discord&label=Discord&color=7289DA&message=Vivensoft)](https://discord.gg/hZb9PGrrt9)
[![YouTube](https://img.shields.io/static/v1?logo=youtube&label=YouTube&color=FF0000&message=antoinecharruel)](https://www.youtube.com/@antoinecharruel)


# TargetingArrow2D

<p align="center">
  <img src="/docs/thumbnail/thumbnail_300x300px.png"/>
</p>

## Features

Adds a new node type for creating 2D targeting arrows using Bézier curves.

## Compatibility:

- Fully compatible with Godot 4.5.
- Cross-platform support (Linux, Windows, macOS, Android, iOS, Web/HTML5).


## Demo GDScript Example

```python
# arrow.gd
extends TargetingArrow2d

var _mouse_left_down: bool = false

# Called when the node enters the scene tree for the first time.
func _ready() -> void:
	pass


# Called every frame. 'delta' is the elapsed time since the previous frame.
func _process(_delta: float) -> void:
	var mouse_position = get_global_mouse_position()
	
	if _mouse_left_down:
		process_arrow(mouse_position)
		show()
	else: 
		hide()


func _input(event) -> void:
	if event is InputEventMouseButton:
		if event.button_index == 1 and event.is_pressed():
			# Mouse left down.
			Input.set_mouse_mode(Input.MOUSE_MODE_HIDDEN)
			_mouse_left_down = true
		elif event.button_index == 1 and not event.is_pressed():
			# Mouse left release.
			Input.set_mouse_mode(Input.MOUSE_MODE_VISIBLE)
			_mouse_left_down = false
```

[![](/docs/preview/screenshot_001.png)]()

[![](/docs/preview/screenshot_002.png)]()