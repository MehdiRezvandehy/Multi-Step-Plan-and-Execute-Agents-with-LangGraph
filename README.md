# Multi-Step-Plan-and-Execute-Agents-with-LangGraph

This work illustrates a multi-step task execution pipeline built with LangChain and LangGraph. The workflow is tailored to tackle complex queries by decomposing them into smaller, manageable steps, executing each sequentially, and re-planning dynamically when necessary. This structured approach enables the agent to effectively handle tasks involving multiple stages, such as retrieving information, interpreting results, and generating a final response.

**Steps:**

* **Initialize the LLM:** The process starts by initializing a language model, OpenAI’s GPT-3.5.
* **Tool and Prompt Setup:** Tools like `DuckDuckGoSearchRun` are configured, along with a custom prompt that shapes the agent’s behavior.
* **State and Planning Definition:** A structured state (e.g., `PlanExecute`) is defined to manage the input, plan, past actions, and final output. A planner component creates a step-by-step strategy to reach the task objective.
* **Re-Planning Mechanism:** A replanner dynamically updates the plan based on previous outcomes. If no further steps are needed, it finalizes the response.
* **Graph Construction and Node Definition:** A workflow graph is assembled with nodes representing planning (`plan_node`), execution (`agent_node`), and re-planning (`replan_node`). This graph governs task progression and ensures proper termination.
* **Workflow Execution:** The system is run with an input query, and the agent progresses through each step, ultimately delivering the final result.
