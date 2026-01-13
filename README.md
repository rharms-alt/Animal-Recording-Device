# Animal-Recording-Device
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Campus Wildlife Journal</title>
    <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;700&display=swap" rel="stylesheet">
    <style>
        :root { --primary: #3c5a82; --accent: #64b5f6; --bg: #f0f4f8; }
        body { font-family: 'Quicksand', sans-serif; background: var(--bg); margin: 0; padding: 0; }
        header { background: var(--primary); color: white; padding: 20px; text-align: center; }
        .container { padding: 20px; max-width: 800px; margin: auto; }
        .card { background: white; border-radius: 15px; margin-bottom: 20px; overflow: hidden; box-shadow: 0 4px 10px rgba(0,0,0,0.1); }
        .img-box { width: 100%; height: 200px; background-size: cover; background-position: center; background-color: #ddd; }
        .info { padding: 15px; text-align: center; }
        .btn { background: var(--accent); color: white; border: none; padding: 15px; width: 100%; border-radius: 10px; font-weight: bold; font-size: 16px; margin-top: 10px; }
        /* Error Message Style */
        #error-msg { display: none; background: #fee2e2; color: #b91c1c; padding: 20px; margin: 20px; border-radius: 10px; border: 1px solid #f87171; }
    </style>
</head>
<body>

<header>
    <h1>🔍 Campus Wildlife</h1>
    <p>Scientific Observation Terminal</p>
</header>

<div id="error-msg">⚠️ System Error: The JavaScript failed to start. Please try refreshing.</div>

<div class="container" id="main-content">
    <div id="grid">
        <p style="text-align:center; color:#999;">Loading Campus Map...</p>
    </div>
</div>

<script>
    // Safety check to ensure script runs
    window.onerror = function(msg) {
        document.getElementById('error-msg').style.display = 'block';
        document.getElementById('error-msg').innerHTML = "Script Error: " + msg;
    };

    const animals = [
        { name: "Gray Squirrel", img: "https://images.unsplash.com/photo-1504208434309-cb69f4fe52b0?w=500" },
        { name: "American Robin", img: "https://images.unsplash.com/photo-1620188461014-99765437818b?w=500" }
    ];

    function init() {
        const grid = document.getElementById('grid');
        grid.innerHTML = ''; // Clear loading text
        
        animals.forEach(a => {
            grid.innerHTML += `
                <div class="card">
                    <div class="img-box" style="background-image: url('${a.img}')"></div>
                    <div class="info">
                        <h3>${a.name}</h3>
                        <button class="btn" onclick="alert('Viewing ${a.name}')">View Observations</button>
                    </div>
                </div>
            `;
        });
    }

    // Run when page loads
    window.onload = init;
</script>
</body>
</html>
