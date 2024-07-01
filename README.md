# Calculator-
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Smart AI Calculator</title>
<link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;700&display=swap" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
<div id="calculator-app">
<header>
<nav>
<button id="menu-toggle"><i class="fas fa-bars"></i></button>
<h1>Smart AI Calculator</h1>
<button id="ai-toggle"><i class="fas fa-robot"></i></button>
</nav>
</header>
<main>
<div id="calculator-container">
<div id="display-container">
<div id="history-display"></div>
<div id="input-display"></div>
<div id="result-display"></div>
</div>
<div id="keypad-container">
<div id="main-keypad">
<div class="keypad-row">
<button class="function-btn" data-action="clear">AC</button>
<button class="function-btn" data-action="backspace"><i class="fas fa-backspace"></i></button>
<button class="function-btn" data-action="percentage">%</button>
<button class="operator-btn" data-action="divide">&divide;</button>
</div>
<div class="keypad-row">
<button class="number-btn" data-value="7">7</button>
<button class="number-btn" data-value="8">8</button>
<button class="number-btn" data-value="9">9</button>
<button class="operator-btn" data-action="multiply">&times;</button>
</div>
<div class="keypad-row">
<button class="number-btn" data-value="4">4</button>
<button class="number-btn" data-value="5">5</button>
<button class="number-btn" data-value="6">6</button>
<button class="operator-btn" data-action="subtract">-</button>
</div>
<div class="keypad-row">
<button class="number-btn" data-value="1">1</button>
<button class="number-btn" data-value="2">2</button>
<button class="number-btn" data-value="3">3</button>
<button class="operator-btn" data-action="add">+</button>
</div>
<div class="keypad-row">
<button class="number-btn" data-value="0">0</button>
<button class="number-btn" data-value=".">.</button>
<button class="function-btn" data-action="toggle-sign">&plusmn;</button>
<button class="function-btn" data-action="equals">=</button>
</div>
</div>
<div id="advanced-keypad">
<div class="keypad-row">
<button class="advanced-btn" data-action="sin">sin</button>
<button class="advanced-btn" data-action="cos">cos</button>
<button class="advanced-btn" data-action="tan">tan</button>
<button class="advanced-btn" data-action="log">log</button>
</div>
<div class="keypad-row">
<button class="advanced-btn" data-action="sqrt">&radic;</button>
<button class="advanced-btn" data-action="power">x<sup>y</sup></button>
<button class="advanced-btn" data-action="factorial">x!</button>
<button class="advanced-btn" data-action="pi">&pi;</button>
</div>
<div class="keypad-row">
<button class="advanced-btn" data-action="e">e</button>
<button class="advanced-btn" data-action="ln">ln</button>
<button class="advanced-btn" data-action="abs">|x|</button>
<button class="advanced-btn" data-action="rand">RAND</button>
</div>
<div class="keypad-row">
<button class="advanced-btn" data-action="exp">EXP</button>
<button class="advanced-btn" data-action="mod">MOD</button>
<button class="advanced-btn" data-action="inverse">1/x</button>
<button class="advanced-btn" data-action="cube">x³</button>
</div>
</div>
</div>
<div id="function-switcher">
<button class="switcher-btn active" data-panel="main-keypad">Basic</button>
<button class="switcher-btn" data-panel="advanced-keypad">Advanced</button>
<button class="switcher-btn" data-panel="programmer-panel">Programmer</button>
<button class="switcher-btn" data-panel="graphing-panel">Graphing</button>
</div>
</div>
<div id="side-panels">
<div id="ai-panel" class="side-panel">
<h3>AI Assistant</h3>
<textarea id="ai-input" placeholder="Ask about math, formulas, or complex calculations..."></textarea>
<button id="ai-submit">Ask AI</button>
<div id="ai-response"></div>
</div>
<div id="history-panel" class="side-panel">
<h3>History</h3>
<ul id="history-list"></ul>
<button id="clear-history">Clear History</button>
</div>
<div id="memory-panel" class="side-panel">
<h3>Memory</h3>
<div id="memory-buttons">
<button class="memory-btn" data-action="mc">MC</button>
<button class="memory-btn" data-action="mr">MR</button>
<button class="memory-btn" data-action="m-plus">M+</button>
<button class="memory-btn" data-action="m-minus">M-</button>
<button class="memory-btn" data-action="ms">MS</button>
</div>
<ul id="memory-list"></ul>
</div>
</div>
</main>
<div id="additional-features">
<div id="unit-converter" class="feature-panel">
<h3>Unit Converter</h3>
<select id="conversion-type">
<option value="length">Length</option>
<option value="weight">Weight</option>
<option value="temperature">Temperature</option>
<option value="time">Time</option>
<option value="speed">Speed</option>
</select>
<div id="converter-inputs">
<input type="number" id="from-value">
<select id="from-unit"></select>
<input type="number" id="to-value" readonly>
<select id="to-unit"></select>
</div>
<button id="convert-btn">Convert</button>
</div>
<div id="formula-sheet" class="feature-panel">
<h3>Formula Sheet</h3>
<div id="formula-categories">
<button class="category-btn active" data-category="algebra">Algebra</button>
<button class="category-btn" data-category="geometry">Geometry</button>
<button class="category-btn" data-category="trigonometry">Trigonometry</button>
<button class="category-btn" data-category="calculus">Calculus</button>
</div>
<div id="formula-list"></div>
</div>
<div id="graphing-panel" class="feature-panel">
<canvas id="graph-canvas"></canvas>
<input type="text" id="equation-input" placeholder="Enter equation (e.g., y = x^2)">
<button id="plot-graph">Plot</button>
</div>
<div id="programmer-panel" class="feature-panel">
<div id="base-switcher">
<button class="base-btn active" data-base="2">BIN</button>
<button class="base-btn" data-base="8">OCT</button>
<button class="base-btn" data-base="10">DEC</button>
<button class="base-btn" data-base="16">HEX</button>
</div>
<div id="bit-operations">
<button class="bit-op-btn" data-action="and">AND</button>
<button class="bit-op-btn" data-action="or">OR</button>
<button class="bit-op-btn" data-action="xor">XOR</button>
<button class="bit-op-btn" data-action="not">NOT</button>
<button class="bit-op-btn" data-action="nand">NAND</button>
<button class="bit-op-btn" data-action="nor">NOR</button>
</div>
</div>
</div>
</div>
<footer>
<p>&copy; 2024 Smart AI Calculator. All rights reserved.</p>
</footer>
</body>
</html>>
<script>
document.addEventListener('DOMContentLoaded', function() {
const calculatorApp = {
init: function() {
this.cacheDOM();
this.bindEvents();
this.initializeCalculator();
},

cacheDOM: function() {
this.displayContainer = document.getElementById('display-container');
this.historyDisplay = document.getElementById('history-display');
this.inputDisplay = document.getElementById('input-display');
this.resultDisplay = document.getElementById('result-display');
this.keypadContainer = document.getElementById('keypad-container');
this.mainKeypad = document.getElementById('main-keypad');
this.advancedKeypad = document.getElementById('advanced-keypad');
this.functionSwitcher = document.getElementById('function-switcher');
this.aiPanel = document.getElementById('ai-panel');
this.aiInput = document.getElementById('ai-input');
this.aiSubmit = document.getElementById('ai-submit');
this.aiResponse = document.getElementById('ai-response');
this.historyPanel = document.getElementById('history-panel');
this.historyList = document.getElementById('history-list');
this.clearHistoryBtn = document.getElementById('clear-history');
this.memoryPanel = document.getElementById('memory-panel');
this.memoryList = document.getElementById('memory-list');
this.unitConverter = document.getElementById('unit-converter');
this.conversionType = document.getElementById('conversion-type');
this.fromValue = document.getElementById('from-value');
this.fromUnit = document.getElementById('from-unit');
this.toValue = document.getElementById('to-value');
this.toUnit = document.getElementById('to-unit');
this.convertBtn = document.getElementById('convert-btn');
this.formulaSheet = document.getElementById('formula-sheet');
this.formulaCategories = document.getElementById('formula-categories');
this.formulaList = document.getElementById('formula-list');
this.graphingPanel = document.getElementById('graphing-panel');
this.graphCanvas = document.getElementById('graph-canvas');
this.equationInput = document.getElementById('equation-input');
this.plotGraphBtn = document.getElementById('plot-graph');
this.programmerPanel = document.getElementById('programmer-panel');
this.baseSwitcher = document.getElementById('base-switcher');
this.bitOperations = document.getElementById('bit-operations');
},

bindEvents: function() {
this.keypadContainer.addEventListener('click', this.handleKeypadClick.bind(this));
this.functionSwitcher.addEventListener('click', this.handleFunctionSwitch.bind(this));
this.aiSubmit.addEventListener('click', this.handleAISubmit.bind(this));
this.clearHistoryBtn.addEventListener('click', this.clearHistory.bind(this));
this.memoryPanel.addEventListener('click', this.handleMemoryAction.bind(this));
this.convertBtn.addEventListener('click', this.performUnitConversion.bind(this));
this.formulaCategories.addEventListener('click', this.switchFormulaCategory.bind(this));
this.plotGraphBtn.addEventListener('click', this.plotGraph.bind(this));
this.baseSwitcher.addEventListener('click', this.switchBase.bind(this));
this.bitOperations.addEventListener('click', this.performBitOperation.bind(this));
},

initializeCalculator: function() {
this.currentInput = '';
this.currentResult = '';
this.memory = 0;
this.history = [];
this.currentBase = 10;
this.loadUnitOptions();
this.loadFormulas('algebra');
this.setupGraphCanvas();
},

handleKeypadClick: function(event) {
const target = event.target;
if (target.classList.contains('number-btn')) {
this.appendNumber(target.dataset.value);
} else if (target.classList.contains('operator-btn')) {
this.handleOperator(target.dataset.action);
} else if (target.classList.contains('function-btn')) {
this.handleFunction(target.dataset.action);
} else if (target.classList.contains('advanced-btn')) {
this.handleAdvancedFunction(target.dataset.action);
}
this.updateDisplay();
},

appendNumber: function(number) {
this.currentInput += number;
},

handleOperator: function(operator) {
if (this.currentInput !== '') {
this.currentInput += ' ' + operator + ' ';
}
},

handleFunction: function(action) {
switch (action) {
case 'clear':
this.clearCalculator();
break;
case 'backspace':
this.backspace();
break;
case 'percentage':
this.calculatePercentage();
break;
case 'equals':
this.calculate();
break;
case 'toggle-sign':
this.toggleSign();
break;
}
},

handleAdvancedFunction: function(action) {
switch (action) {
case 'sin':
case 'cos':
case 'tan':
case 'log':
case 'sqrt':
case 'factorial':
this.applyMathFunction(action);
break;
case 'power':
this.currentInput += ' ^ ';
break;
case 'pi':
this.currentInput += Math.PI;
break;
case 'e':
this.currentInput += Math.E;
break;
case 'ln':
this.applyMathFunction('log');
break;
case 'abs':
this.applyMathFunction('abs');
break;
case 'rand':
this.currentInput += Math.random();
break;
case 'exp':
this.currentInput += ' * 10^';
break;
case 'mod':
this.currentInput += ' % ';
break;
case 'inverse':
this.calculateInverse();
break;
case 'cube':
this.currentInput += '^3';
break;
}
this.updateDisplay();
},

applyMathFunction: function(func) {
if (this.currentInput !== '') {
const value = parseFloat(this.currentInput);
let result;
switch (func) {
case 'sin':
result = Math.sin(value);
break;
case 'cos':
result = Math.cos(value);
break;
case 'tan':
result = Math.tan(value);
break;
case 'log':
result = Math.log10(value);
break;
case 'sqrt':
result = Math.sqrt(value);
break;
case 'factorial':
result = this.factorial(value);
break;
case 'abs':
result = Math.abs(value);
break;
}
this.currentInput = result.toString();
}
},

factorial: function(n) {
if (n === 0 || n === 1) return 1;
for (let i = n - 1; i >= 1; i--) {
n *= i;
}
return n;
},

calculateInverse: function() {
if (this.currentInput !== '') {
const value = parseFloat(this.currentInput);
if (value !== 0) {
this.currentInput = (1 / value).toString();
} else {
this.currentInput = 'Error';
}
}
},

clearCalculator: function() {
this.currentInput = '';
this.currentResult = '';
},

backspace: function() {
this.currentInput = this.currentInput.slice(0, -1);
},

calculatePercentage: function() {
if (this.currentInput !== '') {
const value = parseFloat(this.currentInput);
this.currentInput = (value / 100).toString();
}
},

toggleSign: function() {
if (this.currentInput !== '') {
if (this.currentInput.charAt(0) === '-') {
this.currentInput = this.currentInput.slice(1);
} else {
this.currentInput = '-' + this.currentInput;
}
}
},

calculate: function() {
try {
this.currentResult = eval(this.currentInput).toString();
this.addToHistory(this.currentInput, this.currentResult);
this.currentInput = this.currentResult;
} catch (error) {
this.currentResult = 'Error';
}
},

updateDisplay: function() {
this.inputDisplay.textContent = this.currentInput;
this.resultDisplay.textContent = this.currentResult;
},

addToHistory: function(input, result) {
this.history.push({ input, result });
this.updateHistoryDisplay();
},

updateHistoryDisplay: function() {
this.historyList.innerHTML = '';
this.history.forEach(item => {
const li = document.createElement('li');
li.textContent = `${item.input} = ${item.result}`;
this.historyList.appendChild(li);
});
},

clearHistory: function() {
this.history = [];
this.updateHistoryDisplay();
},

handleMemoryAction: function(event) {
const action = event.target.dataset.action;
switch (action) {
case 'mc':
this.memory = 0;
break;
case 'mr':
this.currentInput = this.memory.toString();
break;
case 'm-plus':
this.memory += parseFloat(this.currentInput) || 0;
break;
case 'm-minus':
this.memory -= parseFloat(this.currentInput) || 0;
break;
case 'ms':
this.memory = parseFloat(this.currentInput) || 0;
break;
}
this.updateMemoryDisplay();
this.updateDisplay();
},

updateMemoryDisplay: function() {
this.memoryList.innerHTML = '';
if (this.memory !== 0) {
const li = document.createElement('li');
li.textContent = this.memory;
this.memoryList.appendChild(li);
}
},

handleFunctionSwitch: function(event) {
if (event.target.classList.contains('switcher-btn')) {
const panel = event.target.dataset.panel;
this.showPanel(panel);
}
},

showPanel: function(panelId) {
const panels = document.querySelectorAll('.feature-panel');
panels.forEach(panel => panel.style.display = 'none');
document.getElementById(panelId).style.display = 'block';

const buttons = this.functionSwitcher.querySelectorAll('.switcher-btn');
buttons.forEach(btn => btn.classList.remove('active'));
this.functionSwitcher.querySelector(`[data-panel="${panelId}"]`).classList.add('active');
},

handleAISubmit: function() {
const query = this.aiInput.value;
// Here you would typically send the query to an AI service
// For this example, we'll just echo the query
this.aiResponse.textContent = `AI response to: ${query}`;
this.aiInput.value = '';
},

loadUnitOptions: function() {
// This would typically load unit options from a data source
// For this example, we'll just add a few sample options
const lengthUnits = ['meters', 'feet', 'inches', 'kilometers'];
const weightUnits = ['kg', 'lbs', 'oz', 'g'];
const temperatureUnits = ['Celsius', 'Fahrenheit', 'Kelvin'];

this.populateUnitSelect(this.fromUnit, lengthUnits);
this.populateUnitSelect(this.toUnit, lengthUnits);
},

populateUnitSelect: function(select, units) {
select.innerHTML = '';
units.forEach(unit => {
const option = document.createElement('option');
option.value = unit;
option.textContent = unit;
select.appendChild(option);
});
},

performUnitConversion: function() {
// This would typically use a conversion library or API
// For this example, we'll just echo the input
const fromValue = this.fromValue.value;
const fromUnit = this.fromUnit.value;
const toUnit = this.toUnit.value;
this.toValue.value = `${fromValue} ${fromUnit} in ${toUnit}`;
},

loadFormulas: function(category) {
// This would typically load formulas from a data source
// For this example, we'll just add a few sample formulas
const formulas = {
algebra: ['a² + b² = c²', 'y = mx + b'],
geometry: ['A = πr²', 'V = lwh'],
trigonometry: ['sin²θ + cos²θ = 1', 'tan θ = sin θ / cos θ'],
calculus: ['f\'(x) = lim[h→0] (f(x+h) - f(x)) / h', '∫f(x)dx = F(x) + C']
};

this.formulaList.innerHTML = '';
formulas[category].forEach(formula => {
const li = document.createElement('li');
li.textContent = formula;
this.formulaList.appendChild(li);
});
},

switchFormulaCategory: function(event) {
if (event.target.classList.contains('category-btn')) {
const category = event.target.dataset.category;
this.loadFormulas(category);

const buttons = this.formulaCategories.querySelectorAll('.category-btn');
buttons.forEach(btn => btn.classList.remove('active'));
event.target.classList.add('active');
}
},

setupGraphCanvas: function() {
// Set up the canvas for graphing
// This would typically involve setting up axes, scales, etc.
},

plotGraph: function() {
const equation = this.equationInput.value;
// This would typically use a graphing library to plot the equation
// For this example, we'll just echo the equation
this.graphCanvas.getContext('2d').fillText(`Graph of ${equation}`, 10, 50);
},

switchBase: function(event) {
if (event.target.classList.contains('base-btn')) {
const base = parseInt(event.target.dataset.base);
this.currentBase = base;
this.updateBaseDisplay();

const buttons = this.baseSwitcher.querySelectorAll('.base-btn');
buttons.forEach(btn => btn.classList.remove('active'));
event.target.classList.add('active');
}
},

updateBaseDisplay: function() {
// Convert the current input to the selected base
// This is a simplification and would need more robust implementation
const decimalValue = parseInt(this.currentInput, 10);
this.currentInput = decimalValue.toString(this.currentBase);
this.updateDisplay();
},

performBitOperation: function(event) {
if (event.target.classList.contains('bit-op-btn')) {
const operation = event.target.dataset.action;
// This would typically perform the bit operation
// For this example, we'll just echo the operation
this.currentInput += ` ${operation} `;
this.updateDisplay();
}
}
};

calculatorApp.init();
});
</script>
</body>
</html>
<style>
:root {
    --primary-color: #4285f4;
    --secondary-color: #34a853;
    --tertiary-color: #fbbc05;
    --quaternary-color: #ea4335;
    --background-color: #f8f9fa;
    --text-color: #202124;
    --button-text-color: #ffffff;
    --button-hover-color: #3367d6;
    --panel-background: #ffffff;
    --border-color: #dadce0;
}

