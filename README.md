<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Meu Site</title>
</head>
<body>
    <h1>Olá, mundo!</h1>
    <p>Esse é meu site no GitHub Pages, gostaria de passar mais informações sobre esse trabalho .</p>
</body>
</html>
from PIL import Image, ImageDraw
import random

def generate_image(width=512, height=512, output_file="generated_image.png"):
    """Gera uma imagem abstrata com cores e formas aleatórias."""
    image = Image.new("RGB", (width, height), "white")
    draw = ImageDraw.Draw(image)

    # Criar formas aleatórias
    for _ in range(50):  # Número de formas
        x1, y1 = random.randint(0, width), random.randint(0, height)
        x2, y2 = random.randint(0, width), random.randint(0, height)
        color = (random.randint(0, 255), random.randint(0, 255), random.randint(0, 255))
        draw.ellipse([x1, y1, x2, y2], fill=color, outline=color)

    image.save(output_file)
    print(f"Imagem gerada e salva como {output_file}")

if __name__ == "__main__":
    generate_image()