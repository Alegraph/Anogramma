# Anogramma
import random

WORDS = ['бутафория', 'вандализм', 'ирригатор', 'литаврист', 'ощериться', 'тюбетейка', 'целлулоид', 'циферблат',
         'экзекутор',
         'языкастый']

word = random.choice(WORDS)
correct = word
jumble = ''

while word:
    position = random.randrange(len(word))
    jumble += word[position]
    word = word[:position] + word[position + 1:]

print(''' 

                         Добро пожаловать в игру: АНОГРАММА
                Требуестя переставить буквы так, чтобы получилось осмысленное слово.
                (Для выхода нажмите Enter, не вводя слова)
''')
print('Вот анограмма: ',jumble)

guess = input('\nПопробуйте отгадать слово: ')
while guess != correct and guess != "":
    print('К сожалению вы не правы')
    guess = input('Ваша версия слова: ')
    
if guess == correct:
    print('Да именно так, Вы отгадали.\n')

print('Thanks for playing.')