body {
    font-family: 'Roboto', sans-serif;
    margin: 0;
    padding: 0;
    background-color: var(--background-color);
    color: var(--text-color);
}

#calculator-app {
    max-width: 1200px;
    margin: 0 auto;
    padding: 20px;
}

header {
    background-color: var(--primary-color);
    padding: 10px 20px;
    color: var(--button-text-color);
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
}

h1 {
    margin: 0;
    font-size: 24px;
}

#menu-toggle, #ai-toggle {
    background: none;
    border: none;
    color: var(--button-text-color);
    font-size: 20px;
    cursor: pointer;
}

main {
    display: flex;
    margin-top: 20px;
}

#calculator-container {
    flex: 2;
    background-color: var(--panel-background);
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    padding: 20px;
}

#display-container {
    background-color: var(--background-color);
    border-radius: 8px;
    padding: 10px;
    margin-bottom: 20px;
}

#history-display {
    font-size: 14px;
    color: #5f6368;
    min-height: 20px;
}

#input-display {
    font-size: 36px;
    font-weight: bold;
    margin: 10px 0;
}

#result-display {
    font-size: 24px;
    color: var(--secondary-color);
}

#keypad-container {
    display: flex;
    flex-direction: column;
}

.keypad-row {
    display: flex;
    justify-content: space-between;
    margin-bottom: 10px;
}

