# IFRN-cnat
Aula sobre git     
import pygame

pygame.init()
screen = pygame.display.set_mode((640, 480))
screen.fill((255, 255, 255))
clock = pygame.time.Clock()
running = True
font = pygame.font.Font(None, 24)

x = 0
while running:
  for event in pygame.event.get():
    if event.type == pygame.QUIT:
      running = False
  
  screen.fill((255, 255, 255)) # apaga o quadro atual

  # Lógica de jogo e renderização do novo quadro
  figura = pygame.Surface([30, 30]) # cria uma superfície quadrada com 30 pixels de lado
  figura.fill((0, 0, 0)) # preenche a superfície com cor preta
  surface_texto = font.render(f"Olá Mundo!", True, 'black')
  screen.blit(figura, (x, 200)) # desenha figura sobre o quadro atual nas coordenadas indicadas
  screen.blit(surface_texto,(50, 50))
  if x < 640 - 30:
    x = x + 3 # avança 3 pixels a cada quadro

  if x >= 610:
    x = x - 3  



  pygame.display.flip() # Desenha o quadro atual na tela
  clock.tick(60)

pygame.quit()

