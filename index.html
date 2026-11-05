<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Supervivencia Espacial 3D</title>
    <!-- Importamos la librería Three.js -->
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <style>
        :root {
            --bg-color: #12121c;
            --panel-bg: #1e1e2e;
            --text-main: #cdd6f4;
            --text-muted: #a6adc8;
            --accent: #89b4fa;
            --danger: #f38ba8;
            --success: #a6e3a1;
            --warning: #f9e2af;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            user-select: none;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background-color: var(--bg-color);
            color: var(--text-main);
            display: flex;
            height: 100vh;
            overflow: hidden;
        }

        /* Contenedor del Juego */
        #game-container {
            flex-grow: 1;
            position: relative;
            background-color: #2b3b2b; /* Color base del planeta */
        }

        canvas {
            display: block;
            width: 100%;
            height: 100%;
        }

        /* Panel Lateral (UI) */
        #ui-panel {
            width: 320px;
            background-color: var(--panel-bg);
            border-left: 2px solid #313244;
            display: flex;
            flex-direction: column;
            padding: 20px;
            box-shadow: -5px 0 15px rgba(0,0,0,0.5);
            z-index: 10;
            overflow-y: auto;
        }

        h1 {
            font-size: 1.5rem;
            color: var(--accent);
            text-align: center;
            margin-bottom: 20px;
            text-transform: uppercase;
            letter-spacing: 2px;
        }

        h2 {
            font-size: 1.1rem;
            margin-bottom: 10px;
            color: var(--text-muted);
            border-bottom: 1px solid #45475a;
            padding-bottom: 5px;
        }

        /* Barras de Estadísticas */
        .stat-box {
            margin-bottom: 15px;
        }
        
        .stat-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
            font-size: 0.9rem;
            font-weight: bold;
        }

        .bar-container {
            width: 100%;
            height: 12px;
            background-color: #313244;
            border-radius: 6px;
            overflow: hidden;
        }

        .bar-fill {
            height: 100%;
            width: 100%;
            border-radius: 6px;
            transition: width 0.3s ease, background-color 0.3s ease;
        }

        #energy-bar { background-color: var(--accent); }
        #hunger-bar { background-color: var(--warning); }

        /* Inventario */
        .inventory-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            margin-bottom: 20px;
        }

        .inv-item {
            background-color: #313244;
            border-radius: 8px;
            padding: 10px;
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            position: relative;
        }

        .inv-count {
            margin-top: 5px;
            font-size: 0.9rem;
            font-weight: bold;
            color: var(--text-main);
        }

        /* Crafteo */
        .craft-item {
            background-color: #313244;
            border-radius: 8px;
            padding: 15px;
            margin-bottom: 10px;
        }

        .craft-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 8px;
        }

        .craft-title {
            font-weight: bold;
            display: flex;
            align-items: center;
            gap: 5px;
        }

        .craft-reqs {
            font-size: 0.8rem;
            color: var(--text-muted);
            margin-bottom: 10px;
        }

        button {
            width: 100%;
            padding: 10px;
            border: none;
            border-radius: 6px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.2s;
        }

        .btn-craft {
            background-color: var(--accent);
            color: #11111b;
        }
        
        .btn-craft:hover:not(:disabled) {
            background-color: #b4befe;
        }

        .btn-craft:disabled {
            background-color: #45475a;
            color: #7f849c;
            cursor: not-allowed;
        }

        .btn-eat {
            background-color: var(--success);
            color: #11111b;
            margin-bottom: 20px;
        }

        .btn-eat:hover {
            background-color: #a6e3a1;
            filter: brightness(1.1);
        }

        /* Mensajes e Indicadores */
        #time-indicator {
            text-align: center;
            font-weight: bold;
            margin-bottom: 20px;
            padding: 10px;
            border-radius: 8px;
            background-color: #313244;
        }

        /* Notificaciones on-screen */
        #notification-area {
            position: absolute;
            top: 20px;
            left: 50%;
            transform: translateX(-50%);
            pointer-events: none;
            display: flex;
            flex-direction: column;
            gap: 10px;
            z-index: 20;
        }

        .toast {
            background: rgba(30, 30, 46, 0.9);
            color: white;
            padding: 10px 20px;
            border-radius: 20px;
            font-size: 0.9rem;
            animation: fadeinout 2.5s forwards;
            border: 1px solid #45475a;
        }

        @keyframes fadeinout {
            0% { opacity: 0; transform: translateY(-20px); }
            15% { opacity: 1; transform: translateY(0); }
            85% { opacity: 1; transform: translateY(0); }
            100% { opacity: 0; transform: translateY(-20px); }
        }
    </style>
