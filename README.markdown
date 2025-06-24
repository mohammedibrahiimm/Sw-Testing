# Search Functionality Test Cases

This repository contains a comprehensive set of test cases designed to validate the search functionality of an e-learning platform. The test cases cover various search scenarios, including valid and invalid inputs, equivalence partitioning, and boundary value analysis (BVA). These test cases ensure robust testing of category, subcategory, popular topic, instructor, and course searches, including edge cases and error handling.

## Purpose

The purpose of these test cases is to:
- Verify that the search feature correctly handles valid inputs across different languages, partial matches, and case-insensitive queries.
- Ensure the system gracefully handles invalid inputs, such as empty searches, overly long inputs, and malicious attempts (e.g., SQL/XSS injection).
- Validate input boundaries and equivalence classes to confirm consistent behavior across different input lengths and formats.

## Test Case Categories

### 1. Valid Search Scenarios
These test cases verify that the search functionality returns expected results for valid inputs.

1. **Category Search via Explore**  
   - Example: Search for "development", "IT & software", "design".
2. **Subcategory Search via Explore**  
   - Example: Search for "web development" (under development), "hardware" (under IT & software), "game design" (under design).
3. **Popular Topic Search via Explore**  
   - Example: Search for "CSS" (under web development), "PLC" (under hardware), "Unity" (under game design).
4. **Category Search via Search Bar**  
   - Example: Search for "development", "IT & software", "design".
5. **Subcategory Search via Search Bar**  
   - Example: Search for "web development", "hardware", "game design".
6. **Popular Topic Search via Search Bar**  
   - Example: Search for "CSS", "PLC", "Unity".
7. **Category Search with Spelling Mistakes**  
   - Example: Search for "develobment", "sofware", "desin".
8. **Subcategory Search with Spelling Mistakes**  
   - Example: Search for "web develobment", "hadware", "gme design".
9. **Popular Topic Search with Spelling Mistakes**  
   - Example: Search for "Uniti".
10. **Category Search in Other Languages**  
    - Example: Search for "تطوير" (development), "سوفت وير" (software), "تصميم" (design).
11. **Subcategory Search in Other Languages**  
    - Example: Search for "تطوير الويب" (web development), "هاردوير" (hardware), "تصميم الألعاب" (game design).
12. **Popular Topic Search in Other Languages**  
    - Example: Search for "يونتي" (Unity).
13. **Instructor Search**  
    - Example: Search for "Tarek Roshdy".
14. **Instructor Search in Other Languages**  
    - Example: Search for "طارق رشدي".
15. **Specific Section Search**  
    - Example: Search for "Test case writing".
16. **Specific Course Search**  
    - Example: Search for "The Complete 2025 Software Testing Bootcamp".
17. **Specific Course Search with Spelling Mistakes**  
    - Example: Search for "The Comlete 2025 Softwar Tesing Bootcamp".
18. **Search with Minimum Characters**  
    - Example: Search with 1 character (e.g., "a").
19. **Search with Maximum Characters**  
    - Example: Search with 256 characters.
20. **Partial Keyword Match (Category)**  
    - Example: Search for "dev" (matches "development").
21. **Partial Keyword Match (Popular Topics)**  
    - Example: Search for "c+" (matches "C++").
22. **Case-Insensitive Search**  
    - Example: Search for "JaVaScRiPt" (matches "JavaScript").
23. **Search with Special Characters**  
    - Example: Search for "C++".
24. **Search with Numeric Keywords**  
    - Example: Search for "Excel 2019".

### 2. Invalid Search Scenarios
These test cases verify that the system appropriately handles invalid inputs.

1. **Empty Search Bar**  
   - Example: Submit a search with no input.
2. **Search Exceeding Maximum Characters**  
   - Example: Search with 257 characters.
3. **Whitespace-Only Search**  
   - Example: Search with only spaces or tabs.
4. **Gibberish Search**  
   - Example: Search for "mohamed1213124123".
5. **SQL/XSS Injection Attempt**  
   - Example: Search for "drop table" or "<script>alert('xss')</script>".

### 3. Equivalence Partitioning
These test cases group inputs into partitions to validate behavior within and outside valid ranges.

1. **Instructor Name**  
   - 0 characters (invalid).  
   - 51 characters (invalid).  
   - 25 characters (valid).
2. **Category**  
   - 0 characters (invalid).  
   - 51 characters (invalid).  
   - 25 characters (valid).
3. **Subcategory**  
   - 0 characters (invalid).  
   - 51 characters (invalid).  
   - 25 characters (valid).
4. **Course Name**  
   - 0 characters (invalid).  
   - 257 characters (invalid).  
   - 128 characters (valid).

### 4. Boundary Value Analysis (BVA)
These test cases focus on the boundaries of input ranges to identify edge-case issues.

1. **Instructor Name**  
   - 0 characters (invalid).  
   - 1 character (valid).  
   - 50 characters (valid).  
   - 51 characters (invalid).
2. **Category**  
   - 0 characters (invalid).  
   - 1 character (valid).  
   - 50 characters (valid).  
   - 51 characters (invalid).
3. **Subcategory**  
   - 0 characters (invalid).  
   - 1 character (valid).  
   - 50 characters (valid).  
   - 51 characters (invalid).
4. **Course Name**  
   - 0 characters (invalid).  
   - 1 character (valid).  
   - 256 characters (valid).  
   - 257 characters (invalid).
