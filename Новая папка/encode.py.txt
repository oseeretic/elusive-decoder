import base64

# Укажите точное имя вашей картинки с логотипом (например, 'bg.png')
image_name = 'bg.png' 

try:
    with open(image_name, "rb") as image_file:
        encoded_string = base64.b64encode(image_file.read()).decode('utf-8')
        
    # Сохраняем текстовый код картинки в файл, чтобы вы могли его скопировать
    with open("base64_code.txt", "w") as text_file:
        text_file.write(f"data:image/png;base64,{encoded_string}")
        
    print("Успешно! Текстовый код картинки сохранен в файл base64_code.txt")
except FileNotFoundError:
    print(f"Ошибка: Файл '{image_name}' не найден в этой папке. Проверьте имя файла.")
