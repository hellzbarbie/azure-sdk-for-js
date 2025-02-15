## API Report File for "@azure/openai-assistants"

> Do not edit this file. It is a report generated by [API Extractor](https://api-extractor.com/).

```ts

import { OperationOptions } from '@azure-rest/core-client';

// @public
export interface Assistant {
    createdAt: Date;
    description: string | null;
    fileIds: string[];
    id: string;
    instructions: string | null;
    metadata?: Record<string, string> | null;
    model: string;
    name: string | null;
    tools: ToolDefinition[];
}

// @public
export interface AssistantCreationOptions {
    description?: string | null;
    fileIds?: string[];
    instructions?: string | null;
    metadata?: Record<string, string> | null;
    model: string;
    name?: string | null;
    tools?: ToolDefinition[];
}

// @public
export interface AssistantDeletionStatus extends DeletionStatus {
}

// @public
export interface AssistantFile {
    assistantId: string;
    createdAt: Date;
    id: string;
}

// @public
export interface AssistantFileDeletionStatus extends DeletionStatus {
}

// @public
export interface AssistantThread {
    createdAt: Date;
    id: string;
    metadata: Record<string, string> | null;
}

// @public
export interface AssistantThreadCreationOptions {
    messages?: {
        role: string;
        content: string;
    }[];
    metadata?: Record<string, string>;
}

// @public
export interface CancelRunOptions extends OperationOptions {
}

// @public
export interface CodeInterpreterImageOutput {
    image: CodeInterpreterImageReference;
    type: "image";
}

// @public
export interface CodeInterpreterImageReference {
    fileId: string;
}

// @public
export interface CodeInterpreterLogOutput {
    logs: string;
    type: "logs";
}

// @public
export interface CodeInterpreterToolCall {
    codeInterpreter: CodeInterpreterToolCallDetails;
    id: string;
    type: "code_interpreter";
}

// @public
export interface CodeInterpreterToolCallDetails {
    input: string;
    outputs: CodeInterpreterToolCallOutput[];
}

// @public
export type CodeInterpreterToolCallOutput = CodeInterpreterLogOutput | CodeInterpreterImageOutput;

// @public
export interface CodeInterpreterToolDefinition {
    type: "code_interpreter";
}

// @public
export interface CreateAndRunThreadOptions {
    assistantId: string;
    instructions?: string;
    metadata?: Record<string, string> | null;
    model?: string;
    thread?: AssistantThreadCreationOptions;
    tools?: ToolDefinition[];
}

// @public
export interface CreateAssistantFileOptions extends OperationOptions {
}

// @public
export interface CreateAssistantOptions extends OperationOptions {
}

// @public
export interface CreateMessageOptions extends OperationOptions {
    fileIds?: string[];
    metadata?: Record<string, string>;
}

// @public
export interface CreateRunOptions {
    additionalInstructions?: string | null;
    assistantId: string;
    instructions?: string | null;
    metadata?: Record<string, string> | null;
    model?: string | null;
    tools?: ToolDefinition[] | null;
}

// @public
export interface CreateRunRequestOptions extends OperationOptions {
}

// @public
export interface CreateThreadAndRunOptions extends OperationOptions {
}

// @public
export interface CreateThreadOptions extends OperationOptions {
}

// @public
export interface DeleteAssistantFileOptions extends OperationOptions {
}

// @public
export interface DeleteAssistantOptions extends OperationOptions {
}

// @public
export interface DeleteFileOptions extends OperationOptions {
}

// @public
export interface DeleteThreadOptions extends OperationOptions {
}

// @public
export interface DeletionStatus {
    deleted: boolean;
    id: string;
}

// @public
export interface FileDeletionStatus extends DeletionStatus {
    id: string;
}

// @public
export interface FileListResponse {
    data: InputFile[];
}

// @public
export type FilePurpose = string;

// @public
export interface FunctionDefinition {
    description: string;
    name: string;
    parameters: unknown;
}

// @public
export interface FunctionToolCall {
    function: FunctionToolCallDetails;
    id: string;
    type: "function";
}

// @public
export interface FunctionToolCallDetails {
    arguments: string;
    name: string;
    output: string | null;
}

// @public
export interface FunctionToolDefinition {
    function: FunctionDefinition;
    type: "function";
}

// @public
export interface GetAssistantFileOptions extends OperationOptions {
}

// @public
export interface GetAssistantOptions extends OperationOptions {
}

// @public
export interface GetFileOptions extends OperationOptions {
}

// @public
export interface GetMessageFileOptions extends OperationOptions {
}

// @public
export interface GetMessageOptions extends OperationOptions {
}

// @public
export interface GetRunOptions extends OperationOptions {
}

// @public
export interface GetRunStepOptions extends OperationOptions {
}

// @public
export interface GetThreadOptions extends OperationOptions {
}

// @public
export interface InputFile {
    bytes: number;
    createdAt: Date;
    filename: string;
    id: string;
    purpose: FilePurpose;
}

// @public
export interface ListAssistantFilesOptions extends OperationOptions {
    after?: string;
    before?: string;
    limit?: number;
    order?: ListSortOrder;
}

// @public
export interface ListAssistantsOptions extends OperationOptions {
    after?: string;
    before?: string;
    limit?: number;
    order?: ListSortOrder;
}

// @public
export interface ListFilesOptions extends OperationOptions {
    purpose?: FilePurpose;
}

// @public
export interface ListMessageFilesOptions extends OperationOptions {
    after?: string;
    before?: string;
    limit?: number;
    order?: ListSortOrder;
}

// @public
export interface ListMessagesOptions extends OperationOptions {
    after?: string;
    before?: string;
    limit?: number;
    order?: ListSortOrder;
}

// @public
export interface ListResponseOf<T> {
    data: T[];
    firstId: string;
    hasMore: boolean;
    lastId: string;
}

// @public
export interface ListRunsOptions extends OperationOptions {
    after?: string;
    before?: string;
    limit?: number;
    order?: ListSortOrder;
}

// @public
export interface ListRunStepsOptions extends OperationOptions {
    after?: string;
    before?: string;
    limit?: number;
    order?: ListSortOrder;
}

// @public
export type ListSortOrder = string;

// @public
export type MessageContent = MessageTextContent | MessageImageFileContent;

// @public
export interface MessageFile {
    createdAt: Date;
    id: string;
    messageId: string;
}

// @public
export interface MessageImageFileContent {
    imageFile: MessageImageFileDetails;
    type: "image_file";
}

// @public
export interface MessageImageFileDetails {
    fileId: string;
}

// @public
export interface MessageImageFileIdDetails {
    fileId: string;
}

// @public
export type MessageRole = string;

// @public
export type MessageTextAnnotation = MessageTextFileCitationAnnotation | MessageTextFilePathAnnotation;

// @public
export interface MessageTextContent {
    text: MessageTextDetails;
    type: "text";
}

// @public
export interface MessageTextDetails {
    annotations: MessageTextAnnotation[];
    value: string;
}

// @public
export interface MessageTextFileCitationAnnotation {
    endIndex: number;
    fileCitation: MessageTextFileCitationDetails;
    startIndex: number;
    text: string;
    type: "file_citation";
}

// @public
export interface MessageTextFileCitationDetails {
    fileId: string;
    quote: string;
}

// @public
export interface MessageTextFilePathAnnotation {
    endIndex: number;
    filePath: MessageTextFilePathDetails;
    startIndex: number;
    text: string;
    type: "file_path";
}

// @public
export interface MessageTextFilePathDetails {
    fileId: string;
}

// @public
export interface RequiredAction {
    submitToolOutputs?: SubmitToolOutputsDetails;
    type: string;
}

// @public
export interface RequiredFunctionToolCall {
    function: FunctionToolCallDetails;
    id: string;
    type: "function";
}

// @public
export type RequiredToolCall = RequiredFunctionToolCall;

// @public
export interface RetrievalToolCall {
    id: string;
    retrieval: Record<string, string>;
    type: "retrieval";
}

// @public
export interface RetrievalToolDefinition {
    type: "retrieval";
}

// @public
export interface RunError {
    code: string;
    message: string;
}

// @public
export type RunStatus = string;

// @public
export interface RunStep {
    assistantId: string;
    cancelledAt: Date | null;
    completedAt: Date | null;
    createdAt: Date;
    expiredAt: Date | null;
    failedAt: Date | null;
    id: string;
    lastError: RunStepError | null;
    metadata?: Record<string, string> | null;
    runId: string;
    status: RunStepStatus;
    stepDetails: RunStepDetails;
    threadId: string;
    type: RunStepType;
}

// @public
export type RunStepDetails = RunStepMessageCreationDetails | RunStepToolCallDetails;

// @public
export interface RunStepError {
    code: RunStepErrorCode;
    message: string;
}

// @public
export interface RunStepError {
    code: RunStepErrorCode;
    message: string;
}

// @public
export type RunStepErrorCode = string;

// @public
export interface RunStepMessageCreationDetails {
    messageCreation: RunStepMessageCreationReference;
    type: "message_creation";
}

// @public
export interface RunStepMessageCreationReference {
    messageId: string;
}

// @public
export type RunStepStatus = string;

// @public
export interface RunStepToolCallDetails {
    toolCalls: ToolCall[];
    type: "tool_calls";
}

// @public
export type RunStepType = string;

// @public
export interface SubmitToolOutputsDetails {
    toolCalls: RequiredToolCall[];
}

// @public
export interface SubmitToolOutputsToRunOptions extends OperationOptions {
}

// @public
export interface ThreadDeletionStatus extends DeletionStatus {
}

// @public
export interface ThreadInitializationMessage {
    content: string;
    fileIds?: string[];
    metadata: Record<string, string> | null;
    role: MessageRole;
}

// @public
export interface ThreadMessage {
    assistantId?: string;
    content: MessageContent[];
    createdAt?: Date;
    fileIds?: string[];
    id?: string;
    metadata: Record<string, string> | null;
    role: string;
    runId?: string;
    threadId?: string;
}

// @public
export interface ThreadRun {
    assistantId: string;
    cancelledAt: Date | null;
    completedAt: Date | null;
    createdAt: Date;
    expiresAt: Date | null;
    failedAt: Date | null;
    fileIds: string[];
    id: string;
    instructions: string;
    lastError?: RunError | null;
    metadata?: Record<string, string> | null;
    model: string;
    requiredAction?: RequiredAction | null;
    startedAt: Date | null;
    status: RunStatus;
    threadId: string;
    tools: ToolDefinition[];
}

// @public
export type ToolCall = CodeInterpreterToolCall | RetrievalToolCall | FunctionToolCall;

// @public
export type ToolDefinition = CodeInterpreterToolDefinition | RetrievalToolDefinition | FunctionToolDefinition;

// @public
export interface ToolOutput {
    output?: string;
    toolCallId?: string;
}

// @public
export interface UpdateAssistantOptions {
    description?: string | null;
    fileIds?: string[];
    instructions?: string | null;
    metadata?: Record<string, string> | null;
    model?: string;
    name?: string | null;
    tools?: ToolDefinition[];
}

// @public
export interface UpdateAssistantRequestOptions extends OperationOptions {
}

// @public
export interface UpdateMessageOptions extends OperationOptions {
    metadata?: Record<string, string>;
}

// @public
export interface UpdateRunOptions extends OperationOptions {
    metadata?: Record<string, string>;
}

// @public
export interface UpdateThreadOptions extends OperationOptions {
    metadata?: Record<string, string>;
}

// @public
export interface UploadFileOptions extends OperationOptions {
    contentType?: string;
    filename?: string;
}

// (No @packageDocumentation comment for this package)

```