button {
    width: 60px;
    height: 60px;
    border: none;
    border-radius: 50%;
    font-size: 18px;
    font-weight: bold;
    cursor: pointer;
    transition: background-color 0.3s;
}

.number-btn {
    background-color: #f1f3f4;
    color: var(--text-color);
}

.operator-btn {
    background-color: #dadce0;
    color: var(--text-color);
}

.function-btn {
    background-color: #dadce0;
    color: var(--text-color);
}

.advanced-btn {
    background-color: #e8f0fe;
    color: var(--primary-color);
}

button:hover {
    background-color: var(--button-hover-color);
    color: var(--button-text-color);
}

#function-switcher {
    display: flex;
    justify-content: space-around;
    margin-top: 20px;
}

.switcher-btn {
    background-color: transparent;
    border: none;
    color: var(--primary-color);
    font-size: 16px;
    cursor: pointer;
    padding: 10px;
    border-bottom: 2px solid transparent;
}

.switcher-btn.active {
    border-bottom-color: var(--primary-color);
}

#side-panels {
    flex: 1;
    margin-left: 20px;
}

.side-panel {
    background-color: var(--panel-background);
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    padding: 20px;
    margin-bottom: 20px;
}

h3 {
    margin-top: 0;
    color: var(--primary-color);
}

