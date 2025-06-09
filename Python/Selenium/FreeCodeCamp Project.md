
# Selenium Python Project Notes

## File Structure

```
booking_project/
├── booking.py          # Main automation logic
├── run.py              # Execution script
└── booking_filteration.py  # Filter handling
```
---

## 1. booking.py (Core Automation Class)

### Class Initialization
```python
class Booking(webdriver.Chrome):
    def __init__(self, driver_path, teardown=False):
        # Chrome options to suppress warnings
        options = webdriver.ChromeOptions()
        options.add_experimental_option('excludeSwitches', ['enable-logging'])
        
        # Driver setup
        super().__init__(options=options)
        self.implicitly_wait(15)  # Global wait
        self.maximize_window()
```
- **Key Features**: Inherits from Chrome WebDriver, sets implicit wait, maximizes window

---

### Core Methods

#### 1. `land_first_page()`
```python
def land_first_page(self):
    self.get(const.BASE_URL)  # Opens booking.com
```
- **Purpose**: Initial navigation to booking.com

#### 2. `change_currency()`
```python
def change_currency(self, currency):
    # Finds and clicks currency selector
    self.find_element(By.CSS_SELECTOR,'button[data-testid="header-currency-picker-trigger"]').click()
    
    # Selects specific currency (e.g., USD)
    self.find_element(By.XPATH,f"//button[contains(., '{currency}')]").click()
```
- **Key Elements**: Uses CSS selector and XPath with dynamic currency input

#### 3. `select_place_to_go()`
```python
def select_place_to_go(self, place: str):
    search_field = self.find_element(By.NAME, 'ss')
    search_field.clear()
    search_field.send_keys(place)
    sleep(3)  # Wait for autocomplete
    self.find_element(By.ID, "autocomplete-result-0").click()
```
- **Flow**: Inputs location > waits for suggestions > selects first result

#### 4. `select_date()`
```python
def select_date(self, check_in, check_out):
    # Converts string dates to datetime objects
    # Calculates required month navigation clicks
    # Clicks next-month button X times
    # Selects date elements using CSS attribute selectors
```
- **Key Logic**: Dynamically navigates calendar based on current date vs target date

#### 5. `select_travellers()`
```python
def select_travellers(self, adults, pets=False, rooms=None, *children):
    # Complex logic to:
    - Adjust adult count (+/- buttons)
    - Add children with specific ages
    - Select rooms
    - Toggle pets checkbox
```
- **UI Pattern**: Uses repeated clicks on +/- buttons to adjust values

#### 6. `apply_filterations()`
```python
def apply_filterations(self, *preferred_stars):
    # Delegates to BookingFilteration class
    filteration = BookingFilteration(self)
    filteration.apply_star_rating(preferred_stars)
    filteration.sort_byprice_lowestfirst()
```
- **Separation of Concerns**: Filter logic moved to separate class

---

## 2. booking_filteration.py (Filter Logic)

### Class Structure
```python
class BookingFilteration:
    def __init__(self, driver: WebDriver):
        self.driver = driver  # Receives driver from main class

    def apply_star_rating(self, star_values):
        # Clicks star rating checkboxes (3,4,5 stars)
        for value in star_values:
            self.driver.find_element(
                By.CSS_SELECTOR, 
                f"div[data-filters-item='class:class={value}']"
            ).click()

    def sort_byprice_lowestfirst(self):
        # Opens sort dropdown > selects "Price (lowest first)"
        self.driver.find_element(By.CSS_SELECTOR,'button[class="a83ed08757 faefc93c6f"]').click()
        self.driver.find_element(By.CSS_SELECTOR,'button[data-id="price"]').click()
```

---

## 3. run.py (Execution Script)

### Workflow
```python
try:
    bot = Booking()  # Initializes driver
    bot.land_first_page()  # Opens booking.com
    bot.change_currency("USD")  # Sets currency
    bot.select_place_to_go("California")  # Location input
    bot.select_date("2025-05-10", "2025-05-13")  # Date selection
    bot.select_travellers(2, True, 2, 11, 15)  # 2 adults, 2 rooms, 2 children (11 & 15)
    bot.apply_filterations(3,4,5)  # 3-5 star hotels
    print(bot.report_results())  # Returns number of hotels found
```
- **Parameters Explained**:
  - `select_travellers(adults, pets, rooms, *children_ages)`
  - `apply_filterations(*star_ratings)`

---

## Key Selenium Patterns Used

1. **Locator Strategies**:
   - Preferred: `By.CSS_SELECTOR` (most)
   - Fallback: `By.XPATH` for text matches (`contains(., 'text')`)
   - Special Case: `By.ID` for unique elements

2. **Wait Strategies**:
   - Implicit Wait: `self.implicitly_wait(15)`
   - Hardcoded Wait: `sleep(3)` (not recommended for production)

3. **Page Object Model**:
   - `Booking` class handles main page
   - `BookingFilteration` handles results page

4. **Date Handling**:
   - Uses `datetime` module for date math
   - CSS attribute selector: `span[data-date="2025-05-10"]`

---

## Common Anti-Patterns to Improve

1. **Avoid Hardcoded Sleeps**
   - Replace `sleep(3)` with explicit waits

2. **Magic Numbers**
   - `add_buttons[0]` → Create named constants

3. **Fragile Selectors**
   - Class names like `"a83ed08757..."` may change. Prefer `data-testid` attributes.

---

## Quick Revision Cheatsheet

| Action              | Method Used              | Locator Type           |
| ------------------- | ------------------------ | ---------------------- |
| Find element        | `find_element()`         | CSS/XPath/ID           |
| Click element       | `.click()`               | Any                    |
| Input text          | `.send_keys()`           | Text fields            |
| Dropdown selection  | `Select()` class         | Visible text/value     |
| Calendar navigation | Next-month button clicks | CSS selector           |
| Filter activation   | Checkbox clicks          | CSS attribute selector |
