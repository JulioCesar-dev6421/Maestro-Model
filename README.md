# 🎙️ Maestro Wake Word - Modelo TFLite Personalizado

## 📜 Visão Geral

Este repositório contém o modelo **TensorFlow Lite (TFLite)** para a palavra de despertar personalizada **"maestro"**. Este modelo foi treinado usando a estrutura **microWakeWord** e é otimizado para a detecção de palavra-chave (KWS) em tempo real em microcontroladores de baixo consumo de energia, como o **ESP32-S3**.

## 🚀 Como Usar no ESPHome

Para implantar a *wake word* "maestro" em um dispositivo ESPHome (muito comum em integrações com o Home Assistant), você precisará do arquivo de manifesto JSON e do modelo TFLite.

### 1. 📂 Estrutura de Arquivos

Os arquivos de modelo e manifesto estão localizados no diretório `/models/`:

| Arquivo | Descrição |
| :--- | :--- |
| `maestro_model.tflite` | O modelo binário (pesos e arquitetura) em formato TFLite. |
| `maestro_manifest.json` | O arquivo de configuração que informa ao microWakeWord os parâmetros do modelo. |

### 2. ⚙️ Configuração no ESPHome YAML

O ESPHome usa o link **RAW** do arquivo de manifesto JSON para configurar e baixar o modelo no dispositivo.

1.  **Obtenha o Link RAW** do arquivo `models/maestro_manifest.json` no seu GitHub.
2.  Adicione a configuração abaixo ao seu arquivo `esphome.yaml`:

```yaml
# Exemplo de configuração no esphome.yaml
micro_wake_word:
  id: my_wake_word_component
  models:
    # Configuração da sua wake word personalizada 'maestro'
    - wake_word: "maestro"
      # URL deve ser o link RAW do GitHub!
      url: "[https://raw.githubusercontent.com/SEU_USUARIO/SEU_REPOSITORIO/main/models/maestro_manifest.json](https://raw.githubusercontent.com/SEU_USUARIO/SEU_REPOSITORIO/main/models/maestro_manifest.json)"