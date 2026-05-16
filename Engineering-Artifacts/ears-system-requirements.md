# GPT Researcher EARS System Requirements

Generated on 2026-05-16 from the repository implementation, documentation, and tests.

## Visual Syntax Legend

- <span style="color:#16a34a"><strong>While precondition clauses</strong></span> mark active states.
- <span style="color:#d97706"><strong>When trigger clauses</strong></span> mark triggering events.
- <span style="color:#7c3aed"><strong>Where optional feature clauses</strong></span> mark feature-scoped behavior.
- <span style="color:#dc2626"><strong>If fault clauses</strong></span> mark unwanted behavior and fault conditions.
- <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> marks the system name.
- <span style="color:#ea580c"><strong>shall</strong></span> marks mandatory behavior.
- System responses remain unstyled natural language.

## Ubiquitous Requirements

REQ-GPTR-U-001: <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> generate factual, unbiased research reports with citations from gathered research context.

REQ-GPTR-U-002: <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> maintain research context, visited URLs, research sources, research images, total costs, and per-step costs for each research task.

REQ-GPTR-U-003: <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> support research report, resource report, outline report, custom report, detailed report, subtopic report, and deep research report types.

REQ-GPTR-U-004: <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> support web, local document, hybrid, Azure document, LangChain document, and LangChain vector store report sources.

REQ-GPTR-U-005: <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> load configuration from defaults, configuration files, and environment variables.

REQ-GPTR-U-006: <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> give environment variables precedence over configuration-file values.

REQ-GPTR-U-007: <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> expose a Python package interface, a CLI interface, a FastAPI interface, and a websocket-enabled frontend interface.

REQ-GPTR-U-008: <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> write generated report artifacts to the outputs directory.

REQ-GPTR-U-009: <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> support configurable writing tones for generated reports.

REQ-GPTR-U-010: <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> track token-derived research costs for agent selection, research, report writing, image planning, and deep research steps.

## Event-Driven Requirements

REQ-GPTR-E-001: <span style="color:#d97706"><strong>When an agent instance is initialized</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> configure retrievers, memory, prompt family, context manager, browser manager, source curator, report generator, image generator, and research conductor.

REQ-GPTR-E-002: <span style="color:#d97706"><strong>When MCP configurations are supplied</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> process the MCP configurations and preserve explicit user retriever settings.

REQ-GPTR-E-003: <span style="color:#d97706"><strong>When a research task is started without a predefined agent and role</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> choose an agent and role for the query.

REQ-GPTR-E-004: <span style="color:#d97706"><strong>When research is conducted</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> plan subqueries, retrieve source material, scrape or load content, compress relevant context, and store the resulting context.

REQ-GPTR-E-005: <span style="color:#d97706"><strong>When a report is written</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> generate the report from the selected report type, tone, report format, language, context, and available images.

REQ-GPTR-E-006: <span style="color:#d97706"><strong>When a custom prompt is supplied for report writing</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> generate the report from the custom prompt and the available context.

REQ-GPTR-E-007: <span style="color:#d97706"><strong>When quick search is requested without aggregation</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> return raw search results.

REQ-GPTR-E-008: <span style="color:#d97706"><strong>When quick search is requested with aggregation</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> summarize the search results.

REQ-GPTR-E-009: <span style="color:#d97706"><strong>When the CLI is invoked with a query and report type</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> conduct research, write a Markdown report, and optionally create PDF and DOCX outputs.

REQ-GPTR-E-010: <span style="color:#d97706"><strong>When an HTTP report request is submitted for background generation</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> enqueue report generation and return a research identifier.

REQ-GPTR-E-011: <span style="color:#d97706"><strong>When an HTTP report request is submitted for immediate generation</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> generate the report, write export files, and return research metadata.

REQ-GPTR-E-012: <span style="color:#d97706"><strong>When a websocket start command is received</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> parse the task settings and start a streaming research task.

REQ-GPTR-E-013: <span style="color:#d97706"><strong>When a websocket ping command is received</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> respond with pong.

REQ-GPTR-E-014: <span style="color:#d97706"><strong>When a chat request is received with a report and message history</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> answer in markdown using the report context.

REQ-GPTR-E-015: <span style="color:#d97706"><strong>When a chat request requires current information</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> use quick search when the search tool is available.

REQ-GPTR-E-016: <span style="color:#d97706"><strong>When a report record is created or updated through the report API</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> persist the report identifier, question, answer, ordered data, chat messages, and timestamp.

REQ-GPTR-E-017: <span style="color:#d97706"><strong>When local document files are listed</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> create the configured document directory when it does not exist and return the available filenames.

