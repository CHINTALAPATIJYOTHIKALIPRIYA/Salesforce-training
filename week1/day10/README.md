 Day 9: Lightning Web Component (LWC) Communication & Architecture

1. Component Communication
In LWC, components maintain strict boundary encapsulation. To create a cohesive application, they communicate using structured paradigms depending on their relationship in the DOM tree:

- Parent-to-Child: The parent component passes data down to a child component by setting properties marked with the @api decorator.
- Child-to-Parent: The child component dispatches a standard or custom browser event (new CustomEvent('event_name', { detail: data })). The parent listens for this event and handles it accordingly.
- Unrelated Components: Components residing in completely different DOM hierarchies communicate via the Lightning Message Service (LMS) or a Publish-Subscribe (PubSub) utility.


2. Dashboard Design
The system utilizes a decoupled, modular dashboard layout to ensure maintainability and a seamless user experience. The setup includes:

- Filter & Search Component (Child A): Captures user inputs, dropdown selections, and active search queries.
- Data Table Component (Child B): Listens for dataset updates and renders records dynamically inside a clean, interactive grid.
- Metrics/KPI Component (Child C): Summarizes relevant data points and aggregates key information visually.
- Dashboard Controller (Parent Container): Acts as the central orchestrator that coordinates actions, maintains global states, and routes data appropriately between the child modules.

---

3. Data Flow Explanation
The application enforces a strict, predictable unidirectional data flow to prevent side effects and keep components loosely coupled:

    [ Parent Dashboard Container ]
       │                      ▲
       │ (Passes Data Down)   │ (Dispatches Event Up)
       ▼                      │
 [ Data Table Component ]   [ Filter Component ]

1. User Action: A user applies a new search filter inside the Filter Component.
2. Event Dispatched: The Filter Component catches this interaction and fires a custom event upward, passing the new filter criteria in its payload.
3. State Management: The Parent Container captures the event, updates its internal state, and queries or filters the raw dataset.
4. Data Propagation: The updated data payload is pushed downward into the Data Table Component through public @api properties, prompting an efficient, automatic UI re-render.

---

4. Aura vs LWC
Salesforce shifted from the legacy Aura Framework to modern Lightning Web Components to better align with the evolution of web browsers.

- Feature: Architecture
  - Aura Framework: Heavy, proprietary abstraction layer built over older JS standards.
  - Lightning Web Components (LWC): Lightweight framework built natively on modern web components standards.

- Feature: Performance
  - Aura Framework: Slower; execution relies heavily on framework-side rendering layers.
  - Lightning Web Components (LWC): Exceptional; runs natively inside the browser engine for lightning-fast speeds.

- Feature: Data Binding
  - Aura Framework: Bi-directional ({!v.prop}) — can lead to unpredictable side effects.
  - Lightning Web Components (LWC): Unidirectional ({prop}) — predictable, easier to debug, and control.

- Feature: Development
  - Aura Framework: Requires learning proprietary .cmp tags and unique JS structures.
  - Lightning Web Components (LWC): Uses standard HTML5 templates, modern clean ES6+ JavaScript, and CSS3.

- Feature: Testing Environment
  - Aura Framework: Difficult to mock and unit test independently outside of Salesforce environments.
  - Lightning Web Components (LWC): Highly testable locally utilizing industry-standard tools like Jest.

---

5. Reflection & Revision Task Answers

### Why do enterprise applications need modular architecture?
Enterprise applications feature massive codebases built and managed over many years by scaling development teams. A monolithic structure quickly leads to "spaghetti code," where a small patch in one feature unexpectedly breaks another.

Modular architecture separates functionalities into small, decoupled blocks. This is indispensable for enterprise apps because it delivers:
- Maintainability: Code isolates easily. If a bug surfaces within the data table, fixing it inside that singular component eliminates the risk of introducing regressions elsewhere.
- Parallel Development: Teams can develop separate functional views concurrently without running into constant, messy Git conflict blocks.
- Reusability: A robust component (like a custom multi-select picker) can be dropped into entirely different application modules instantly, eliminating duplicative engineering hours.
  
