
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Corazón en Movimiento</title>
    <link rel="stylesheet" href="styles.css">
    <style>
    body {
        display: flex;
        justify-content: center;
        align-items: center;
        height: 100vh;
        margin: 0;
        background-color: #f0f0f0;
    }
    
    .container {
        position: relative;
        width: 100%;
        height: 100%;
    }
    
    .heart {
        position: absolute;
        top: 50%;
        left: 50%;
        width: 100px;
        height: 100px;
        background-color: red;
        transform: translate(-50%, -50%) rotate(-45deg);
        animation: move 4s linear infinite;
        transition: transform 0.5s ease;
    }
    
    .heart::before,
    .heart::after {
        content: '';
        position: absolute;
        width: 100px;
        height: 100px;
        background-color: red;
        border-radius: 50%;
    }
    
    .heart::before {
        top: -50px;
        left: 0;
    }
    
    .heart::after {
        left: 50px;
        top: 0;
    }
    
    @keyframes move {
        0% {
            transform: translate(-50%, -50%) rotate(-45deg) translateX(0);
        }
        50% {
            transform: translate(-50%, -50%) rotate(-45deg) translateX(200px);
        }
        100% {
            transform: translate(-50%, -50%) rotate(-45deg) translateX(0);
        }
    }

    .message {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        font-size: 24px;
        color: red;
        display: none; /* Oculto por defecto */
    }
</style>
</head>
<body>
    <div class="container">
        <div class="heart" id="heart"></div>
        <div class="message" id="message">Te quiero mucho</div>
    </div>
    <script src="script.js"></script>
    <script>
    const heart = document.getElementById('heart');
const message = document.getElementById('message');

// Función para abrir el corazón y mostrar el mensaje
function openHeart() {
    heart.style.transform = 'translate(-50%, -50%) rotate(-45deg) scale(1.5)';
    message.style.display = 'block'; // Mostrar el mensaje
}

// Llamar a la función después de 4 segundos
setTimeout(openHeart, 4000); // Cambia el tiempo si es necesario
</script>
</body>
</html>