REQ-GPTR-E-018: <span style="color:#d97706"><strong>When a file is uploaded for local research</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> store the uploaded file in the configured document directory and load the document collection.

REQ-GPTR-E-019: <span style="color:#d97706"><strong>When a file deletion request is received</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> delete the named document file from the configured document directory when it exists.

REQ-GPTR-E-020: <span style="color:#d97706"><strong>When websocket research completes</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> generate Markdown, PDF, DOCX, and JSON log artifact paths for the client.

## State-Driven Requirements

REQ-GPTR-S-001: <span style="color:#16a34a"><strong>While source URLs are supplied</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> gather context from the supplied URLs before other source workflows.

REQ-GPTR-S-002: <span style="color:#16a34a"><strong>While the report source is web</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> gather context through the configured retrievers and browser scraping.

REQ-GPTR-S-003: <span style="color:#16a34a"><strong>While the report source is local</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> load supported local documents from the configured document path and use them as retrieval context.

REQ-GPTR-S-004: <span style="color:#16a34a"><strong>While the report source is hybrid</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> combine local or online document context with web context.

REQ-GPTR-S-005: <span style="color:#16a34a"><strong>While the report source is Azure</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> load Azure blob documents and use them as retrieval context.

REQ-GPTR-S-006: <span style="color:#16a34a"><strong>While the report source is LangChain documents</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> load the supplied LangChain documents and use them as retrieval context.

REQ-GPTR-S-007: <span style="color:#16a34a"><strong>While the report source is LangChain vector store</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> retrieve context from the supplied vector store and optional filter.

REQ-GPTR-S-008: <span style="color:#16a34a"><strong>While source curation is enabled</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> curate gathered research sources before report writing.

REQ-GPTR-S-009: <span style="color:#16a34a"><strong>While verbose mode is enabled</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> stream research status, subqueries, source additions, image status, report status, and cost updates.

REQ-GPTR-S-010: <span style="color:#16a34a"><strong>While detailed report mode is active</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> conduct initial research, generate subtopics, research each subtopic, write an introduction, assemble a table of contents, write a conclusion, and add references.

REQ-GPTR-S-011: <span style="color:#16a34a"><strong>While deep research mode is active</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> generate follow-up questions, explore recursive research branches, track progress, aggregate learnings, preserve citations, and trim context to the configured word limit.

REQ-GPTR-S-012: <span style="color:#16a34a"><strong>While a websocket research task is running</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> keep the running task active and reject concurrent commands.

REQ-GPTR-S-013: <span style="color:#16a34a"><strong>While the frontend websocket connection is open</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> accept heartbeat pings and stream JSON messages for logs, images, reports, errors, and artifact paths.

REQ-GPTR-S-014: <span style="color:#16a34a"><strong>While report chat is active</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> preserve chat messages with the associated report record.

## Optional Feature Requirements

REQ-GPTR-O-001: <span style="color:#7c3aed"><strong>Where MCP research is enabled</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> add MCP retrieval capability, apply the selected MCP strategy, and include MCP context with web context.

REQ-GPTR-O-002: <span style="color:#7c3aed"><strong>Where MCP fast strategy is selected</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> run MCP research once for the original query and reuse cached MCP results for subqueries.

REQ-GPTR-O-003: <span style="color:#7c3aed"><strong>Where MCP deep strategy is selected</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> run MCP research for each subquery.

REQ-GPTR-O-004: <span style="color:#7c3aed"><strong>Where MCP disabled strategy is selected</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> skip MCP research.

REQ-GPTR-O-005: <span style="color:#7c3aed"><strong>Where image generation is configured</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> identify visualization opportunities, generate images before report writing, and pass generated image markdown to the report writer.

REQ-GPTR-O-006: <span style="color:#7c3aed"><strong>Where multi-agent reporting is requested</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> run the multi-agent research workflow and return the generated report.

REQ-GPTR-O-007: <span style="color:#7c3aed"><strong>Where PDF export is enabled</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> convert Markdown report content to a PDF file.

REQ-GPTR-O-008: <span style="color:#7c3aed"><strong>Where DOCX export is enabled</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> convert Markdown report content to a DOCX file.

REQ-GPTR-O-009: <span style="color:#7c3aed"><strong>Where domain filters are supplied</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> restrict search operations to the supplied domains when the selected retriever supports domain filtering.

REQ-GPTR-O-010: <span style="color:#7c3aed"><strong>Where a vector store is supplied</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> load document data into the vector store and retrieve similar content from it.

