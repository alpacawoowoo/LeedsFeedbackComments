import requests
from bs4 import BeautifulSoup

def get_planning_comments(url):
    # Send a GET request to the URL
    response = requests.get(url)
    
    # Check if the request was successful
    if response.status_code != 200:
        raise Exception(f"Failed to load page {url}")
    
    # Parse the HTML content
    soup = BeautifulSoup(response.content, 'html.parser')
    
    # Assuming comments are in <div> tags with class "comment"
    comments = soup.find_all('div', class_='comment')
    
    # Extract text from each comment
    comments_text = [comment.get_text(strip=True) for comment in comments]
    
    return comments_text

# Example usage
if __name__ == "__main__":
    url = "https://example.com/planning-comments"
    comments = get_planning_comments(url)
    for idx, comment in enumerate(comments, start=1):
        print(f"Comment {idx}: {comment}")
