# CodeAlpha-
import random

def generate_phishing_email():
    sender = "legitimate@example.com"
    subject = "Important Account Update"
    body = "Dear Customer,\n\nPlease update your account information by clicking the link below:\n\n" \
           "http://malicious-website.com/update-account\n\nThank you,\nLegitimate Bank"

    return {"sender": sender, "subject": subject, "body": body}

def user_identifies_phishing(email):
    # Simulate user awareness by checking for common signs of phishing
    if "http://malicious-website.com" in email["body"] and "Dear Customer" in email["body"]:
        return False
    else:
        return True

def main():
    phishing_email = generate_phishing_email()

    print("You received an email:")
    print("From:", phishing_email["sender"])
    print("Subject:", phishing_email["subject"])
    print("Body:", phishing_email["body"])

    user_response = input("\nDo you think this is a phishing email? (yes/no): ").lower()

    if user_response == "yes" and user_identifies_phishing(phishing_email):
        print("\nCongratulations! You correctly identified the phishing email.")
    elif user_response == "no" and not user_identifies_phishing(phishing_email):
        print("\nCongratulations! You correctly recognized the legitimate email.")
    else:
        print("\nOops! It seems there might be a misunderstanding.")

if __name__ == "__main__":
    main()
    