## Unwanted Behavior Requirements

REQ-GPTR-F-001: <span style="color:#dc2626"><strong>If a configuration path is missing or invalid</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> use the default configuration.

REQ-GPTR-F-002: <span style="color:#dc2626"><strong>If retriever configuration contains invalid retrievers</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> warn and default to the Tavily retriever.

REQ-GPTR-F-003: <span style="color:#dc2626"><strong>If document loading finds no loadable documents</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> raise a document loading error.

REQ-GPTR-F-004: <span style="color:#dc2626"><strong>If MCP research fails for a query</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> log the MCP error and continue with other sources.

REQ-GPTR-F-005: <span style="color:#dc2626"><strong>If subquery processing fails</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> stream a subquery error and return empty context for that subquery.

REQ-GPTR-F-006: <span style="color:#dc2626"><strong>If image generation is unavailable or image planning fails</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> skip image generation and continue report generation.

REQ-GPTR-F-007: <span style="color:#dc2626"><strong>If report generation fails with the system-message format</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> retry report generation with a user-message-only format.

REQ-GPTR-F-008: <span style="color:#dc2626"><strong>If a requested report is not found</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> return a not-found response.

REQ-GPTR-F-009: <span style="color:#dc2626"><strong>If a report API update or deletion targets a missing report</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> return a not-found response.

REQ-GPTR-F-010: <span style="color:#dc2626"><strong>If a websocket command is unknown</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> send an unknown-command error.

REQ-GPTR-F-011: <span style="color:#dc2626"><strong>If websocket chat payload parsing fails</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> send an invalid-message-format chat response.

REQ-GPTR-F-012: <span style="color:#dc2626"><strong>If chat web search is requested without a Tavily API key</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> return a web-search-disabled result.

REQ-GPTR-F-013: <span style="color:#dc2626"><strong>If PDF conversion fails</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> return an empty PDF path.

REQ-GPTR-F-014: <span style="color:#dc2626"><strong>If DOCX conversion fails</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> return an empty DOCX path.

REQ-GPTR-F-015: <span style="color:#dc2626"><strong>If a nonnumeric cost value is added</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> raise a cost validation error.

REQ-GPTR-F-016: <span style="color:#dc2626"><strong>If a file deletion request targets a missing file</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> return a file-not-found response.

REQ-GPTR-F-017: <span style="color:#dc2626"><strong>If a chat completion returns no assistant content</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> return a fallback apology message.

REQ-GPTR-F-018: <span style="color:#dc2626"><strong>If websocket message handling raises an unexpected exception</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> log the exception and disconnect the websocket.

REQ-GPTR-F-019: <span style="color:#dc2626"><strong>If a websocket task raises an unexpected exception</strong></span>, then <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> log the exception and stream an error log message.

## Complex Requirements

REQ-GPTR-C-001: <span style="color:#16a34a"><strong>While source URLs are supplied</strong></span>, <span style="color:#d97706"><strong>when complementing source URLs is enabled</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> gather additional web-search context after processing the supplied URLs.

REQ-GPTR-C-002: <span style="color:#16a34a"><strong>While deep research mode is active</strong></span>, <span style="color:#d97706"><strong>when a recursive branch fails</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> skip the failed branch and continue aggregating successful branch results.

REQ-GPTR-C-003: <span style="color:#16a34a"><strong>While MCP fast strategy is selected</strong></span>, <span style="color:#d97706"><strong>when a subquery is processed after the original query</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> reuse cached MCP context for the subquery.

REQ-GPTR-C-004: <span style="color:#16a34a"><strong>While verbose mode is enabled</strong></span>, <span style="color:#d97706"><strong>when an image concept is generated successfully</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> stream image readiness information before report writing.

REQ-GPTR-C-005: <span style="color:#16a34a"><strong>While a report record exists</strong></span>, <span style="color:#d97706"><strong>when a chat message is added through the report API</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> append the message to the report chat history and update the report timestamp.

REQ-GPTR-C-006: <span style="color:#16a34a"><strong>While the frontend websocket connection is open</strong></span>, <span style="color:#d97706"><strong>when a report_complete message is received</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> replace the streamed answer with the complete report content.

REQ-GPTR-C-007: <span style="color:#16a34a"><strong>While a vector store is supplied</strong></span>, <span style="color:#d97706"><strong>when document data is loaded</strong></span>, <span style="color:#2563eb"><strong>The GPT Researcher</strong></span> <span style="color:#ea580c"><strong>shall</strong></span> load the document data into the vector store before retrieving similar content.
