# -
🧠 ИИ, различающий загрязнёа, оснонную и чистую окружающую среду Что это такое? Это системванная на искусственном интеллекте, которая с помощью камер, датчиков и анализа данных определяет, загрязнена ли окружающая среда или нет.  🔍 Как он работает: Сбор данных: ИИ получает информацию с камер, дронов, спутников. 
class EnvironmentAI:
    def __init__(self):
        self.thresholds = {
            'air_quality': 50,     # чем меньше, тем чище (например, индекс PM2.5)
            'water_clarity': 70,   # чем больше, тем чище
            'ground_cleanliness': 80  # чем больше, тем чище
        }

    def analyze(self, data):
        air = data.get('air_quality')
        water = data.get('water_clarity')
        ground = data.get('ground_cleanliness')

        result = {}

        result['air'] = 'Чистый' if air <= self.thresholds['air_quality'] else 'Загрязнённый'
        result['water'] = 'Чистая' if water >= self.thresholds['water_clarity'] else 'Загрязнённая'
        result['ground'] = 'Чистая' if ground >= self.thresholds['ground_cleanliness'] else 'Загрязнённая'

        return result

env_data = {
    'air_quality': 72,        # индекс загрязнения воздуха
    'water_clarity': 40,      # прозрачность воды
    'ground_cleanliness': 85  # чистота почвы
}

ai = EnvironmentAI()
analysis = ai.analyze(env_data)

print("Результаты анализа окружающей среды:")
for key, value in analysis.items():
    print(f"{key.capitalize()}: {value}")
    Результаты анализа окружающей среды:
Air: Загрязнённый
Water: Загрязнённая
Ground: Чистая
