# AI refinement evaluation — Issue #2

Issue: [Create Barça News homepage](https://github.com/Junes2003/barca-news-factory/issues/2)

## Setup and method

The n8n workflow `01 - Refine Task` retrieves the GitHub issue, checks its author, sets the Refining label and sends its title and description to a Basic LLM Chain connected to Ollama (`llama3.2:latest`).

Original issue description: Create a homepage for Barça News with FC Barcelona colors, a navigation bar and a section for the latest news.

Two outputs were supplied by the project owner during interactive testing. The first revealed unsupported assumptions about the project. The prompt was then extended and the issue was tested again. The outputs below preserve the supplied wording; escaped newline characters are rendered as actual line breaks.

## Output 1 — before the prompt adjustment

> **Goal**
>
> Create a functional Barça News homepage with a clear and consistent design, incorporating FC Barcelona colors, a navigation bar, and a section for the latest news.
>
> **Motivation**
>
> The primary motivation is to provide a visually appealing and user-friendly homepage that effectively showcases Barça News content, enhancing the overall user experience.
>
> **Scope**
>
> The scope of this task includes designing and developing the homepage, ensuring that it adheres to Barça News Factory's brand guidelines and visual identity.
>
> **Dependencies and constraints**
>
> The homepage must be built using the latest version of the Barça News Factory's CMS (Content Management System) and integrate with the existing database for news articles. The design must be responsive and work seamlessly across various devices and screen sizes.
>
> **Acceptance criteria**
>
> To confirm successful completion, the following conditions must be met:
>
> 1. The homepage displays the Barça News Factory logo in the correct position and format.
> 2. The navigation bar is present and contains links to main sections (e.g., news, events, etc.).
> 3. The latest news section is displayed prominently on the homepage, with at least three news articles.
> 4. The homepage is responsive and works correctly on various devices and screen sizes.
> 5. The design and layout adhere to the Barça News Factory's brand guidelines and visual identity.
>
> **Verification**
>
> Verification of the acceptance criteria will be performed through a series of unit and integration tests, ensuring that the homepage functions as expected and meets the specified requirements.
>
> **Open questions**
>
> Please provide further clarification on the following:
>
> 1. What are the specific dimensions and requirements for the navigation bar's width and layout?
> 2. Are there any additional visual elements (e.g., images, graphics) that should be included on the homepage?
> 3. Are there any specific accessibility requirements for the homepage that should be considered?

## Prompt adjustment

The following text was appended to the existing AI Refinement prompt:

```text
The project is currently being built from scratch.
Do not assume that a CMS, database, framework, logo,
API or existing functionality is available.
Use simple local sample data where appropriate.
Ask the owner if technical requirements are unclear.
```

## Output 2 — after the prompt adjustment

> **Goal**
>
> Create a fully functional homepage for Barça News that incorporates FC Barcelona colors, a navigation bar, and a section for the latest news.
>
> **Motivation**
>
> The goal of this task is to provide a user-friendly and visually appealing homepage that effectively communicates the brand identity of Barça News.
>
> **Scope**
>
> The scope of this task includes designing and implementing the following features:
>
> - A navigation bar with links to relevant sections (e.g., latest news, articles, etc.)
> - A section for displaying the latest news, including title, description, and content
> - Incorporation of FC Barcelona colors (including but not limited to, primary color, secondary color, background color, etc.) throughout the design
> - Simple and responsive design that adapts to different screen sizes and devices
>
> **Dependencies and constraints**
>
> The following dependencies and constraints apply to this task:
>
> - No pre-existing CMS, database, framework, logo, API, or existing functionality will be available for this task.
> - Technical requirements for the project must be clarified by the owner before proceeding.
> - Use of simple local sample data will be used where appropriate to facilitate development and testing.
>
> **Acceptance criteria**
>
> To confirm that this task is complete and meets the requirements, the following acceptance criteria must be met:
>
> - The navigation bar is functional and links to the correct sections.
> - The latest news section is displayed correctly, including title, description, and content.
> - The FC Barcelona colors are consistently applied throughout the design.
> - The design is responsive and adapts to different screen sizes and devices.
>
> **Verification**
>
> Verification of these acceptance criteria will involve:
>
> - Manual testing of the navigation bar and latest news section.
> - Visual inspection to confirm the application of FC Barcelona colors.
> - Testing on different devices and screen sizes to ensure responsiveness.
>
> **Open questions**
>
> - Are there any specific technical requirements or constraints that need to be considered?
> - How does the logo of FC Barcelona need to be incorporated into the design?
> - Are there any specific fonts, images, or graphics that need to be used throughout the design?

## Short evaluation

| Criterion | Output 1 | Output 2 |
|---|---|---|
| Follows specification template | Yes | Yes |
| Unsupported assumptions | Existing CMS, database, logo and brand guidelines | No existing CMS/database assumed; still asks about a logo not requested |
| Local sample data | Not proposed | Explicitly proposed |
| Acceptance criteria | Some observable criteria, but unsupported requirements | Better aligned with original task; some criteria remain vague |
| Verification | Proposed unit/integration tests | Proposed manual and responsive-design checks |
| Clarification questions | Yes | Yes |

The second output is better aligned with the actual project because the model was explicitly given project context and told not to assume existing infrastructure. Further improvement could define measurable responsive-design criteria and avoid unnecessary questions or unapproved scope additions.

This is a qualitative comparison of two observed outputs, not a controlled benchmark or proof of general model reliability. No coding-agent implementation, acceptance tests, completed factory run or human approval is demonstrated by these outputs alone. The owner must still review the specification before approving the task.