#ai-input {
    width: 100%;
    height: 80px;
    margin-bottom: 10px;
    padding: 10px;
    border: 1px solid var(--border-color);
    border-radius: 4px;
    resize: none;
}

#ai-submit {
    background-color: var(--primary-color);
    color: var(--button-text-color);
    border: none;
    border-radius: 4px;
    padding: 10px 20px;
    cursor: pointer;
}

#ai-response {
    margin-top: 10px;
    padding: 10px;
    background-color: #e8f0fe;
    border-radius: 4px;
}

#history-list, #memory-list {
    list-style-type: none;
    padding: 0;
}

#history-list li, #memory-list li {
    margin-bottom: 5px;
    padding: 5px;
    background-color: #f1f3f4;
    border-radius: 4px;
}

#clear-history {
    background-color: var(--quaternary-color);
    color: var(--button-text-color);
    border: none;
    border-radius: 4px;
    padding: 5px 10px;
    cursor: pointer;
    margin-top: 10px;
}

.memory-btn {
    background-color: #e8f0fe;
    color: var(--primary-color);
    border: none;
    border-radius: 4px;
    padding: 5px 10px;
    margin-right: 5px;
    cursor: pointer;
}

#additional-features {
    margin-top: 20px;
}

.feature-panel {
    background-color: var(--panel-background);
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
    padding: 20px;
    margin-bottom: 20px;
}

