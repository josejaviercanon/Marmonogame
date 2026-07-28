## 🐒 Marmonogame ##

[![Platform](https://img.shields.io/badge/platform-Cross--Platform-blue)](#-cross-platform-reach)
[![Framework](https://img.shields.io/badge/framework-MonoGame-red)](https://monogame.net)
[![Vulkan](https://img.shields.io/badge/graphics-Vulkan-red)](#)
[![C#](https://img.shields.io/badge/language-C%23-239120)](#)
[![License](https://img.shields.io/badge/license-MIT-green)](#)

Marmonogame is a pocket-sized, high-performance 2D/3D hybrid engine built on top of MonoGame and .NET 10. Tailored for mid-to-high-end mobile devices, desktop (Windows, Linux via DesktopVK), and consoles, it balances the purity of classic object-oriented architecture with modern, low-overhead Vulkan rendering.
Designed specifically for small-to-medium-scale games, Marmonogame entirely skips custom ECS overhead. Instead, it relies on clean, zero-allocation game loops, dedicated C# linear algebra, and strict structural lifecycle management to deliver uncompromised performance at 60/120 FPS.

------------------------------

## 🌿 The Marmonogame Philosophy
In the wild, the [pygmy marmoset](https://www.google.com/search?q=pygmy+marmoset&kgmid=/g/11ckvdb1tq#sv=CBwS4AQKpQQSogQK4gNBSmlUNHRLYUN5WEN3ZjJqLW5ielhuc1o0SE42T1F1eWdCUExhbER6YWJwLXJnakdGNENXNlRsQ3EyYTM3S1IyVVl2MHBBUHZHMTg0aHNlWWhlLTczMGVOcUNWNU1UbUV2SEFIb1d1c1ZFOUNPUzBvMkRLal9NZWlUaWYyejlhYl8wSmRBcUlVWktGV1dldEdMU182NHVBSThlNVRzZkVsc3VvNEVuOXJkc2paQlJUcVJ2aFRvejBsWE5KQkJyM2UwN0R1T0tXSXlvM1lHd3RfMXZNUU13RUwxV0VIS280ZWtKTkRHVDV3VC1jRl9GRFJMRkFBMWwxR3owbnNLdjNVbXl4WDFGa2pPY0VEendvcWdFbTF0UktrTjctRm15bk55WDBTSklVd3hrdFYweUhIRWxlX0dYWUNIbTRqWE1DSDZqYk9WTHRvLXE4NUZSN3ZzT2hiSldHd3p4WWRsQ2ZXTTQxUExTaVRmRWtpUUYxRXVRZ0dLdU4tNGliekxSbnc3ampmT01aWVo4NHVKSmc2QVVCZzQ4TnBXenp0azVSRkppTjJSODVESVJYLTlVYkFpLWFPRDdDT1BMQlpJTHcxRC1CWXZ0cjZSR2cyeVJCOVM0SGFPd0ZWaVdibFBTYzQ0ZxIXN3p0cGF2M09INzZQd2JrUHBQS1MtUUkaIkFEc3I5ZlRBaDhBYUkxZUY4Z1pBVDdfQmJLWGJWZFVXZVESBDc4NTQaATMiEwoBcRIOcHlnbXkgbWFybW9zZXQiFgoFa2dtaWQSDS9nLzExY2t2ZGIxdHEoABhFINeWvroE) survives and thrives by being exceptionally agile, highly resourceful, and masterfully adapted to its environment. They do not rely on sheer size or brute force; instead, they navigate complex canopy ecosystems with lightning-fast reflexes, precise movement, and a highly focused footprint.
We believe a modern framework for small-to-medium indie games should work the exact same way:

* Agility Over Bloat: Say goodbye to massive, heavyweight structural overhead and complex architectural abstractions. Our framework strips away the bulk to deliver a razor-sharp, zero-allocation pipeline built strictly for speed and precision.
* Lean Resource Mastery: Maximize your hardware without exhausting your machine. By eliminating heavy engine taxation and GC micro-stutters, every single line of code is optimized to run flawlessly across mid-range mobile screens and modern desktop systems alike.
* Precision and Control: No hidden black boxes or automated guesswork. We prioritize explicit, predictable object structures and hand-coded math, giving you complete, uncompromised control over every pixel, matrix transformation, and frame lifecycle step.

------------------------------

## 🚀 Key Features & Architecture

### 🏛️ Classic Object-Oriented State Management

* No ECS Overhead: Skips complex entity-component-system indexing in favor of traditional, explicit hierarchies (GameObject, Sprite, AnimatedSprite).
* Robust Lifecycle: Built entirely around standard MonoGame GameComponent and DrawableGameComponent abstractions.
* Screen & State Management: Features a built-in ScreenManager controlling transitional states like GameplayScreen, MainMenuScreen, and PauseScreen.

### 📉 Zero-GC Game Loop Hygiene

* No-Allocation Rendering: Strict optimization practices across Update(GameTime) and Draw(GameTime) loops.
* Zero Heap Pressures: Complete avoidance of new keyword instantiations, boxing, or runtime LINQ allocations during execution frames to eliminate Garbage Collection micro-stutters.

### 🌋 Cross-Platform Vulkan Backend

* Unified Modern Graphics: Utilizes Vulkan alongside DirectX 12 for low-overhead, close-to-metal hardware access.
* Desktop & Mobile Parity: Shares a unified rendering abstraction allowing identical code execution across Android mobile devices, Linux/Windows desktops (DesktopVK), and console systems.
* Hybrid Dimensionality: Optimized for pixel-perfect 2D rendering while natively supporting the loading, transforming, and shading of low-poly 3D models.

### 📐 Linear Algebra & Shaders

* Hand-Coded Vectors & Collisions: Direct math calculations utilizing Matrix, Vector2, Vector3, Quaternion, and BoundingBox.
* Built-in Geometry Math: Native support for Axis-Aligned Bounding Boxes (AABB), Circle intersections, and Raycasting.
* Custom Shaders: High-fidelity graphical effects written in raw HLSL .fx files, compiled down natively using the mgfxc compiler.

------------------------------
### 🛠️ The Tech Stack

| Component | Library / Package | Type | Purpose |
|---|---|---|---|
| Engine Core | MonoGame.Runtime.Windows.DX12 / DesktopVK | NuGet / Core | Core framework abstraction, windowing, audio, and unified graphics management. |
| UI Framework | Gum.MonoGame | NuGet + Tool | Responsive game HUD layouts and menu management with WYSIWYG editor support. |
| Font Rendering | FontStashSharp.MonoGame | NuGet | Real-time, dynamic TTF runtime rasterization and asset atlas layout generation. |
| Animation & Assets | MonoGame.Extended | NuGet | Optimized sprite sheet sheets, texture atlas parsing, and custom camera viewport bounds. |
| Content Processing | MonoGame.Extended.Content.Pipeline | NuGet Extension | Integrates custom processors directly into the MGCB pipeline for TMX (Tiled maps). |
| Debug Tooling | ImGui.NET | NuGet | Runtime developer overlay console, object property inspectors, and visual performance graphs. |
| Physics | Aether.Physics2D | NuGet | Fast, ultra-stable Box2D-based rigid-body physics simulation. |
| Input System | Custom Engine Module | Local Wrapper | Action-based polling system mapping keyboard, touch gestures, and gamepads (IsActionPressed). |
| 2D Camera | Custom Engine Module | Local Extension | Viewport bounds management, smooth target tracking, zoom interpolations, and custom TransformMatrix calculations. |
| Game AI | Custom Engine Module | Local Engine | Finite State Machines (FSM), lightweight Behavior Trees, and multi-threaded grid-based A* pathfinding. |

------------------------------
## 📥 Installation & Setup

### Prerequisites

* [.NET 10.0 SDK](https://dotnet.microsoft.com/download) or higher.
* MonoGame MGCB Editor Tool installed globally via dotnet tools.

### 1. Initialize your project
Clone this repository or use the CLI template to bootstrap your new project:

dotnet new marmy-engine -n MyAmazingGame
cd MyAmazingGame

### 2. Restore Dependencies
Restore both native runtime libraries and additional utility packages:

dotnet restore

### 3. Build & Run
To run the game using the desktop Vulkan platform layer initialization configuration:

dotnet run --project MyAmazingGame.DesktopVK

------------------------------
## 🕹️ Quick Start Code Snippet
Developing with Marmonogame relies on defining structured screens running within a zero-allocation loop lifecycle:

~~~
using Microsoft.Xna.Framework;
using Microsoft.Xna.Framework.Graphics;
using Marmonogame.Core.Screens;

namespace MyAmazingGame.Screens;

public class GameplayScreen : GameScreen
{
    private SpriteBatch _spriteBatch;
    private Texture2D _characterSprite;
    private Vector2 _playerPosition;
    private Matrix _cameraTransform;

    public override void LoadContent()
    {
        _spriteBatch = new SpriteBatch(GraphicsDevice);
        _characterSprite = Content.Load<Texture2D>("Textures/pygmy_marmoset");
        _playerPosition = new Vector2(400, 300);
    }

    public override void Update(GameTime gameTime)
    {
        // Action-based input polling wrapper - Zero Heap Allocations
        float dt = (float)gameTime.ElapsedGameTime.TotalSeconds;
        
        if (Input.IsActionPressed("MoveLeft"))  _playerPosition.X -= 200f * dt;
        if (Input.IsActionPressed("MoveRight")) _playerPosition.X += 200f * dt;
        
        // Custom camera transformation calculation
        _cameraTransform = Camera.GetTransformMatrix();
    }

    public override void Draw(GameTime gameTime)
    {
        GraphicsDevice.Clear(Color.CornflowerBlue);

        // Standard, low-overhead sprite batch drawing matching MonoGame APIs
        _spriteBatch.Begin(transformMatrix: _cameraTransform);
        _spriteBatch.Draw(_characterSprite, _playerPosition, Color.White);
        _spriteBatch.End();
    }
}
~~~

------------------------------
💡 
