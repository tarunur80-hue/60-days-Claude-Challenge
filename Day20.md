# Application Development with Claude
# Day 20
# Build an AI Face Puzzle Game
# Turn your face into an interactive puzzle game

## Claude can generate complete browser applications including UI design, game mechanics, camera integration, image processing, local storage, and interactive experiences. This demonstrates how AI can accelerate software development from idea to working product.
    
    1 Game Development: Build interactive browser games without manual coding.
    2 Web APIs: Use browser camera APIs and media devices.
    3 Image Processing: Convert captured photos into playable puzzle pieces.
    4 Interactive UI: Create responsive experiences for desktop and mobile.

# Prompt:
    ## Given:
    You are an expert front-end developer. Build me a complete, fully working face puzzle game as a single self-contained HTML file (no external dependencies except what can load from cdnjs.cloudflare.com, cdn.jsdelivr.net, or unpkg.com).
    
    FEATURES REQUIRED — deliver ALL of these in one complete response:
    
    1. CAMERA ACCESS
       - On load, request webcam permission using getUserMedia()
       - Show a live video preview (front-facing camera preferred)
       - Display a 'Take Photo' button to snapshot the user's face onto a canvas
    
    2. PUZZLE GENERATION
       - After snapshot, let the user choose difficulty: 3×3, 4×4, or 5×5 grid
       - Slice the captured face image into equal puzzle pieces
       - Randomly scramble the pieces (guarantee it is solvable)
       - Render each piece as a draggable tile at its scrambled position
    
    3. DRAG & TOUCH GESTURE CONTROLS
       - Support both mouse drag (desktop) and touch drag (mobile/tablet)
       - When a piece is dropped onto another piece's cell, swap their positions
       - Snap pieces to the nearest grid cell on release
       - Highlight a piece with a coloured border while it is being dragged
       - Show a green border on pieces that land in their correct position
    
    4. TIMER & MOVE COUNTER
       - Start the timer the moment the puzzle begins
       - Display elapsed time live (format: mm:ss.t)
       - Count and display total moves made
       - Show how many pieces are correctly placed out of the total
    
    5. WIN DETECTION & RESULTS SCREEN
       - Detect automatically when all pieces are in the correct position
       - Stop the timer immediately on win
       - Show a results overlay with: final time, total moves, and difficulty
       - Save the top 5 best times to localStorage with date, time, moves, and difficulty
       - Display a leaderboard of saved best times
    
    6. UI & POLISH
       - Clean, modern design
       - Works on desktop and mobile
       - 'Retake Photo' button
       - 'Play Again' button
       - 'New Photo' button
       - Responsive layout
    
    TECHNICAL REQUIREMENTS:
    - Single HTML file
    - All CSS and JS inline
    - No frameworks
    - Must work in Chrome, Firefox, and Safari
    - Camera must work over HTTPS or localhost
    - Handle camera permission denied gracefully
    - Do NOT leave placeholder comments
    
    Output the complete HTML file in one code block. Do not truncate or summarise any section.
## Modified:
    Where acess to local disk is also given:

    You are an expert front-end developer. Build me a complete, fully working face puzzle game as a single self-contained HTML file (no external dependencies except what can load from cdnjs.cloudflare.com, cdn.jsdelivr.net, or unpkg.com).

    FEATURES REQUIRED — deliver ALL of these in one complete response:
    
    1. IMAGE INPUT OPTIONS (CAMERA + LOCAL UPLOAD)
       - On load, request webcam permission using getUserMedia()
       - Prefer the front-facing camera
       - Show a live webcam preview
       - Provide a "Take Photo" button to capture the user's face from the camera onto a canvas
       - Also provide an option to upload images from the local device
       - Add an "Upload Photo" button using file input
       - Support JPG, PNG, and WEBP formats
       - Allow the user to choose between:
            a) Taking a photo using webcam
            b) Uploading an existing photo from local storage
       - After selecting/uploading an image, show a preview before starting the puzzle
       - Include a "Retake Photo" / "Choose Another Photo" option
    
    2. PUZZLE GENERATION
       - After a photo is captured or uploaded, allow the user to choose difficulty:
            - 3×3 grid
            - 4×4 grid
            - 5×5 grid
       - Crop and scale the image correctly to fit the puzzle area
       - Slice the selected face image into equal puzzle pieces using canvas
       - Generate puzzle tiles from the image pieces
       - Randomly scramble the pieces
       - Ensure the shuffle is always solvable
       - Render each puzzle piece as a draggable tile in its scrambled position
    
    3. DRAG & TOUCH GESTURE CONTROLS
       - Support:
            - Mouse drag on desktop
            - Touch drag on mobile/tablet
       - When a tile is dropped onto another tile position:
            - Swap the two pieces
       - Snap pieces automatically to the nearest grid cell
       - Highlight the currently dragged piece with a colored border
       - Show a green border for pieces placed in the correct position
       - Prevent pieces from moving outside the puzzle area
    
    4. TIMER & MOVE COUNTER
       - Start timer immediately when puzzle starts
       - Display live elapsed time in format:
            mm:ss.t
       - Count total moves made
       - Display:
            - Current moves
            - Correctly placed pieces / total pieces
            - Completion percentage
    
    5. WIN DETECTION & RESULTS SCREEN
       - Automatically detect when all puzzle pieces are in the correct position
       - Stop timer immediately after completion
       - Show a results overlay containing:
            - Final time
            - Total moves
            - Difficulty level
            - Number of pieces
       - Save top 5 best scores using localStorage
       - Store:
            - Date
            - Completion time
            - Number of moves
            - Difficulty
       - Display a leaderboard showing best times
       - Sort leaderboard by fastest completion time
    
    6. GAME CONTROLS
       Include:
       - "Start Puzzle" button
       - "Play Again" button
       - "New Photo" button
       - "Retake Photo" button
       - "Upload Different Photo" button
    
    7. UI & POLISH
       - Create a clean modern UI
       - Responsive design for:
            - Desktop
            - Mobile
            - Tablet
       - Use smooth animations
       - Add polished transitions when swapping pieces
       - Make buttons modern and accessible
       - Show helpful messages for camera permission errors
       - Handle:
            - Camera denied
            - No camera available
            - Invalid image upload
            - Large image files
       - Ensure the game works in:
            - Chrome
            - Firefox
            - Safari
    
    TECHNICAL REQUIREMENTS:
    - Single HTML file only
    - All HTML, CSS, and JavaScript must be inline
    - No frameworks
    - No backend
    - No build tools
    - No external assets
    - Only allow libraries from:
        cdnjs.cloudflare.com
        cdn.jsdelivr.net
        unpkg.com
    - Camera must work over HTTPS or localhost
    - Use modern browser APIs
    - Code must be complete and directly runnable
    - Do not use placeholder comments
    - Do not omit any section
    
    OUTPUT REQUIREMENT:
    Return the complete HTML file inside ONE code block.
    Do not explain.
    Do not summarize.
    Do not truncate any part of the code.

# Output;

HTML : <img width="1920" height="890" alt="Untitled3" src="https://github.com/user-attachments/assets/2e9d386a-e46f-4f95-8451-a41e2f6034da" />
<img width="1920" height="889" alt="Untitled1" src="https://github.com/user-attachments/assets/8a2f876c-f31b-4c56-8ac5-a499a686ecd1" />
<img width="1920" height="892" alt="Untitled" src="https://github.com/user-attachments/assets/a14a5e37-5d88-4de0-8d3b-cc4d41976091" />
[face-puzzle-game.html](https://github.com/user-attachments/files/29164877/face-puzzle-game.html)

            