#unit-converter select, #unit-converter input {
    width: 100%;
    padding: 5px;
    margin-bottom: 10px;
    border: 1px solid var(--border-color);
    border-radius: 4px;
}

#convert-btn {
    background-color: var(--secondary-color);
    color: var(--button-text-color);
    border: none;
    border-radius: 4px;
    padding: 10px 20px;
    cursor: pointer;
}

#formula-categories {
    display: flex;
    justify-content: space-between;
    margin-bottom: 10px;
}

.category-btn {
    background-color: transparent;
    border: none;
    color: var(--primary-color);
    cursor: pointer;
    padding: 5px 10px;
    border-radius: 4px;
}

.category-btn.active {
    background-color: var(--primary-color);
    color: var(--button-text-color);
}

#formula-list {
    list-style-type: none;
    padding: 0;
}

#formula-list li {
    margin-bottom: 5px;
    padding: 5px;
    background-color: #f1f3f4;
    border-radius: 4px;
}

#graph-canvas {
    width: 100%;
    height: 200px;
    background-color: #f1f3f4;
    border-radius: 4px;
    margin-bottom: 10px;
}

#equation-input {
    width: calc(100% - 80px);
    padding: 5px;
    margin-right: 10px;
    border: 1px solid var(--border-color);
    border-radius: 4px;
}

