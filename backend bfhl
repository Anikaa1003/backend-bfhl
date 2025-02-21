from flask import Flask, request, jsonify
import re

app = Flask(__name__)

@app.route("/bfhl", methods=["POST"])
def process_data():
    try:
        data = request.get_json()
        if not data or "data" not in data:
            return jsonify({"is_success": False, "error": "Invalid input"}), 400

        input_array = data["data"]
        numbers = [x for x in input_array if x.isdigit()]
        alphabets = [x for x in input_array if x.isalpha()]
        highest_alphabet = [max(alphabets, key=str.lower)] if alphabets else []

        response = {
            "is_success": True,
            "user_id": "john_doe_17091999",
            "email": "john@xyz.com",
            "roll_number": "ABCD123",
            "numbers": numbers,
            "alphabets": alphabets,
            "highest_alphabet": highest_alphabet
        }
        return jsonify(response), 200
    
    except Exception as e:
        return jsonify({"is_success": False, "error": str(e)}), 500

@app.route("/bfhl", methods=["GET"])
def get_operation_code():
    return jsonify({"operation_code": 1}), 200

if __name__ == "__main__":
    app.run(debug=True)
