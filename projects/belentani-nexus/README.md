# BELENTANI NEXUS - Plataforma All-in-One AI

## 🎯 Visión

Plataforma unificada estilo Cabina.AI/HappyTime con estética cyberpunk bélica Belentani. Integra 50+ modelos de IA (especialmente China) con sistema de créditos transparente.

## 📁 Estructura del Proyecto

```
belentani-nexus/
├── ARCHITECTURE.md          # Arquitectura completa con 35+ APIs
├── index.html               # MVP frontend (chat multi-modelo)
├── ZAI_PROMPTS.md           # 10 prompts para Z.AI (generar herramientas)
├── PROMPT_TRIAGE.md         # Auditoría rápida de repos (solo lectura)
├── PROMPT_DEEP.md           # Auditoría profunda (corrección automática)
├── driver.ps1               # Driver PowerShell para auditoría masiva
└── README.md                # Este archivo
```

## 🚀 Quick Start

### 1. Frontend MVP

Abrir `index.html` en el navegador. El MVP incluye:
- Chat con Qwen 3.8 Max (requiere API key en el código)
- Selector de modelos (texto, imagen, video, audio)
- Sistema de créditos (localStorage)
- Estética cyberpunk con starfield Three.js

**Configurar API keys:**
```javascript
// En index.html, línea ~600
const API_CONFIG = {
    'qwen3.8-max': {
        endpoint: 'https://dashscope-intl.aliyuncs.com/compatible-mode/v1/chat/completions',
        apiKey: '***', // <-- TU API KEY AQUÍ
        model: 'qwen3.8-max'
    }
}
```

### 2. Generar Herramientas con Z.AI

Usar los prompts en `ZAI_PROMPTS.md` para generar herramientas fullstack:

1. Ir a https://z.ai
2. Copiar uno de los 10 prompts
3. Z.AI genera la app fullstack gratis con sandbox
4. Deploy a Vercel/Netlify

**Prompts prioritarios:**
1. Repo Auditor Dashboard - Auditoría automática
2. Secret Scanner - Detecta API keys expuestas
3. README Generator - Genera READMEs profesionales

### 3. Auditoría Masiva de Repos

Ejecutar auditoría de los ~200 repos de GitHub:

```powershell
# Instalar Qwen Code si no lo tienes
npm install -g @qwen-code/cli

# Configurar API key
$env:QWEN_API_KEY = "***"

# Ejecutar en modo prueba (3 repos)
.\driver.ps1 -GITHUB_USER belentani7 -MAX_REPOS 3 -DRY_RUN

# Ejecutar auditoría completa
.\driver.ps1 -GITHUB_USER belentani7

# Solo fase triage (rápido)
.\driver.ps1 -GITHUB_USER belentani7 -SKIP_DEEP

# Solo fase deep (corrección)
.\driver.ps1 -GITHUB_USER belentani7 -SKIP_TRIAGE
```

**Salida:**
- `informes/*.md` - Informe por repo
- `st/*.verdict` - Veredicto (OK/WARN/CRIT)
- `st/*.changes` - Cambios realizados
- `RESUMEN.md` - Resumen final
- `logs/*.log` - Logs detallados

## 🎨 APIs Integradas

### China (Prioridad Máxima)

**Texto/Code:**
- Qwen (Alibaba) - qwen3.8-max, qwen3.8-flash ✅ Token Plan Pro
- DeepSeek - deepseek-v3, deepseek-r1
- GLM (Zhipu AI) - glm-4, glm-4v
- Kimi (Moonshot AI) - moonshot-v1-128k
- MiniMax - abab6.5-chat
- Baichuan - Baichuan2-Turbo

**Imagen:**
- Qwen-Image (Alibaba) - qwen-image-3.0 ✅ Free quota
- Kolors (Kuaishou) - kolors
- ERNIE-ViL (Baidu) - ernie-vilg-v2

**Video:**
- Wan (Alibaba) - wanx-v1 ✅ Free quota
- CogVideoX (Zhipu) - cogvideox
- Tencent Hunyuan - hunyuan-video

**Audio:**
- CosyVoice (Alibaba) - cosyvoice-v1 ✅ Free quota
- Fish Speech - fish-speech-1.5
- Volcano TTS (ByteDance) - volcano-tts

### Occidente (Free Tiers)

**Texto:**
- Groq - llama-3.3-70b, mixtral-8x7b
- OpenRouter - 50+ modelos
- Cerebras - llama-3.1-70b

**Imagen:**
- Stable Diffusion - sd3.5-large
- Flux - flux-pro, flux-schnell
- Ideogram - ideogram-2.0
- Pollinations - flux ✅ GRATIS ILIMITADO

