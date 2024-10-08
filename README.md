# Kagaz

*Midnight ledger / The Moons Gazette*

So, I have been getting this Idea since long that “ What If I make a newspaper that gives news of some other world”. And thats how we are here today.

## It needs a:

- Punchy Headline
- Many Small articles
- A Good Name
- Awesome font styles

## From AI end it needs:

- Characters
- Things
- Situations
- Locations
- Plot
- Articles

```mermaid
flowchart TD
    classDef main fill:#FF6B6B,stroke:#333,stroke-width:2px,color:#000
    classDef sub fill:#4ECDC4,stroke:#333,stroke-width:2px,color:#000
    classDef detail fill:#FFD93D,stroke:#333,stroke-width:1px,color:#000
    classDef article fill:#6BCB77,stroke:#333,stroke-width:1px,color:#000

    Newspaper[Otherworldly Newspaper]:::main
    Newspaper --> Features[Newspaper Features]:::sub
    Newspaper --> Content[Content Generation]:::sub
    Newspaper --> Structure[Weekly Structure]:::sub

    Features --> |1| Headline[Punchy Headline]:::detail
    Features --> |2| Articles[Many Small Articles]:::detail
    Features --> |3| Name[A Good Name]:::detail
    Features --> |4| Font[Awesome Font Styles]:::detail

    Content --> Characters[Characters]:::sub
    Content --> Things[Things]:::sub
    Content --> Situations[Situations]:::sub
    Content --> Locations[Locations]:::sub
    Content --> Plots[Plots]:::sub

    Characters --> CharDetail[New weekly characters<br>with own storylines]:::detail
    Things --> ThingsDetail[Important objects<br>in character stories]:::detail
    Situations --> SituationDetail[Weekly defined<br>'What happened?' factor]:::detail
    Locations --> LocationDetail[Multiple locations<br>per plot]:::detail

    Plots --> PlotDetail[7 articles per plot<br>1 week duration]:::detail
    PlotDetail --> ArticleStructure[Article Structure]:::sub

    ArticleStructure --> |1| Art1[Article 1]:::article
    ArticleStructure --> |2| Art2[Article 2]:::article
    ArticleStructure --> |3| Art3[Article 3]:::article
    ArticleStructure --> |4| Art4[Article 4]:::article
    ArticleStructure --> |5| Art5[Article 5]:::article
    ArticleStructure --> |6| Art6[Article 6]:::article
    ArticleStructure --> |7| Art7[Article 7]:::article

    Structure --> WeeklyStructure[12 different plots<br>3 key events per week]:::detail
```

## Characters:

- Hmm lemme think each week there are new characters that are made.
- Each characters will have there own story lines.
- Each characters will have there own situations they will fall into.
- And Each character will have a end of week conclusion.

```mermaid
graph TD
  Character --> Things
  Character --> Situation
  Character --> Locations
  Character --> Plots
  Character --> Aticles
  
```

## Things:

- So each character will have multiple things that will be in there story.
- Things can be stuff like *(A missing shoe, a yellow umbrella, A knife used for stabbing, A lost bicycle)*
- Why are they important?
    
    *“**Objects help the writer develop the narrative and are often essential to the story**. A storyteller can tell about magical objects, such as a wand. They can also introduce into the story a map, from which the whole narrative starts, a gun or a watch. Many stories have started with a simple object.”*
    

```mermaid
graph TD
  Things --> Characters
  Things --> Situations
  Things --> Locations
  Things --> Plots
```

## Situations:

- Hmm more like headlines I guess the *(What happened to Jeff?)* factor.
- Situations will be the outline of plots or like the topic of plots.
- Will be defined weekly.
- Situations will also define - Outlines, Plots, Characters, Things.

## Plots:

- So Plots hmmm ….. PLOTS PLOTS PLOTS. According to me plots will be generated using the the context of situations.
- Each plot will follow the basics of story it will start with a topic and end at a conclusion in the end of the week
- Each Plot will be 1 week long or will have 7 key stories.
- There will be a total of 12 different plots and each plot will have 7 parts or 7 articles.
- In the end of the each week the architecture will generate 3 diff keys points and a random topic will be selected so that we will never know what will happen next.
- Ok here is what I am thinking:

![chart](https://github.com/user-attachments/assets/ee7a3904-b623-4c85-ac94-bdff5ed1ff33)


## Location:

- Each Location will be a part of a plot .
- Each Plot will have Multiple Locations.
- Each Location will have a significance.

## Articles:

- All Articles will be based on a plot.
- A plot will have 7 articles.
- Each article will have 5 key events
- each article will be related to one another for every plot
- Each Key Event will be randomly selected from a option of 3

# LLM Ka Hissa:

## The Basic Generate Function:

```python
from groq import Groq

client = Groq()
completion = client.chat.completions.create(
    model="llama3-8b-8192",
    messages=[
        {
            "role": "user",
            "content": ""
        }
    ],
    temperature=1,
    max_tokens=1024,
    top_p=1,
    stream=True,
    stop=None,
)

for chunk in completion:
    print(chunk.choices[0].delta.content or "", end="")

```

Basically This Function Will Be Modified and used to make all other generation functions.
