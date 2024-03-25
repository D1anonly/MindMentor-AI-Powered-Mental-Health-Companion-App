# MindMentor-AI-Powered-Mental-Health-Companion-App
MindMentor uses generative AI and natural language processing to provide personalized mental health support, offering coping strategies and resources based on users' needs.
import random

# Mock database of resources and coping strategies
resources = {
    "stress": ["Take deep breaths", "Try to take a short walk"],
    "anxiety": ["Practice mindfulness meditation", "Write down your thoughts"],
    "depression": ["Reach out to a friend or family member", "Focus on small, achievable goals"],
    "general": ["Visit a mental health professional", "Consider joining a support group"]
}

def understand_query(query):
    """
    Simplified function to categorize the user's query.
    This is a placeholder for more complex NLP processes.
    """
    query = query.lower()
    if "stress" in query:
        return "stress"
    elif "anxiety" in query or "nervous" in query:
        return "anxiety"
    elif "sad" in query or "depression" in query:
        return "depression"
    else:
        return "general"

def generate_response(category):
    """
    Generates a response based on the identified category of the query.
    """
    if category in resources:
        suggestion = random.choice(resources[category])
        response = f"Feeling {category}? Here's something you might try: {suggestion}."
    else:
        response = "I'm here to help. Could you tell me a bit more about how you're feeling?"
    return response

def mindmentor_chatbot(user_input):
    """
    Main function to simulate interaction with the MindMentor app.
    """
    category = understand_query(user_input)
    response = generate_response(category)
    return response

# Example usage
user_input = "I'm feeling really stressed about work."
print(mindmentor_chatbot(user_input))
