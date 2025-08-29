# BFHL REST API

A REST API built with Node.js and Express that processes arrays and returns categorized data.

## Features

- Separates numbers into odd and even arrays
- Extracts and uppercases alphabets
- Identifies special characters
- Calculates sum of numbers
- Creates concatenated string with alternating caps in reverse order

## API Endpoints

### POST /bfhl
Processes an array and returns categorized data.

**Request Body:**
```json
{
  "data": ["a", "1", "334", "4", "R", "$"]
}
```

**Response:**
```json
{
  "is_success": true,
  "user_id": "john_doe_17091999",
  "email": "john@xyz.com",
  "roll_number": "ABCD123",
  "odd_numbers": ["1"],
  "even_numbers": ["334", "4"],
  "alphabets": ["A", "R"],
  "special_characters": ["$"],
  "sum": "339",
  "concat_string": "Ra"
}
```

### GET /bfhl
Returns operation code for testing.

## Local Development

1. Clone the repository:
```bash
git clone <your-repo-url>
cd bfhl-api
```

2. Install dependencies:
```bash
npm install
```

3. Start the development server:
```bash
npm run dev
```

4. Test the API:
```bash
curl -X POST http://localhost:3000/bfhl \
  -H "Content-Type: application/json" \
  -d '{"data": ["a","1","334","4","R", "$"]}'
```

## Deployment

### Vercel Deployment

1. Install Vercel CLI:
```bash
npm i -g vercel
```

2. Deploy:
```bash
vercel
```

3. Follow the prompts and your API will be deployed.

## Important Notes

- Update the `user_id`, `email`, and `roll_number` in server.js with your actual details
- The `user_id` format should be: `{full_name_ddmmyyyy}` (lowercase)
- All numbers are returned as strings
- Special characters include any non-alphanumeric characters

## Example Usage

Test with different inputs:

```bash
# Example A
curl -X POST https://your-vercel-url.vercel.app/bfhl \
  -H "Content-Type: application/json" \
  -d '{"data": ["a","1","334","4","R", "$"]}'

# Example B  
curl -X POST https://your-vercel-url.vercel.app/bfhl \
  -H "Content-Type: application/json" \
  -d '{"data": ["2","a", "y", "4", "&", "-", "*", "5","92","b"]}'

# Example C
curl -X POST https://your-vercel-url.vercel.app/bfhl \
  -H "Content-Type: application/json" \
  -d '{"data": ["A","ABcD","DOE"]}'
```