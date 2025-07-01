[Text Generation](https://cloud.google.com/vertex-ai/generative-ai/docs/multimodal/send-chat-prompts-gemini#system-instructions)
[System Instructions](https://cloud.google.com/vertex-ai/generative-ai/docs/learn/prompts/system-instructions)

## Prompt engineering best practices

Prompt engineering is all about how to design your prompts so that the response is what you were indeed hoping to see.

The idea of using "unfancy" prompts is to minimize the noise in your prompt to reduce the possibility of the LLM misinterpreting the intent of the prompt. Below are a few guidelines on how to engineer "unfancy" prompts.

In this section, you'll cover the following best practices when engineering prompts:

* Be concise
* Be specific, and well-defined
* Ask one task at a time
* Improve response quality by including examples
* Turn generative tasks to classification tasks to improve safety

### Be concise

🛑 Not recommended. The prompt below is unnecessarily verbose.


```python
prompt = "What do you think could be a good name for a flower shop that specializes in selling bouquets of dried flowers more than fresh flowers?"

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```

#### Response
Okay, here are some name ideas for a dried flower shop, categorized for different vibes:

**Elegant & Sophisticated:**

*   **The Everbloom Atelier:** (Atelier suggests artistry and craftsmanship)
*   **Preserved Petals:** Simple, descriptive, and elegant.
*   **La Fleur Éternelle:** (French for "The Eternal Flower") - Adds a touch of romance.
*   **Golden Harvest Florals:** Evokes a sense of abundance and natural beauty.
*   **The Still Life Bouquet:**  Connects to the artistic tradition of still life paintings.
*   **Timeless Blooms:** Emphasizes the lasting quality of dried flowers.

**Rustic & Natural:**

*   **The Dried Meadow:** Simple, evocative of a natural setting.
*   **Wildflower Wisp:** Suggests delicate and natural beauty.
*   **The Gathered Stem:** Implies a curated and natural collection.
*   **Sunbaked Blooms:** Evokes the process of drying flowers.
*   **The Prairie Posy:** Rustic and charming.
*   **Fields of Forever:** Captures the essence of dried flowers lasting long.

**Modern & Minimalist:**

*   **Dried & Co.** Simple, modern, and versatile.
*   **The Flora Archive:** Suggests a curated collection of preserved flowers.
*   **Still Life Studio:** Modern and artistic.
*   **Eternal Flora:** Concise and impactful.
*   **Dry Bloom:** Short, sweet, and to the point.
*   **The Sustainable Stem:** Highlights the eco-friendly aspect of dried flowers.

**Whimsical & Playful:**

*   **The Petal Potpourri:**  Playful and descriptive.
*   **Bloom & Brush:** Suggests creativity and artistry.
*   **The Forever Flower:** Simple and memorable.
*   **The Happy Herbarium:**  Whimsical and a bit scientific.
*   **Dried Delights:** Focuses on the joy and beauty of dried flowers.
*   **The Seed & Story:** Implies that each flower has a unique tale to tell.

**Tips for Choosing:**

*   **Consider your target audience:**  Are you aiming for a high-end clientele or a more casual customer base?
*   **Check for availability:**  Make sure the name isn't already in use in your area and that you can secure a domain name and social media handles.
*   **Say it out loud:**  Make sure the name is easy to pronounce and remember.
*   **Get feedback:**  Ask friends, family, and potential customers what they think of your favorite names.
*   **Think about your brand:**  Does the name reflect the overall style and aesthetic of your shop?
*   **Think about SEO**: Consider adding words like "dried flowers", "dried bouquets" to help people find your business online if you are looking to have a website.

Good luck with your flower shop!

###

✅ Recommended. The prompt below is to the point and concise.


```python
prompt = "Suggest a name for a flower shop that sells bouquets of dried flowers"

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```
#### Response

Okay, here are some name suggestions for a dried flower shop, playing with different angles like rustic, modern, romantic, and descriptive:

**Rustic & Earthy:**

*   The Dried Stem
*   Everbloom & Co.
*   The Wildflower Keepsake
*   Harvest Hues
*   Rustic Petals
*   The Preserved Bloom
*   Golden Reeds & Co.

**Modern & Chic:**

*   Still Life Florals
*   Dried & Dusted
*   The Everlasting Edit
*   Botanical Remains
*   Eternal Bloom
*   Dried Studio

**Romantic & Whimsical:**

*   Whispers of Bloom
*   The Timeless Bouquet
*   Forever Floral
*   Dried Romance
*   The Petaled Past
*   Amber & Bloom

**Descriptive & Straightforward:**

*   The Dried Flower Shop
*   Preserved Petals
*   Dried Floral Arrangements
*   Lasting Blooms
*   The Bouquet Keeper

**Bonus - Unique & Playful:**

*   Petrified Petals (a little edgy)
*   The Bone Yard Blooms

**Tips for Choosing:**

*   **Consider your target audience:** Are you aiming for a high-end clientele or a more casual market?
*   **Check for availability:** Make sure the name isn't already in use in your area or online.  Do a trademark search.
*   **Say it out loud:** Does it sound good? Is it easy to remember and pronounce?
*   **Think about your branding:** Does the name fit with the overall aesthetic you want to create?

I hope this gives you a good starting point! Good luck!



### Be specific, and well-defined

Suppose that you want to brainstorm creative ways to describe Earth.

🛑 The prompt below might be a bit too generic (which is certainly OK if you'd like to ask a generic question!)


```python
prompt = "Tell me about Earth"

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```

#### Response
Okay, let's delve into the wonders of Earth! Here's a rundown of key aspects of our home planet:

**Basics:**

*   **Name:** Earth (also sometimes referred to as Terra)
*   **Planet Type:** Terrestrial (rocky)
*   **Position in Solar System:** Third planet from the Sun
*   **Orbit:** Nearly circular, elliptical orbit. The average distance from the Sun is about 150 million kilometers (93 million miles), which is defined as one astronomical unit (AU).
*   **Diameter:** Approximately 12,742 kilometers (7,918 miles)
*   **Mass:** About 5.97 x 10^24 kilograms
*   **Rotation Period (Day):** About 23 hours, 56 minutes, and 4 seconds (sidereal day - relative to stars). A solar day (time from noon to noon) is about 24 hours.
*   **Revolution Period (Year):** About 365.25 days (this is why we have leap years)
*   **Atmosphere:** Primarily nitrogen (about 78%) and oxygen (about 21%), with smaller amounts of argon, carbon dioxide, and trace gases. The atmosphere protects us from harmful radiation and helps regulate temperature.
*   **Surface:** About 71% covered by water (oceans, seas, lakes, rivers, ice), and 29% land (continents, islands).
*   **Moon(s):** One natural satellite, the Moon (Luna).
*   **Rings:** No planetary rings.

**Internal Structure:**

Earth has a layered structure:

*   **Inner Core:** Solid iron and nickel, under immense pressure and heat.
*   **Outer Core:** Liquid iron and nickel; generates Earth's magnetic field.
*   **Mantle:** Thickest layer; mostly solid rock, but capable of slow flow over geological timescales (convection).
*   **Crust:** Thin, outermost layer; divided into oceanic crust (thinner, denser) and continental crust (thicker, less dense).

**Key Features & Processes:**

*   **Plate Tectonics:** Earth's crust is divided into plates that move and interact, causing earthquakes, volcanoes, mountain formation, and the creation of new land.
*   **Magnetic Field:** Generated by the movement of liquid iron in the outer core. It shields Earth from harmful solar wind.
*   **Water Cycle:** Continuous movement of water between the oceans, atmosphere, and land through evaporation, condensation, precipitation, and runoff.
*   **Seasons:** Caused by the tilt of Earth's axis of rotation relative to its orbit around the Sun. Different parts of the Earth receive more direct sunlight at different times of the year.
*   **Climate:** The long-term average weather patterns in a region. Earth's climate is influenced by many factors, including solar radiation, atmospheric composition, ocean currents, and land surface features.
*   **Life:** The only known planet to harbor life. A vast diversity of organisms exists in various ecosystems.

**Why is Earth Habitable?**

Several factors contribute to Earth's unique habitability:

*   **Distance from the Sun:** Just the right distance for liquid water to exist on the surface. Too close, and water would evaporate; too far, and it would freeze.
*   **Atmosphere:** Provides a protective shield from harmful radiation and maintains a relatively stable temperature.
*   **Water:** Essential for all known life.
*   **Magnetic Field:** Protects life from harmful solar wind.
*   **Plate Tectonics:** Helps regulate the carbon cycle and maintain a stable climate over long periods.

**Earth's Moon (Luna):**

*   Relatively large moon compared to Earth.
*   Influences tides.
*   Stabilizes Earth's axial tilt, which helps maintain relatively stable seasons.
*   Has a significant impact on the earth by creating tides.

**Interesting Facts:**

*   Earth is not perfectly round; it's slightly flattened at the poles and bulges at the equator (an oblate spheroid).
*   The highest point on Earth is Mount Everest (in the Himalayas).
*   The lowest point on land is the shore of the Dead Sea.
*   The deepest point in the ocean is the Mariana Trench.
*   Earth is estimated to be about 4.54 billion years old.
*   The greenhouse effect is a natural process that helps keep Earth warm enough to support life.

**Human Impact:**

*   Humans have significantly altered Earth's environment through activities such as deforestation, pollution, and the burning of fossil fuels.
*   Climate change, driven by human emissions of greenhouse gases, is a major threat to Earth's ecosystems and human societies.

**In Summary:**

Earth is a dynamic and complex planet with a unique combination of factors that make it habitable for life. It is essential to understand Earth's systems and processes in order to protect our planet and ensure a sustainable future.

I can provide more information on specific aspects you're interested in.  Just let me know what you'd like to explore further! For example, are you interested in plate tectonics, Earth's atmosphere, climate change, or the history of life on Earth?
####


✅ Recommended. The prompt below is specific and well-defined.


```python
prompt = "Generate a list of ways that makes Earth unique compared to other planets"

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```
#### Response

Earth is truly unique in our solar system, and possibly in the universe as we know it. Here's a list of ways that Earth stands out:

**Essential for Life as We Know It:**

*   **Liquid Water on the Surface:** This is arguably the most critical feature. Liquid water is essential for the type of life we know. While other planets may have water ice or subsurface oceans, Earth is the only known planet with stable liquid water on its surface.
*   **Oxygen-Rich Atmosphere:** Earth's atmosphere is approximately 21% oxygen, a byproduct of photosynthesis. This high concentration of oxygen is crucial for complex life forms that rely on aerobic respiration.
*   **Ozone Layer:** This layer of ozone in the stratosphere absorbs most of the Sun's harmful ultraviolet (UV) radiation, protecting life on the surface.
*   **Stable Temperature Range:** Earth's distance from the Sun and its atmosphere create a relatively stable temperature range that is conducive to liquid water and life.
*   **Presence of Life:**  So far, Earth is the only planet known to harbor life.

**Geological and Physical Characteristics:**

*   **Plate Tectonics:** Earth's lithosphere is divided into plates that move and interact, resulting in phenomena like earthquakes, volcanoes, and mountain building. Plate tectonics are crucial for regulating the planet's temperature, cycling nutrients, and creating diverse habitats.
*   **Strong Magnetic Field:** Generated by the movement of liquid iron in Earth's outer core, the magnetic field deflects harmful solar wind and cosmic radiation, protecting the atmosphere and life on the surface.
*   **Active Volcanism:** Earth has ongoing volcanic activity, which plays a role in releasing gases from the interior, shaping the landscape, and potentially influencing the climate.
*   **Diversity of Ecosystems:** Earth boasts a vast array of ecosystems, from rainforests and deserts to coral reefs and polar ice caps, each supporting unique communities of life.
*   **Significant Size and Mass:** Earth has a specific size and mass that allow it to retain an atmosphere and have sufficient gravity to hold water.
*   **Moon:** Earth's relatively large moon is unique in its size compared to the planet it orbits. The moon stabilizes Earth's axial tilt, which contributes to stable seasons.
*   **Dynamical Atmosphere:** The presence of complex weather patterns, including hurricanes, monsoons, and jet streams, helps to redistribute heat around the planet.

**Astrobiological Significance:**

*   **Biosphere:** Earth has a biosphere, which is the totality of all living organisms and their interactions with the environment. This complex system is unique and essential for maintaining the planet's habitability.
*   **Complex Chemical Composition:** The planet has a great number of complex molecules which have created diverse environments for life.
*   **Evidence of Intelligence:** Earth has humans, who have developed complex technologies, cultures, and civilizations. This is unique and has had a profound impact on the planet.

**Important Considerations:**

*   **Our Limited Understanding:** We've only explored a tiny fraction of the universe. It's possible that other planets with similar or even more unique characteristics exist, but we haven't found them yet.
*   **Definition of "Unique":** What constitutes "unique" can depend on the criteria used. While other planets may have some of these features in isolation, Earth's combination of these characteristics is what makes it so special.

In summary, Earth's combination of liquid water, a breathable atmosphere, a stable temperature, plate tectonics, a strong magnetic field, and, most importantly, life makes it a truly unique and precious planet.



### Ask one task at a time

🛑 Not recommended. The prompt below has two parts to the question that could be asked separately.


```python
prompt = "What's the best method of boiling water and why is the sky blue?"

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```

#### Response
Let's tackle these two very different questions:

**Best Method of Boiling Water**

There isn't a single "best" method, as it depends on your priorities (speed, energy efficiency, safety, convenience, etc.). Here's a breakdown:

*   **Electric Kettle:**
    *   **Pros:** Fastest for small to medium amounts of water, energy-efficient (usually shuts off automatically), safe (usually has automatic shut-off features).
    *   **Cons:** Requires electricity, limited capacity, may not be suitable for large volumes.
    *   **Best for:** Everyday use, quick cups of tea or coffee, most general scenarios.

*   **Stovetop Kettle:**
    *   **Pros:** Relatively fast, can handle larger volumes than electric kettles, doesn't require electricity (if you have a gas stove).
    *   **Cons:** Requires monitoring to prevent boiling dry, can be less energy-efficient than electric kettles, heating element can get hot.
    *   **Best for:** Larger volumes of water, camping (with a portable stove), situations where electricity is limited.

*   **Microwave:**
    *   **Pros:** Convenient, quick for small amounts.
    *   **Cons:** Can be uneven heating (superheating is a risk), water can boil over violently, less energy-efficient.
    *   **Best for:** Very small amounts of water in a pinch, but generally not recommended.

*   **Stovetop Pot:**
    *   **Pros:** Can handle very large volumes, versatile.
    *   **Cons:** Slowest for small amounts, least energy-efficient, requires close monitoring, heating element can get hot.
    *   **Best for:** Making pasta, blanching vegetables, large batches of stock.

**The Bottom Line for Boiling Water:**  For most situations, an **electric kettle** is the best combination of speed, efficiency, and convenience. A **stovetop kettle** is a good alternative for larger volumes or when electricity is unavailable.

**Why is the Sky Blue?**

The sky is blue because of a phenomenon called **Rayleigh scattering**. Here's the explanation:

1.  **Sunlight and Colors:** Sunlight is actually made up of all the colors of the rainbow.

2.  **Entering the Atmosphere:** When sunlight enters the Earth's atmosphere, it collides with tiny air molecules (mostly nitrogen and oxygen).

3.  **Scattering:** This collision causes the sunlight to scatter in different directions.

4.  **Rayleigh Scattering and Wavelength:** Rayleigh scattering is much more effective at scattering shorter wavelengths of light (blue and violet) than longer wavelengths (red and orange). The amount of scattering is inversely proportional to the fourth power of the wavelength, meaning shorter wavelengths are scattered much more.

5.  **Why Not Violet?** Violet is scattered even *more* than blue. However, the sun emits slightly less violet light than blue light, and our eyes are also more sensitive to blue.  Therefore, we perceive the sky as blue.

6. **Sunsets and Sunrises**: When the sun is low on the horizon, sunlight has to travel through more of the atmosphere to reach our eyes. This means that most of the blue light has already been scattered away, leaving the longer wavelengths like red and orange to dominate what we see. This is why sunrises and sunsets are often red or orange.

**In simple terms:** Blue light is scattered more by the air molecules in the atmosphere, making the sky appear blue.

####

✅ Recommended. The prompts below asks one task a time.


```python
prompt = "What's the best method of boiling water?"

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```

#### Response
The "best" method of boiling water depends on your priorities and resources. Here's a breakdown of common methods, along with their pros and cons:

**1. Electric Kettle:**

*   **Pros:**
    *   **Speed:** Typically the fastest way to boil small to medium amounts of water.
    *   **Convenience:** Very easy to use, often with automatic shut-off features.
    *   **Energy Efficiency:** Can be more energy-efficient than other methods for small amounts of water because they heat the water directly.
    *   **Safety:** Many have safety features like auto shut-off and boil-dry protection.
    *   **Precise Temperature Control:** Some models offer temperature control, ideal for brewing different types of tea or coffee.
*   **Cons:**
    *   **Requires Electricity:** Useless without power.
    *   **Capacity Limitations:** Usually smaller capacity than a stovetop pot.
    *   **Cost:** Can be more expensive upfront than a basic stovetop pot.

**2. Stovetop Pot:**

*   **Pros:**
    *   **Versatility:** Can be used with any heat source (gas, electric, induction, wood stove).
    *   **Large Capacity:** Can boil large volumes of water for cooking, canning, etc.
    *   **Affordable:** Basic pots are relatively inexpensive.
    *   **No Electricity Required:** Can be used with gas or wood stoves during power outages.
*   **Cons:**
    *   **Slower than Electric Kettle:** Generally takes longer to boil water.
    *   **Requires More Attention:** Needs to be monitored to prevent boiling dry or overflowing.
    *   **Less Energy Efficient:** More heat loss to the surrounding environment.
    *   **Uneven Heating:** Can have hot spots, especially on electric stovetops.

**3. Microwave Oven:**

*   **Pros:**
    *   **Speed:** Can be faster than stovetop, especially for small amounts of water.
    *   **Convenience:** Easy to use.
*   **Cons:**
    *   **Uneven Heating:** Can lead to superheating (water exceeding boiling point without visibly boiling, then erupting violently when disturbed).  This is a SIGNIFICANT SAFETY HAZARD.
    *   **Not Recommended:** Generally discouraged due to the risk of superheating and explosions.
    *   **Can Ruin Water Quality:**  Some argue that microwaving water can change its taste due to altered molecular structure (this is debatable but worth noting).  Containers can also leach chemicals into the water.
    *   **Not suitable for large volumes:** Only suitable for small amounts of water at a time.

**4. Camping Stove:**

*   **Pros:**
    *   **Portability:** Designed for outdoor use, making it ideal for camping or hiking.
    *   **Fuel Options:** Can use various fuels, such as propane, butane, or white gas.
*   **Cons:**
    *   **Slower than Electric Kettle or Stovetop (Generally):** Boil times can vary depending on the stove and fuel type.
    *   **Less Convenient:** Requires setup and fuel management.
    *   **Can be Unstable:** Need a level surface to prevent tipping.
    *   **More Dangerous:** Requires cautious use to prevent fire hazards.

**5. Solar Cooker:**

*   **Pros:**
    *   **Environmentally Friendly:** Uses solar energy, reducing carbon footprint.
    *   **No Fuel Required:** Saves money on fuel costs.
*   **Cons:**
    *   **Weather Dependent:** Requires direct sunlight to function effectively.
    *   **Slowest Method:** Can take a long time to boil water.
    *   **Limited Availability:** Solar cookers can be bulky and not readily available everywhere.

**In summary:**

*   **For everyday use, speed, and convenience:** **Electric kettle** is generally the best choice.
*   **For versatility and large volumes:** **Stovetop pot** is a good option.
*   **AVOID using a microwave to boil water due to the risk of superheating.**
*   **For outdoor adventures:** **Camping stove** is essential.
*   **For sustainable cooking:** **Solar cooker** is a great option, but only when weather allows.

Choose the method that best suits your needs, considering speed, convenience, energy efficiency, safety, and the amount of water you need to boil. Always prioritize safety, especially when using a microwave or camping stove.


####

```python
prompt = "Why is the sky blue?"

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```

#### Response
The sky is blue because of a phenomenon called **Rayleigh scattering**. Here's a breakdown:

*   **Sunlight is made of all colors:** White light from the sun is actually composed of all the colors of the rainbow (red, orange, yellow, green, blue, indigo, and violet).

*   **Light enters the atmosphere:** When sunlight enters the Earth's atmosphere, it collides with air molecules (mostly nitrogen and oxygen).

*   **Scattering happens:** This collision causes the light to scatter in different directions.

*   **Rayleigh scattering:** The amount of scattering depends on the wavelength (color) of the light. Shorter wavelengths (blue and violet) are scattered *much* more than longer wavelengths (red and orange). This is Rayleigh scattering.

*   **Why blue, not violet?** Violet light is scattered even more than blue light, but there are a couple of reasons why we see a blue sky:
    *   The sun emits less violet light than blue light.
    *   Our eyes are more sensitive to blue than violet.

*   **So, we see blue:** Because blue light is scattered so much more, it's spread all over the sky. When we look up, we see this scattered blue light coming from all directions.

**In simpler terms:**

Imagine throwing a handful of small blue marbles and a handful of larger red marbles at a bumpy surface. The smaller blue marbles are much more likely to bounce off in all directions, while the larger red marbles tend to keep going in their original direction. The air molecules are like the bumpy surface, and the light colors are like the marbles. Blue light bounces around more, so we see a blue sky.

**Why are sunsets red?**

During sunset (or sunrise), the sunlight has to travel through a much longer path in the atmosphere. As a result, most of the blue light is scattered away before it reaches our eyes. The longer wavelengths, like red and orange, are scattered less and can travel through the atmosphere to reach us, giving us the beautiful red and orange hues of the sunset.



### Watch out for hallucinations

Although LLMs have been trained on a large amount of data, they can generate text containing statements not grounded in truth or reality; these responses from the LLM are often referred to as "hallucinations" due to their limited memorization capabilities. Note that simply prompting the LLM to provide a citation isn't a fix to this problem, as there are instances of LLMs providing false or inaccurate citations. Dealing with hallucinations is a fundamental challenge of LLMs and an ongoing research area, so it is important to be cognizant that LLMs may seem to give you confident, correct-sounding statements that are in fact incorrect.

Note that if you intend to use LLMs for the creative use cases, hallucinating could actually be quite useful.

Try the prompt like the one below repeatedly. We set the temperature to `1.0` so that it takes more risks in its choices. It's possible that it may provide an inaccurate, but confident answer.


```python
generation_config = GenerateContentConfig(temperature=1.0)

prompt = "What day is it today?"

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```


Today is Sunday, October 22, 2023.



Since LLMs do not have access to real-time information without further integrations, you may have noticed it hallucinates what day it is today in some of the outputs.

### Using system instructions to guardrail the model from irrelevant responses

How can we attempt to reduce the chances of irrelevant responses and hallucinations?

One way is to provide the LLM with [system instructions](https://cloud.google.com/vertex-ai/generative-ai/docs/multimodal/send-chat-prompts-gemini#system-instructions).

Let's see how system instructions works and how you can use them to reduce hallucinations or irrelevant questions for a travel chatbot.

Suppose we ask a simple question about one of Italy's most famous tourist spots.


```python
generation_config = GenerateContentConfig(temperature=1.0)

chat = client.chats.create(
    model=MODEL_ID,
    config=GenerateContentConfig(
        system_instruction=[
            "Hello! You are an AI chatbot for a travel web site.",
            "Your mission is to provide helpful queries for travelers.",
            "Remember that before you answer a question, you must check to see if it complies with your mission.",
            "If not, you can say, Sorry I can't answer that question.",
        ]
    ),
)

prompt = "What is the best place for sightseeing in Milan, Italy?"

response = chat.send_message(prompt)
display(Markdown(response.text))
```


The Duomo di Milano is a must-see. It is one of the world's largest cathedrals and a stunning example of Gothic architecture. You can go up to the roof for incredible views of the city.


Now let us pretend to be a user asks the chatbot a question that is unrelated to travel.


```python
prompt = "What is the best processor for a gaming pc?"
response = chat.send_message(prompt)
display(Markdown(response.text))
```


Sorry I can't answer that question.


You can see that this way, a guardrail in the prompt prevented the chatbot from veering off course.

### Turn generative tasks into classification tasks to reduce output variability

#### Generative tasks lead to higher output variability

The prompt below results in an open-ended response, useful for brainstorming, but response is highly variable.


```python
prompt = "I'm a high school student. Recommend me a programming activity to improve my skills."

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```

#### Response
Okay, to recommend a programming activity, I need a little more information!  Tell me:

1.  **What languages do you know?** (e.g., Python, JavaScript, Java, C++, etc.)
2.  **What are your current skill levels?** (e.g., Beginner, Intermediate, Advanced.  Also, what topics in that language are you comfortable with, and what are you struggling with?)
3.  **What are your interests?** (e.g., Web development, game development, data science, cybersecurity, etc.)

However, in the meantime, here are a few suggestions catering to different skill levels and interests.  I'll try to make them progressively more challenging:

**Beginner Level (Assuming a basic understanding of at least one language, like Python):**

*   **Text-Based Game:**
    *   **Concept:**  Create a simple adventure game where the user makes choices by typing commands. Think of it like an interactive story.
    *   **Why it's good:**  Great for practicing `if/else` statements, user input, and basic string manipulation.
    *   **Example:** A "choose your own adventure" where the player has to navigate a forest, fight a monster, or solve a puzzle.
    *   **Language:** Python is ideal due to its simplicity.

*   **Simple Calculator:**
    *   **Concept:** Build a calculator that can perform basic arithmetic operations (+, -, *, /).
    *   **Why it's good:**  Reinforces `if/else`, user input, and type conversion (e.g., converting strings to numbers).
    *   **Language:**  Python, Java, or JavaScript are all suitable.

*   **To-Do List App (Console-Based):**
    *   **Concept:** A program that allows you to add tasks, mark them as complete, and list the tasks.
    *   **Why it's good:** Introduces the concept of lists (or arrays) and loops.  Good for practicing organization.
    *   **Language:** Python is excellent.

**Intermediate Level (Comfortable with loops, functions, and basic data structures):**

*   **Web Scraper (Python with Beautiful Soup):**
    *   **Concept:** Write a program to automatically extract information from a website.  For example, get the titles and links of articles from a news website.
    *   **Why it's good:**  Introduces working with external libraries, handling web requests, and parsing HTML.  Excellent for understanding data extraction.
    *   **Language:** Python (with the `requests` and `Beautiful Soup` libraries).

*   **Simple Web App (Python with Flask or JavaScript with Node.js/Express):**
    *   **Concept:** Create a simple website that allows users to input data and see a result.  For example, a unit converter or a basic form.
    *   **Why it's good:**  Introduces web development concepts like HTML, CSS, and server-side programming.
    *   **Language:** Python (with Flask) or JavaScript (with Node.js/Express).

*   **Data Analysis Project (Python with Pandas and Matplotlib):**
    *   **Concept:** Find a dataset online (e.g., on Kaggle or government data portals) and use Python to analyze it.  Calculate statistics, create visualizations, and draw conclusions.
    *   **Why it's good:**  Introduces data science concepts, working with data in tabular format, and creating charts.
    *   **Language:** Python (with the `Pandas` and `Matplotlib` libraries).

*   **More Advanced Game (Pygame or similar):**
    *   **Concept:** Create a simple graphical game, such as a Pong or Space Invaders clone.
    *   **Why it's good:** Introduces graphics programming, event handling, and game logic.
    *   **Language:** Python (with Pygame), or Java, or C++ (with SFML or SDL).

**Advanced Level (Comfortable with object-oriented programming, data structures, and algorithms):**

*   **Implement a Data Structure or Algorithm:**
    *   **Concept:** Choose a data structure (e.g., a binary search tree, a hash table, a graph) or an algorithm (e.g., Dijkstra's algorithm, a sorting algorithm) and implement it from scratch.
    *   **Why it's good:**  Deepens understanding of fundamental computer science concepts.
    *   **Language:** Java, C++, or Python.

*   **Contribute to an Open-Source Project:**
    *   **Concept:** Find an open-source project on GitHub that interests you and contribute code to it.
    *   **Why it's good:**  Provides real-world experience working with a team, using version control (Git), and following coding standards.

*   **Machine Learning Project (Python with Scikit-learn or TensorFlow):**
    *   **Concept:** Build a machine learning model to solve a specific problem, such as image classification or natural language processing.
    *   **Why it's good:** Introduces machine learning concepts and techniques.
    *   **Language:** Python (with `Scikit-learn` or `TensorFlow`).

*   **More Complex Web Application:**
      * **Concept:** A web app with user authentication, database integration, and potentially a more complex front-end (using a JavaScript framework like React, Angular, or Vue.js).
      * **Why it's good:**  Covers a wider range of web development skills.

**General Tips for All Levels:**

*   **Break Down the Problem:**  Don't try to do everything at once.  Divide the project into smaller, more manageable tasks.
*   **Use Version Control (Git):**  Learn to use Git to track your changes and collaborate with others.
*   **Test Your Code:**  Write tests to ensure that your code works correctly.
*   **Google is Your Friend:**  Don't be afraid to search for solutions online.  Learning to find answers is a valuable skill.
*   **Ask for Help:**  If you get stuck, don't hesitate to ask for help from teachers, classmates, or online communities.
*   **Have Fun!**  Choose a project that you find interesting, and you'll be more motivated to learn.

**Please tell me more about your current skills and interests, and I can give you a more tailored recommendation!**



#### Classification tasks reduces output variability

The prompt below results in a choice and may be useful if you want the output to be easier to control.


```python
prompt = """I'm a high school student. Which of these activities do you suggest and why:
a) learn Python
b) learn JavaScript
c) learn Fortran
"""

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```

#### Response
Okay, as a high school student looking to learn a programming language, I highly recommend **a) Learn Python** over JavaScript and Fortran. Here's why:

**Why Python is the Best Choice for You Right Now:**

*   **Beginner-Friendly and Readable:** Python is known for its clear and simple syntax. It reads almost like plain English, making it much easier to grasp the fundamental programming concepts without getting bogged down in complex syntax rules. This allows you to focus on the *logic* of programming rather than memorizing arcane code.

*   **Versatile and Widely Applicable:** Python is used in a huge range of fields, including:
    *   **Web Development (Backend):** While JavaScript is king on the frontend (what you see in the browser), Python is often used on the backend to handle server logic, databases, and APIs.
    *   **Data Science and Machine Learning:** Python is *the* dominant language in data science. Libraries like NumPy, Pandas, Scikit-learn, and TensorFlow make it incredibly powerful for analyzing data, building models, and creating AI applications.  This is a HUGE growth area.
    *   **Scripting and Automation:** Python is great for automating repetitive tasks, writing scripts to manage files, and interacting with operating systems.
    *   **Game Development:** Libraries like Pygame make it possible to create simple games with Python.
    *   **Education:** Many universities use Python as the introductory language for computer science courses.
    *   **General-Purpose Programming:** You can use Python to create almost any kind of application.

*   **Huge Community and Extensive Libraries:** Python has a massive and active community, which means there's a wealth of online resources, tutorials, documentation, and support available. You can easily find answers to your questions and get help when you're stuck.  The extensive library ecosystem means you don't have to reinvent the wheel – there are pre-built modules for almost anything you want to do.

*   **Career Opportunities:** While all three languages can lead to careers, Python's versatility and popularity in high-demand fields like data science and web development make it a strong choice for future job prospects.

**Why JavaScript is Second Best (But Not the Right Choice to Start):**

*   **Essential for Web Development (Frontend):** JavaScript is the language of the web browser. It's used to create interactive websites, dynamic user interfaces, and web applications. If you want to be a frontend web developer, you *must* learn JavaScript.
*   **Backend Development (with Node.js):**  Node.js allows you to use JavaScript on the server-side, expanding its capabilities.
*   **Steeper Learning Curve:** While JavaScript is powerful, it can be more confusing for beginners than Python. Its syntax is a bit more complex, and understanding the asynchronous nature of JavaScript can be challenging.
*   **Focus is More Narrow:** While JavaScript is incredibly important, it's primarily focused on web development. Python's broader applicability makes it a better starting point for exploring different areas of programming.
*   **Reason for Second best:** You may want to pick up JavaScript after Python, particularly if you're interested in web development.

**Why Fortran is the Least Recommended (Especially for a Beginner):**

*   **Scientific and Engineering Applications:** Fortran is a venerable language that is still used in scientific computing, numerical analysis, and engineering simulations. It's highly optimized for these types of tasks.
*   **Legacy Code:** A lot of existing scientific and engineering software is written in Fortran, so there's a need for programmers to maintain and update this code.
*   **Very Niche:**  Compared to Python and JavaScript, Fortran has a much smaller and more specialized community.
*   **Outdated Syntax:** Fortran's syntax can feel archaic compared to modern languages like Python.
*   **Limited Applicability Outside of Specific Fields:** While Fortran is essential in its niche, it's not as useful for general-purpose programming or other common applications.  It's unlikely to be used in a high school setting outside of very specific STEM projects.

**In summary:**

*   **Learn Python first.**  It's the easiest to learn, the most versatile, and has the biggest community.  It will give you a strong foundation in programming concepts.
*   **Then, consider learning JavaScript** if you're interested in web development.
*   **Only learn Fortran** if you have a specific need for it (e.g., a science teacher requires it for a project).

Good luck with your programming journey!



### Improve response quality by including examples

Another way to improve response quality is to add examples in your prompt. The LLM learns in-context from the examples on how to respond. Typically, one to five examples (shots) are enough to improve the quality of responses. Including too many examples can cause the model to over-fit the data and reduce the quality of responses.

Similar to classical model training, the quality and distribution of the examples is very important. Pick examples that are representative of the scenarios that you need the model to learn, and keep the distribution of the examples (e.g. number of examples per class in the case of classification) aligned with your actual distribution.

#### Zero-shot prompt

Below is an example of zero-shot prompting, where you don't provide any examples to the LLM within the prompt itself.


```python
prompt = """Decide whether a Tweet's sentiment is positive, neutral, or negative.

Tweet: I loved the new YouTube video you made!
Sentiment:
"""

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```


Sentiment: Positive



#### One-shot prompt

Below is an example of one-shot prompting, where you provide one example to the LLM within the prompt to give some guidance on what type of response you want.


```python
prompt = """Decide whether a Tweet's sentiment is positive, neutral, or negative.

Tweet: I loved the new YouTube video you made!
Sentiment: positive

Tweet: That was awful. Super boring 😠
Sentiment:
"""

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```


Sentiment: negative



#### Few-shot prompt

Below is an example of few-shot prompting, where you provide a few examples to the LLM within the prompt to give some guidance on what type of response you want.


```python
prompt = """Decide whether a Tweet's sentiment is positive, neutral, or negative.

Tweet: I loved the new YouTube video you made!
Sentiment: positive

Tweet: That was awful. Super boring 😠
Sentiment: negative

Tweet: Something surprised me about this video - it was actually original. It was not the same old recycled stuff that I always see. Watch it - you will not regret it.
Sentiment:
"""

response = client.models.generate_content(model=MODEL_ID, contents=prompt)
display(Markdown(response.text))
```


Sentiment: positive



#### Choosing between zero-shot, one-shot, few-shot prompting methods

Which prompt technique to use will solely depends on your goal. The zero-shot prompts are more open-ended and can give you creative answers, while one-shot and few-shot prompts teach the model how to behave so you can get more predictable answers that are consistent with the examples provided.
