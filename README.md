# RevisaoDeTermos

# Semáforo Inteligente com IoT

## Objetivo
Este projeto tem como objetivo desenvolver um semáforo inteligente utilizando conceitos de Internet das Coisas (IoT), capaz de se adaptar ao fluxo de veículos e a condições especiais como chuva e falha de sensores. O sistema busca melhorar o controle do trânsito em um cruzamento urbano de forma automatizada.

---

## Arquitetura
O sistema é baseado em sensores instalados no cruzamento que enviam dados para um controlador IoT. Esse controlador processa as informações e envia os dados para um servidor local, responsável pelo monitoramento e apoio à tomada de decisão.

Componentes principais:
- Sensores de fluxo de veículos
- Sensor de chuva
- Sensor de luminosidade
- Controlador IoT 
- Servidor local
- Rede IoT com protocolo MQTT

### Requisitos
Requisitos Funcionais
 RF01. Detectar o fluxo de veículos em cada via
 RF02. Ajustar automaticamente o tempo do sinal verde
 RF03. Detectar presença de pedestres
 RF04. Controlar sinal sonoro para pedestres
 RF05. Identificar condições climáticas adversas
 RF06. Priorizar veículos de emergência
 RF07. Entrar em modo seguro em caso de falha
 RF08. Enviar dados em tempo real para a central
 RF09. Permitir configuração manual por operador autorizado

Requisitos Não Funcionais
 RNF01. Tempo de resposta inferior a 2 segundos
 RNF02. Disponibilidade mínima de 99%
 RNF03. Sistema deve ser escalável para múltiplos cruzamentos
 RNF04. Comunicação de dados criptografada
 RNF05. Interface da central deve ser intuitiva
 RNF06. Sistema deve operar sob temperaturas de -10°C a 50°C

### Historia do usuario
HU01
 Como motorista,
 quero que o semáforo ajuste o tempo de verde conforme o trânsito,
 para reduzir congestionamentos.
 
HU02
 Como pedestre,
 quero tempo suficiente para atravessar com segurança,
 mesmo em dias de chuva.

HU03
 Como operador da central,
 quero ser notificado quando um sensor falhar,
 para agir rapidamente.

### Codigo

import tkinter as tk
import random


'CONFIGURAÇÕES'

TEMPO_VERDE_PADRAO = 3000
TEMPO_VERDE_ESTENDIDO = 6000
TEMPO_AMARELO_PADRAO = 1500
TEMPO_AMARELO_CHUVA = 3000
FLUXO_ALTO_LIMITE = 20


'SIMULAÇÃO DOS SENSORES'


def ler_fluxo():
    return random.randint(0, 30)

def ler_chuva():
    return random.choice(["nenhuma", "fraca", "forte"])

def sensor_funcionando():
    return random.choice([True, True, True, False])

def servidor_disponivel():
    return random.choice([True, True, False])
