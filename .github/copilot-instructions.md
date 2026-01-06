# Numero Secreto - AI Coding Guidelines

## Project Overview
This is a vanilla JavaScript number guessing game with Portuguese text and text-to-speech functionality. The game generates random numbers between 1-100, provides hints, and tracks attempts.

## Architecture
- **index.html**: Main HTML structure with input field, buttons, and responsive layout
- **app.js**: Game logic with global state variables and DOM manipulation functions
- **style.css**: Responsive styling with gradient backgrounds and mobile breakpoints

## Key Patterns

### Text Display and Speech
Always use `exibirTextoNaTela(tag, texto)` for updating text content - it automatically speaks the text in Brazilian Portuguese:

```javascript
exibirTextoNaTela('h1', 'Acertou!');
exibirTextoNaTela('p', 'O número secreto é menor');
```

### Game State Management
Use global variables for game state:
- `numeroSecreto`: Current secret number
- `tentativas`: Attempt counter
- `listaDeNumerosSorteados`: Array tracking used numbers

### Number Generation
`gerarNumeroAleatorio()` ensures unique numbers by tracking used values and resetting when all numbers are exhausted.

### Portuguese Conventions
- All user-facing text is in Portuguese
- Function names use Portuguese: `verificarChute()`, `reiniciarJogo()`, `limparCampo()`
- Variable names mix Portuguese and English: `numeroSecreto`, `listaDeNumerosSorteados`

## Development Workflow
- No build process required - open `index.html` directly in browser
- Test speech functionality requires internet connection for responsivevoice.js
- Game runs entirely client-side with no server dependencies

## Integration Points
- **responsivevoice.js**: External script for text-to-speech (Brazilian Portuguese Female voice)
- Uses Google Fonts: Chakra Petch (headings) and Inter (body text)

## Common Tasks
- Add new game features: Extend `verificarChute()` logic and update UI in `index.html`
- Modify speech: Adjust voice parameters in `exibirTextoNaTela()` calls
- Change range: Update `numeroLimite` and HTML input `max` attribute
- Add responsiveness: Modify CSS media queries for new breakpoints