**Video:**
- Luma Dream Machine - dream-machine
- Hailuo (MiniMax) - hailuo-video
- PixVerse - pixverse-v2

**Audio:**
- ElevenLabs - eleven_multilingual_v2
- Google Cloud TTS - waveNet
- OpenAI TTS - tts-1-hd

## 💰 Sistema de Créditos

- **1 crédito = 1 imagen OR 1 video corto (5s) OR 1000 tokens de texto**
- Registro gratuito: 100 créditos
- Daily login: +5 créditos
- Referidos: +20 créditos por usuario

**Precios:**
- Pack 100 créditos: $5
- Pack 500 créditos: $20
- Pack 2000 créditos: $70
- Suscripción mensual (1000 créditos): $30/mes

## 🎯 Roadmap

### Fase 1: MVP (✅ Completado)
- [x] Frontend básico con chat multi-modelo
- [x] Integración de Qwen (Token Plan)
- [x] Sistema de créditos básico
- [x] Estética cyberpunk bélica

### Fase 2: Imágenes y Videos (En progreso)
- [ ] Integración de 10 APIs de imágenes
- [ ] Integración de 5 APIs de videos
- [ ] Galería de generaciones
- [ ] Comparación lado a lado

### Fase 3: Herramientas Z.AI (Pendiente)
- [ ] Repo Auditor Dashboard
- [ ] Secret Scanner Visual
- [ ] README Generator
- [ ] Dependency Updater

### Fase 4: Auditoría Masiva (Pendiente)
- [ ] Ejecutar driver.ps1 en 200 repos
- [ ] Revisar informes generados
- [ ] Merge de PRs automáticos
- [ ] Rotar secrets expuestos

### Fase 5: Backend (Futuro)
- [ ] Node.js + Express para proxy
- [ ] SQLite para gestión de créditos
- [ ] Autenticación de usuarios
- [ ] API pública

## 🔧 Configuración Avanzada

### Variables de Entorno

```bash
# APIs de IA
export QWEN_API_KEY = "***"
export DEEPSEEK_API_KEY = "***"
export GROQ_API_KEY = "***"
export OPENROUTER_API_KEY = "***"

# GitHub
export GITHUB_TOKEN = "***"

# Base de datos (futuro)
export DATABASE_URL = "postgresql://..."
```

### Docker (Futuro)

```yaml
version: '3.8'
services:
  frontend:
    build: ./frontend
    ports:
      - "3000:3000"
    environment:
      - VITE_API_URL=http://backend:4000
  
  backend:
    build: ./backend
    ports:
      - "4000:4000"
    environment:
      - QWEN_API_KEY=${QWEN_API_KEY}
      - DATABASE_URL=${DATABASE_URL}
  
  db:
    image: postgres:15
    environment:
      - POSTGRES_DB=belentani_nexus
      - POSTGRES_USER=admin
      - POSTGRES_PASSWORD=${DB_PASSWORD}
    volumes:
      - pgdata:/var/lib/postgresql/data

volumes:
  pgdata:
```

## 📊 Métricas de Éxito

### Técnicos
- Latencia < 2s para texto
- Latencia < 10s para imágenes
- Uptime > 99%
- Soporte para 50+ modelos

### Negocio
- 1000 usuarios en 3 meses
- 10% conversión a pago
- $5000 MRR en 6 meses
- 4.5+ rating en Product Hunt

## 🎓 Aprendizajes

### Sobre Tokens y Contexto
- Contexto grande = más tokens de input = más costo
- Solución: usar modelos con contexto pequeño para tareas simples
- qwen3.6-flash (32K) para tareas básicas
- qwen3.8-max (1M) solo cuando sea necesario

### Sobre Auditoría de Repos
- Dos pasadas: triage (rápido) + deep (solo críticos)
- Sesión fresca por repo para evitar contaminación de contexto
- Prompt caching máximo con prefijo estático
- Timeout por repo para evitar bloqueos

## 🤝 Contribuir

1. Fork el repositorio
2. Crear rama: `git checkout -b feature/nueva-feature`
3. Commit: `git commit -m 'Add nueva feature'`
4. Push: `git push origin feature/nueva-feature`
5. Pull Request

## 📄 Licencia

MIT License - Ver [LICENSE](LICENSE) para detalles

## 📞 Contacto

- **GitHub**: https://github.com/belentani7
- **Email**: belentani7pedro@gmail.com
- **Web**: https://belentani7.github.io/belentani_Omega/

---

**BELENTANI NEXUS** - All-in-One AI Platform  
_Cyberpunk Bélico Estética · 50+ Modelos · Sistema de Créditos Transparente_