</head>
<body>

    <div id="game-container">
        <div id="notification-area"></div>
        <canvas id="gameCanvas"></canvas>
    </div>

    <div id="ui-panel">
        <h1>Explorador</h1>
        
        <div id="time-indicator">Día 1 - Mañana ☀️</div>

        <h2>Estado</h2>
        <div class="stat-box">
            <div class="stat-header">
                <span>Energía</span>
                <span id="energy-text">100%</span>
            </div>
            <div class="bar-container">
                <div id="energy-bar" class="bar-fill"></div>
            </div>
        </div>
        <div class="stat-box">
            <div class="stat-header">
                <span>Hambre</span>
                <span id="hunger-text">100%</span>
            </div>
            <div class="bar-container">
                <div id="hunger-bar" class="bar-fill"></div>
            </div>
        </div>

        <button id="btn-eat" class="btn-eat">Comer Baya (Teclado: E)</button>

        <h2>Inventario</h2>
        <div class="inventory-grid">
            <div class="inv-item">
                🪵
                <div class="inv-count" id="inv-wood">0</div>
            </div>
            <div class="inv-item">
                🪨
                <div class="inv-count" id="inv-stone">0</div>
            </div>
            <div class="inv-item">
                🍒
                <div class="inv-count" id="inv-berry">0</div>
            </div>
        </div>

        <h2>Construcción</h2>
        <div class="craft-item">
            <div class="craft-header">
                <div class="craft-title">🔥 Fuego</div>
            </div>
            <div class="craft-reqs">Coste: 5 🪵, 2 🪨<br>Efecto: Calor en la noche</div>
            <button id="btn-craft-fire" class="btn-craft">Construir</button>
        </div>

        <div class="craft-item">
            <div class="craft-header">
                <div class="craft-title">⛺ Tienda</div>
            </div>
            <div class="craft-reqs">Coste: 15 🪵<br>Efecto: Base segura</div>
            <button id="btn-craft-tent" class="btn-craft">Construir</button>
        </div>
    </div>

    <script>
        // === CONFIGURACIÓN DE THREE.JS ===
        const container = document.getElementById('game-container');
        // Ocultamos el canvas original 2D (Three.js creará el suyo)
        document.getElementById('gameCanvas').style.display = 'none';

        const scene = new THREE.Scene();
        // Color del cielo inicial (Día)
        scene.background = new THREE.Color(0x87CEEB); 
        scene.fog = new THREE.Fog(0x87CEEB, 100, 400);

        const camera = new THREE.PerspectiveCamera(60, container.clientWidth / container.clientHeight, 0.1, 1000);
        
        const renderer = new THREE.WebGLRenderer({ antialias: true });
        renderer.setSize(container.clientWidth, container.clientHeight);
        renderer.shadowMap.enabled = true;
        renderer.shadowMap.type = THREE.PCFSoftShadowMap;
        container.appendChild(renderer.domElement);

        window.addEventListener('resize', () => {
            camera.aspect = container.clientWidth / container.clientHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(container.clientWidth, container.clientHeight);
        });

        // === ILUMINACIÓN ===
        const ambientLight = new THREE.AmbientLight(0xffffff, 0.6); // Luz general
        scene.add(ambientLight);

        const sunLight = new THREE.DirectionalLight(0xffffff, 0.8);
        sunLight.position.set(100, 200, 100);
        sunLight.castShadow = true;
        sunLight.shadow.camera.left = -200;
        sunLight.shadow.camera.right = 200;
        sunLight.shadow.camera.top = 200;
        sunLight.shadow.camera.bottom = -200;
        scene.add(sunLight);

        // === MUNDO Y ENTORNOS ===
        const MAP_SIZE = 1500;
        const groundGeo = new THREE.PlaneGeometry(MAP_SIZE, MAP_SIZE);
        const groundMat = new THREE.MeshStandardMaterial({ color: 0x2b3b2b, roughness: 0.8 });
        const ground = new THREE.Mesh(groundGeo, groundMat);
        ground.rotation.x = -Math.PI / 2;
        ground.receiveShadow = true;
        scene.add(ground);

        // Límites del mapa (Muros invisibles)
        const wallMat = new THREE.MeshBasicMaterial({ color: 0xf38ba8, wireframe: true, transparent: true, opacity: 0.2 });
        const wallGeo = new THREE.BoxGeometry(MAP_SIZE, 50, 10);
        
        const walls = [
            new THREE.Mesh(wallGeo, wallMat), new THREE.Mesh(wallGeo, wallMat),
            new THREE.Mesh(wallGeo, wallMat), new THREE.Mesh(wallGeo, wallMat)
        ];
        walls[0].position.set(0, 25, -MAP_SIZE/2);
        walls[1].position.set(0, 25, MAP_SIZE/2);
        walls[2].position.set(-MAP_SIZE/2, 25, 0); walls[2].rotation.y = Math.PI/2;
        walls[3].position.set(MAP_SIZE/2, 25, 0); walls[3].rotation.y = Math.PI/2;
        walls.forEach(w => scene.add(w));

        // === JUGADOR 3D ===
        const playerGroup = new THREE.Group();
        
        // Cuerpo
        const bodyGeo = new THREE.CylinderGeometry(2, 2, 6, 16);
        const bodyMat = new THREE.MeshStandardMaterial({ color: 0xcdd6f4 });
        const body = new THREE.Mesh(bodyGeo, bodyMat);
        body.position.y = 3;
        body.castShadow = true;
        
        // Cabeza (Casco de explorador)
        const headGeo = new THREE.SphereGeometry(2.5, 16, 16);
        const headMat = new THREE.MeshStandardMaterial({ color: 0x89b4fa, metalness: 0.5, roughness: 0.2 });
        const head = new THREE.Mesh(headGeo, headMat);
        head.position.y = 7;
        head.castShadow = true;

        playerGroup.add(body);
        playerGroup.add(head);
        
        playerGroup.position.set(0, 0, 0);
        scene.add(playerGroup);

        // === CONSTANTES Y ESTADO DEL JUEGO ===
        const DAY_DURATION = 60000;
        const keys = { w: false, a: false, s: false, d: false, arrowup: false, arrowleft: false, arrowdown: false, arrowright: false };
        
        const playerState = {
            speed: 40, // Unidades de Three.js por segundo
            size: 4
        };

        const stats = { energy: 100, hunger: 100, max: 100 };
        const inventory = { wood: 0, stone: 0, berry: 0 };
        
        const resources = [];
        const structures = [];
        let gameTime = 0;
        let daysSurvived = 1;
        let clock = new THREE.Clock();

        // === GENERACIÓN PROCEDURAL DE RECURSOS ===
        const resourceGeometries = {
            wood: new THREE.CylinderGeometry(1, 1, 6, 8),
            stone: new THREE.DodecahedronGeometry(2),
            berry: new THREE.BoxGeometry(3, 3, 3) // Arbusto
        };
        const resourceMaterials = {
            wood: new THREE.MeshStandardMaterial({ color: 0x8B5A2B }),
            stone: new THREE.MeshStandardMaterial({ color: 0x808080, roughness: 0.9 }),
            berry: new THREE.MeshStandardMaterial({ color: 0x228B22 }) // Verde para el arbusto
        };

        function spawnResources(count) {
            const types = [
                { type: 'wood', emoji: '🪵', weight: 4 },
                { type: 'stone', emoji: '🪨', weight: 3 },
                { type: 'berry', emoji: '🍒', weight: 2 }
            ];

            for (let i = 0; i < count; i++) {
                let totalWeight = types.reduce((acc, curr) => acc + curr.weight, 0);
                let random = Math.random() * totalWeight;
                let selectedType;
                
                for (let t of types) {
                    if (random < t.weight) { selectedType = t; break; }
                    random -= t.weight;
                }

                // Crear Mesh 3D
                const mesh = new THREE.Mesh(resourceGeometries[selectedType.type], resourceMaterials[selectedType.type]);
                const rx = (Math.random() - 0.5) * (MAP_SIZE - 20);
                const rz = (Math.random() - 0.5) * (MAP_SIZE - 20);
                
                mesh.position.set(rx, 0, rz);
                mesh.castShadow = true;
                mesh.receiveShadow = true;

                if (selectedType.type === 'wood') {
                    mesh.position.y = 1;
                    mesh.rotation.x = Math.PI / 2;
                    mesh.rotation.z = Math.random() * Math.PI;
                } else if (selectedType.type === 'stone') {
                    mesh.position.y = 1.5;
                    mesh.rotation.set(Math.random(), Math.random(), Math.random());
                } else if (selectedType.type === 'berry') {
                    mesh.position.y = 1.5;
                    // Agregar las bayas rojas al arbusto
                    const berrySphGeo = new THREE.SphereGeometry(0.8, 8, 8);
                    const berrySphMat = new THREE.MeshStandardMaterial({ color: 0xff0000 });
                    for(let b = 0; b < 3; b++) {
                        const bMesh = new THREE.Mesh(berrySphGeo, berrySphMat);
                        bMesh.position.set((Math.random()-0.5)*3, 2, (Math.random()-0.5)*3);
                        mesh.add(bMesh);
                    }
                }

                scene.add(mesh);

                resources.push({
                    id: Math.random().toString(36).substr(2, 9),
                    x: rx,
                    z: rz,
                    type: selectedType.type,
                    emoji: selectedType.emoji,
                    size: 4,
                    mesh: mesh
                });
            }
        }

        spawnResources(150);

        // === CONTROLES ===
        window.addEventListener('keydown', (e) => {
            const key = e.key.toLowerCase();
            if (keys.hasOwnProperty(key)) keys[key] = true;
            if (key === 'e') eatBerry();
        });

        window.addEventListener('keyup', (e) => {
            const key = e.key.toLowerCase();
            if (keys.hasOwnProperty(key)) keys[key] = false;
        });

        // === UI & MECÁNICAS ===
        function updateUI() {
            document.getElementById('energy-bar').style.width = `${Math.max(0, stats.energy)}%`;
            document.getElementById('energy-text').innerText = `${Math.floor(stats.energy)}%`;
            document.getElementById('energy-bar').style.backgroundColor = stats.energy < 20 ? 'var(--danger)' : 'var(--accent)';

            document.getElementById('hunger-bar').style.width = `${Math.max(0, stats.hunger)}%`;
            document.getElementById('hunger-text').innerText = `${Math.floor(stats.hunger)}%`;
            document.getElementById('hunger-bar').style.backgroundColor = stats.hunger < 20 ? 'var(--danger)' : 'var(--warning)';

            document.getElementById('inv-wood').innerText = inventory.wood;
            document.getElementById('inv-stone').innerText = inventory.stone;
            document.getElementById('inv-berry').innerText = inventory.berry;

            document.getElementById('btn-craft-fire').disabled = !(inventory.wood >= 5 && inventory.stone >= 2);
            document.getElementById('btn-craft-tent').disabled = !(inventory.wood >= 15);
        }

        function showNotification(text) {
            const area = document.getElementById('notification-area');
            const toast = document.createElement('div');
            toast.className = 'toast';
            toast.innerText = text;
            area.appendChild(toast);
            setTimeout(() => toast.remove(), 2500);
        }

        function eatBerry() {
            if (inventory.berry > 0) {
                if (stats.hunger >= 100 && stats.energy >= 100) { showNotification("Estás lleno."); return; }
                inventory.berry--;
                stats.hunger = Math.min(100, stats.hunger + 15);
                stats.energy = Math.min(100, stats.energy + 10);
                showNotification("Has comido una baya 🍒");
                updateUI();
            } else { showNotification("No tienes bayas 🍒"); }
        }

        document.getElementById('btn-eat').addEventListener('click', eatBerry);

        // --- CRAFTEO 3D ---
        document.getElementById('btn-craft-fire').addEventListener('click', () => {
            if (inventory.wood >= 5 && inventory.stone >= 2) {
                inventory.wood -= 5;
                inventory.stone -= 2;
                
                // Modelo del Fuego 3D
                const fireGroup = new THREE.Group();
                const logs = new THREE.Mesh(new THREE.CylinderGeometry(1.5, 1.5, 4, 6), resourceMaterials.wood);
                logs.rotation.z = Math.PI / 2; logs.position.y = 0.5;
                const logs2 = logs.clone(); logs2.rotation.y = Math.PI / 2;
                
                const flameGeo = new THREE.ConeGeometry(2, 5, 8);
                const flameMat = new THREE.MeshBasicMaterial({ color: 0xff4500, transparent: true, opacity: 0.8 });
                const flame = new THREE.Mesh(flameGeo, flameMat);
                flame.position.y = 3;

                // Luz puntual para la noche
                const fireLight = new THREE.PointLight(0xffaa00, 2, 100);
                fireLight.position.y = 5;
                fireLight.castShadow = true;

                fireGroup.add(logs, logs2, flame, fireLight);
                fireGroup.position.set(playerGroup.position.x, 0, playerGroup.position.z + 5); // Un poco al frente
                scene.add(fireGroup);

                structures.push({ type: 'fire', x: fireGroup.position.x, z: fireGroup.position.z });
                showNotification("Has encendido un Fuego 🔥");
                updateUI();
            }
        });

        document.getElementById('btn-craft-tent').addEventListener('click', () => {
            if (inventory.wood >= 15) {
                inventory.wood -= 15;
                
                // Modelo Tienda de campaña 3D (Prisma)
                const tentGeo = new THREE.CylinderGeometry(5, 5, 12, 3);
                const tentMat = new THREE.MeshStandardMaterial({ color: 0x313244 });
                const tent = new THREE.Mesh(tentGeo, tentMat);
                
                tent.rotation.z = Math.PI / 2;
                tent.rotation.x = Math.PI / 2; // Acostar
                tent.position.set(playerGroup.position.x, 3, playerGroup.position.z - 8);
                tent.castShadow = true;
                
                scene.add(tent);

                structures.push({ type: 'tent', x: tent.position.x, z: tent.position.z });
                showNotification("Has construido una Tienda ⛺");
                updateUI();
            }
        });

        function checkCollisions() {
            for (let i = resources.length - 1; i >= 0; i--) {
                const res = resources[i];
                const dist = Math.hypot(playerGroup.position.x - res.x, playerGroup.position.z - res.z);
                
                if (dist < (playerState.size + res.size)) {
                    inventory[res.type]++;
                    showNotification(`+1 ${res.emoji}`);
                    scene.remove(res.mesh); // Quitar del mundo 3D
                    resources.splice(i, 1);
                    updateUI();
                }
            }
        }

        function getDistanceToNearestFire() {
            let min_dist = Infinity;
            for (const s of structures) {
                if (s.type === 'fire') {
                    const dist = Math.hypot(playerGroup.position.x - s.x, playerGroup.position.z - s.z);
                    if (dist < min_dist) min_dist = dist;
                }
            }
            return min_dist;
        }

        // === BUCLE PRINCIPAL ===
        const colorDay = new THREE.Color(0x87CEEB);
        const colorNight = new THREE.Color(0x050510);
        const fogDay = new THREE.Color(0x87CEEB);
        const fogNight = new THREE.Color(0x050510);

        function animate() {
            requestAnimationFrame(animate);
            
            const deltaTime = clock.getDelta();
            
            // Movimiento
            let dx = 0;
            let dz = 0;
            let currentSpeed = stats.energy > 0 ? playerState.speed : playerState.speed * 0.3;

            if (keys.w || keys.arrowup) dz -= currentSpeed;
            if (keys.s || keys.arrowdown) dz += currentSpeed;
            if (keys.a || keys.arrowleft) dx -= currentSpeed;
            if (keys.d || keys.arrowright) dx += currentSpeed;

            if (dx !== 0 || dz !== 0) {
                if (dx !== 0 && dz !== 0) {
                    const length = Math.sqrt(dx*dx + dz*dz);
                    dx = (dx/length) * currentSpeed;
                    dz = (dz/length) * currentSpeed;
                }

                playerGroup.position.x += dx * deltaTime;
                playerGroup.position.z += dz * deltaTime;

                // Limitar al mapa
                playerGroup.position.x = Math.max(-MAP_SIZE/2 + 5, Math.min(MAP_SIZE/2 - 5, playerGroup.position.x));
                playerGroup.position.z = Math.max(-MAP_SIZE/2 + 5, Math.min(MAP_SIZE/2 - 5, playerGroup.position.z));

                // Rotar jugador hacia donde camina
                playerGroup.rotation.y = Math.atan2(-dx, -dz);

                stats.energy -= (0.5 * deltaTime);
            }

            // Hambre y penalizaciones
            stats.hunger -= (1.5 * deltaTime);
            if (stats.hunger <= 0) stats.energy -= (2 * deltaTime);

            // Día/Noche
            gameTime += deltaTime * 1000;
            const cycleProgress = (gameTime % DAY_DURATION) / DAY_DURATION;
            const isNight = cycleProgress > 0.5;

            // Interpolación de colores para el cielo y la niebla
            let transitionFactor = Math.abs(Math.cos(cycleProgress * Math.PI * 2));
            // Suavizado manual para que la noche sea realmente oscura en la base inferior de la onda
            let darkness = cycleProgress > 0.25 && cycleProgress < 0.75 ? transitionFactor : 1; 

            scene.background.lerpColors(colorNight, colorDay, darkness);
            scene.fog.color.lerpColors(fogNight, fogDay, darkness);
            
            // Luz solar
            ambientLight.intensity = 0.2 + (0.4 * darkness);
            sunLight.intensity = 0.8 * darkness;

            if (isNight) {
                const nightDarkness = Math.sin((cycleProgress - 0.5) * Math.PI) * 0.95; 
                const distToFire = getDistanceToNearestFire();
                if (distToFire > 40) { // Radio 3D del fuego
                    stats.energy -= (3 * deltaTime * nightDarkness);
                }
            }

            stats.energy = Math.max(0, stats.energy);
            stats.hunger = Math.max(0, stats.hunger);

            // Indicador UI
            let timeText = ""; let timeIcon = "";
            if (cycleProgress < 0.25) { timeText = "Mañana"; timeIcon = "🌅"; }
            else if (cycleProgress < 0.5) { timeText = "Tarde"; timeIcon = "☀️"; }
            else if (cycleProgress < 0.75) { timeText = "Anochecer"; timeIcon = "🌆"; }
            else { timeText = "Noche"; timeIcon = "🌙"; }
            
            daysSurvived = Math.floor(gameTime / DAY_DURATION) + 1;
            document.getElementById('time-indicator').innerHTML = `Día ${daysSurvived} - ${timeText} ${timeIcon}`;

            // Respawn
            if (Math.random() < 0.01 && resources.length < 200) {
                spawnResources(1);
            }

            checkCollisions();
            if(Math.random() < 0.1) updateUI(); // Actualizar UI sin saturar 60fps

            // Animación de cámara (Sigue al jugador isométricamente)
            const camOffsetX = 0;
            const camOffsetY = 60;
            const camOffsetZ = 50;
            
            camera.position.lerp({
                x: playerGroup.position.x + camOffsetX,
                y: playerGroup.position.y + camOffsetY,
                z: playerGroup.position.z + camOffsetZ
            }, 0.1);
            camera.lookAt(playerGroup.position);

            renderer.render(scene, camera);
        }

        // Iniciar
        updateUI();
        animate();

    </script>
</body>
</html>