#plot-graph {
    background-color: var(--tertiary-color);
    color: var(--text-color);
    border: none;
    border-radius: 4px;
    padding: 5px 10px;
    cursor: pointer;
}

#base-switcher {
    display: flex;
    justify-content: space-between;
    margin-bottom: 10px;
}

.base-btn {
    background-color: transparent;
    border: none;
    color: var(--primary-color);
    cursor: pointer;
    padding: 5px 10px;
    border-radius: 4px;
}

.base-btn.active {
    background-color: var(--primary-color);
    color: var(--button-text-color);
}

#bit-operations {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
}

.bit-op-btn {
    background-color: #e8f0fe;
    color: var(--primary-color);
    border: none;
    border-radius: 4px;
    padding: 5px 10px;
    cursor: pointer;
}

footer {
    text-align: center;
    margin-top: 20px;
    color: #5f6368;
}

@media (max-width: 768px) {
    main {
        flex-direction: column;
    }

    #side-panels {
        margin-left: 0;
        margin-top: 20px;
    }

    button {
        width: 50px;
        height: 50px;
        font-size: 16px;
    }
}
</style>
<script>
class AdvancedCalculator {
    constructor() {
        this.initializeElements();
        this.bindEvents();
        this.currentInput = '';
        this.memory = 0;
        this.history = [];
        this.currentBase = 10;
        this.aiModel = new AIModel();
        this.graphingCalculator = new GraphingCalculator('graph-canvas');
        this.unitConverter = new UnitConverter();
        this.formulaSheet = new FormulaSheet();
        this.programmerCalculator = new ProgrammerCalculator();
    }

