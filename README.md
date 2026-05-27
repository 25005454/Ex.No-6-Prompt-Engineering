Ex.No.6 Development of Python Code Compatible with Multiple AI Tools

Aim: 

Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights with Multiple AI Tools.

Explanation:

Develop a python code that integrates multiple AI tool by interacting with their APIs.
Compare outputs from different APIs.
Analyze the response and the Output.

The aim is to understand how to request help from AI tools for tasks like writing Python code, integrating with APIs, comparing outputs, and generating actionable insights.

program :
```

import requests

# Example: Integrating with two AI APIs (Tool A and Tool B)
# Replace with actual API endpoints and keys

API_A_URL = "https://api.toolA.com/v1/generate"
API_B_URL = "https://api.toolB.com/v1/generate"

API_A_KEY = "your_api_key_A"
API_B_KEY = "your_api_key_B"

def call_api_a(prompt):
    response = requests.post(
        API_A_URL,
        headers={"Authorization": f"Bearer {API_A_KEY}"},
        json={"prompt": prompt}
    )
    return response.json().get("output", "")

def call_api_b(prompt):
    response = requests.post(
        API_B_URL,
        headers={"Authorization": f"Bearer {API_B_KEY}"},
        json={"prompt": prompt}
    )
    return response.json().get("output", "")

def compare_outputs(output_a, output_b):
    """Simple comparison logic: length, keywords, and differences"""
    insights = {
        "length_A": len(output_a),
 "length_B": len(output_b),
        "common_words": set(output_a.split()) & set(output_b.split()),
        "unique_to_A": set(output_a.split()) - set(output_b.split()),
        "unique_to_B": set(output_b.split()) - set(output_a.split())
    }
    return insights

def main():
    prompt = "Explain the importance of AI in healthcare."
    
    # Call both APIs
    output_a = call_api_a(prompt)
    output_b = call_api_b(prompt)
    
    print("=== Output from Tool A ===")
    print(output_a)
    print("\n=== Output from Tool B ===")
    print(output_b)
    
    # Compare outputs
    insights = compare_outputs(output_a, output_b)
    print("\n=== Comparative Insights ===")
    for key, value in insights.items():
        print(f"{key}: {value}")

if __name__ == "__main__":
    main()
```
* Explanation :
- API Integration: The code connects to two different AI tools using their REST APIs.
- Prompt Handling: A single prompt is sent to both tools.
- Output Comparison: The results are compared based on:
- Length of responses
- Common words
- Unique words in each output
- Actionable Insights: The comparison highlights differences and overlaps, helping decide which tool provides more relevant or richer information.

* Result :
When executed, the program will:
- Generate responses from multiple AI tools.
- Display outputs side by side.
- Provide comparative insights (e.g., which tool is more detailed, unique perspectives).
This approach can be extended to:
- Sentiment analysis of outputs
-  Ranking tools based on accuracy or relevance
- Automating decision-making pipelines




