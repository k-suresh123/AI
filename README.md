https://github.com/leonvanzyl/langchain-js/blob/lesson-2/prompt-template.js
prompt template: 

// Instantiate the model
const model = new ChatOpenAI({
  modelName: "gpt-3.5-turbo",
  temperature: 0.9,
});

// Create Prompt Template from fromMessages

const prompt = ChatPromptTemplate.fromMessages([
  [
    "You are a talented chef.  Create a recipe based on a main ingredient provided by the user.",
  ],
  ["human", "{word}"],
]);

const chain = prompt.pipe(model);

const response = await chain.invoke({
  word: "dog",
});

console.log(response);