    initializeElements() {
        this.display = document.getElementById('input-display');
        this.resultDisplay = document.getElementById('result-display');
        this.historyDisplay = document.getElementById('history-display');
        this.keypadContainer = document.getElementById('keypad-container');
        this.functionSwitcher = document.getElementById('function-switcher');
        this.aiInput = document.getElementById('ai-input');
        this.aiSubmit = document.getElementById('ai-submit');
        this.aiResponse = document.getElementById('ai-response');
        this.historyList = document.getElementById('history-list');
        this.clearHistoryBtn = document.getElementById('clear-history');
        this.memoryList = document.getElementById('memory-list');
    }

    bindEvents() {
        this.keypadContainer.addEventListener('click', this.handleKeypadClick.bind(this));
        this.functionSwitcher.addEventListener('click', this.handleFunctionSwitch.bind(this));
        this.aiSubmit.addEventListener('click', this.handleAISubmit.bind(this));
        this.clearHistoryBtn.addEventListener('click', this.clearHistory.bind(this));
        document.getElementById('memory-panel').addEventListener('click', this.handleMemoryAction.bind(this));
    }

    handleKeypadClick(event) {
        const button = event.target;
        if (button.matches('button')) {
            const action = button.dataset.action;
            const value = button.dataset.value;

            if (value) {
                this.appendToInput(value);
            } else if (action) {
                this.performAction(action);
            }

            this.updateDisplay();
        }
    }

    appendToInput(value) {
        this.currentInput += value;
    }

    performAction(action) {
        switch (action) {
            case 'clear':
                this.clear();
                break;
            case 'backspace':
                this.backspace();
                break;
            case 'calculate':
                this.calculate();
                break;
            case 'toggle-sign':
                this.toggleSign();
                break;
            case 'percentage':
                this.percentage();
                break;
            default:
                if (this.isOperator(action)) {
                    this.appendToInput(` ${action} `);
                } else {
                    this.performMathFunction(action);
                }
        }
    }

    isOperator(action) {
        return ['+', '-', '*', '/', '^'].includes(action);
    }

    performMathFunction(func) {
        switch (func) {
            case 'sin':
            case 'cos':
            case 'tan':
            case 'log':
            case 'ln':
            case 'sqrt':
                this.currentInput = `${func}(${this.currentInput})`;
                break;
            case 'factorial':
                this.currentInput = `factorial(${this.currentInput})`;
                break;
            case 'pi':
                this.currentInput += Math.PI;
                break;
            case 'e':
                this.currentInput += Math.E;
                break;
        }
    }

    clear() {
        this.currentInput = '';
        this.resultDisplay.textContent = '';
    }

    backspace() {
        this.currentInput = this.currentInput.slice(0, -1);
    }

    toggleSign() {
        if (this.currentInput !== '' && !isNaN(this.currentInput)) {
            this.currentInput = (-parseFloat(this.currentInput)).toString();
        }
    }

    percentage() {
        if (this.currentInput !== '' && !isNaN(this.currentInput)) {
            this.currentInput = (parseFloat(this.currentInput) / 100).toString();
        }
    }

    calculate() {
        try {
            const result = math.evaluate(this.currentInput);
            this.addToHistory(this.currentInput, result);
            this.resultDisplay.textContent = result;
            this.currentInput = result.toString();
        } catch (error) {
            this.resultDisplay.textContent = 'Error';
        }
    }

    updateDisplay() {
        this.display.textContent = this.currentInput;
    }

    addToHistory(input, result) {
        this.history.push({ input, result });
        this.updateHistoryDisplay();
    }

    updateHistoryDisplay() {
        this.historyList.innerHTML = '';
        this.history.slice(-5).forEach(item => {
            const li = document.createElement('li');
            li.textContent = `${item.input} = ${item.result}`;
            this.historyList.appendChild(li);
        });
    }

    clearHistory() {
        this.history = [];
        this.updateHistoryDisplay();
    }

    handleFunctionSwitch(event) {
        if (event.target.matches('.switcher-btn')) {
            const panel = event.target.dataset.panel;
            this.showPanel(panel);
        }
    }

    showPanel(panelId) {
        const panels = document.querySelectorAll('.feature-panel');
        panels.forEach(panel => panel.style.display = 'none');
        document.getElementById(panelId).style.display = 'block';

        const buttons = this.functionSwitcher.querySelectorAll('.switcher-btn');
        buttons.forEach(btn => btn.classList.remove('active'));
        this.functionSwitcher.querySelector(`[data-panel="${panelId}"]`).classList.add('active');
    }

