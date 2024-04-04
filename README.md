 import phonenumbers
from phonenumbers import geocoder

def track_location(phone_number):
    try:
        # Parse phone number
        parsed_number = phonenumbers.parse(phone_number, None)

        # Check if the phone number is valid
        if not phonenumbers.is_valid_number(parsed_number):
            return "Invalid phone number"

        # Get location information
        location = geocoder.description_for_number(parsed_number, "en")
        return f"Location: {location}"
    except Exception as e:
        return f"Error: {str(e)}"

# Example phone number
phone_number = "+1234567890"  # Replace with the phone number you want to track

# Track location
location_info = track_location(phone_number)
print(location_info)