    handleAISubmit() {
        const query = this.aiInput.value;
        this.aiModel.processQuery(query)
            .then(response => {
                this.aiResponse.textContent = response;
            })
            .catch(error => {
                this.aiResponse.textContent = 'An error occurred while processing your request.';
            });
    }

    handleMemoryAction(event) {
        if (event.target.matches('.memory-btn')) {
            const action = event.target.dataset.action;
            switch (action) {
                case 'mc':
                    this.memoryClear();
                    break;
                case 'mr':
                    this.memoryRecall();
                    break;
                case 'm-plus':
                    this.memoryAdd();
                    break;
                case 'm-minus':
                    this.memorySubtract();
                    break;
                case 'ms':
                    this.memoryStore();
                    break;
            }
            this.updateMemoryDisplay();
        }
    }

    memoryClear() {
        this.memory = 0;
    }

    memoryRecall() {
        this.currentInput = this.memory.toString();
        this.updateDisplay();
    }

    memoryAdd() {
        if (this.currentInput !== '' && !isNaN(this.currentInput)) {
            this.memory += parseFloat(this.currentInput);
        }
    }

    memorySubtract() {
        if (this.currentInput !== '' && !isNaN(this.currentInput)) {
            this.memory -= parseFloat(this.currentInput);
        }
    }

    memoryStore() {
        if (this.currentInput !== '' && !isNaN(this.currentInput)) {
            this.memory = parseFloat(this.currentInput);
        }
    }

    updateMemoryDisplay() {
        this.memoryList.innerHTML = '';
        if (this.memory !== 0) {
            const li = document.createElement('li');
            li.textContent = this.memory;
            this.memoryList.appendChild(li);
        }
    }
}

class AIModel {
    async processQuery(query) {
        // This is a placeholder for AI processing
        // In a real implementation, this would call an AI service
        return new Promise((resolve) => {
            setTimeout(() => {
                resolve(`AI response to: "${query}"`);
            }, 1000);
        });
    }
}

class GraphingCalculator {
    constructor(canvasId) {
        this.canvas = document.getElementById(canvasId);
        this.ctx = this.canvas.getContext('2d');
        this.setupCanvas();
    }

    setupCanvas() {
        // Set up the canvas for graphing
        this.ctx.fillStyle = 'black';
        this.ctx.fillRect(0, 0, this.canvas.width, this.canvas.height);
    }

    plotGraph(equation) {
        // This is a placeholder for graph plotting
        // In a real implementation, this would use a graphing library
        this.ctx.fillStyle = 'white';
        this.ctx.font = '16px Arial';
        this.ctx.fillText(`Graph of ${equation}`, 10, 30);
    }
}

class UnitConverter {
    convert(value, fromUnit, toUnit) {
        // This is a placeholder for unit conversion
        // In a real implementation, this would use a conversion library
        return `${value} ${fromUnit} = ${value * 2} ${toUnit}`;
    }
}

class FormulaSheet {
    getFormulas(category) {
        // This is a placeholder for formula retrieval
        const formulas = {
            algebra: ['a² + b² = c²', 'y = mx + b'],
            geometry: ['A = πr²', 'V = lwh'],
            trigonometry: ['sin²θ + cos²θ = 1', 'tan θ = sin θ / cos θ'],
            calculus: ['f\'(x) = lim[h→0] (f(x+h) - f(x)) / h', '∫f(x)dx = F(x) + C']
        };
        return formulas[category] || [];
    }
}

class ProgrammerCalculator {
    constructor() {
        this.currentBase = 10;
    }

    setBase(base) {
        this.currentBase = base;
    }

    convert(number, fromBase, toBase) {
        return parseInt(number, fromBase).toString(toBase);
    }

    performBitOperation(operation, a, b) {
        switch (operation) {
            case 'AND':
                return a & b;
            case 'OR':
                return a | b;
            case 'XOR':
                return a ^ b;
            case 'NOT':
                return ~a;
            default:
                return 'Invalid operation';
        }
    }
}

// Initialize the calculator when the DOM is loaded
document.addEventListener('DOMContentLoaded', () => {
    const calculator = new AdvancedCalculator();
});
</script>s
