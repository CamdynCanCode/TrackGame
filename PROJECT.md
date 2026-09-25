# TrackGame Project Specification

## 1. Game Concept

TrackGame is a single-player career-focused track & field sports game.

The goal is to combine the gameplay and presentation of a modern sports game with the progression and customization of a career RPG.

The player creates an athlete and follows their career from their early competitive years toward higher levels of competition and potentially a professional career.

The game should make individual races matter.

A race should not simply be "800m - Start."

It should have context:

* Why am I racing?
* Who am I racing?
* What do I need to qualify for?
* What is my current PR?
* Who is my rival?
* What happens if I win?
* How is my career changing?

---

# 2. Core Gameplay Loop

The primary loop is:

Create Athlete
→ Train
→ Enter Meet
→ Race
→ Receive Results
→ Improve Athlete
→ Progress Career
→ Enter More Important Meets

Later systems such as recruiting, sponsorships, equipment, and professional contracts will build on this loop.

---

# 3. Race Simulation

The race simulation is the foundation of the game.

The simulation should be independent from the visual character system as much as reasonably possible.

An athlete should have simulation data such as:

* Distance traveled
* Current velocity
* Maximum velocity
* Acceleration
* Fatigue
* Stamina
* Position
* Lane
* Race strategy
* Relevant attributes

The simulation determines what an athlete is doing.

The animation system turns that state into what the player sees.

## Example

An athlete might have:

* Distance: 612m
* Speed: 7.9 m/s
* Fatigue: 64%
* Position: 3rd
* Strategy: Sit and kick

The character animation system uses that information to produce the appropriate movement.

---

# 4. Athlete Attributes

Attributes should influence performance without making the system feel like a simple arcade stat boost.

Potential attributes include:

### Speed

Maximum running speed.

### Acceleration

How quickly the athlete reaches higher speeds.

### Aerobic Endurance

Ability to maintain performance over longer periods.

### Speed Endurance

Ability to maintain high speed while fatigued.

### Kick

Ability to produce additional speed late in a race.

### Race IQ

Ability to make better tactical decisions.

### Recovery

How quickly fatigue decreases between efforts and training sessions.

The exact attribute system will be tested and changed during development.

---

# 5. AI Racing

AI runners should behave like athletes rather than moving along predetermined paths.

Potential strategies include:

* Front running
* Even pacing
* Sit and kick
* Surging
* Responding to competitors
* Saving energy
* Moving for position

AI should be capable of reacting to the race rather than following identical predetermined splits every time.

---

# 6. Character System

Characters should use a shared skeletal system where possible.

Customization should primarily modify appearance rather than directly modifying athletic performance.

Potential customization:

* Height
* Body proportions
* Face
* Hair
* Skin
* Clothing
* Shoes
* Accessories

Face customization can use morph targets/blend shapes.

Character appearance should be representable as data so that the same character can be recreated when loading a save.

Example concept:

```text
CharacterData
- Face parameters
- Body parameters
- Hair ID
- Hair color
- Clothing IDs
- Shoe ID
```

---

# 7. Equipment

Equipment will eventually include:

* Running shoes
* Spikes
* Training shoes
* Uniforms
* Warmups
* Accessories

Equipment may eventually have gameplay effects, but the initial prototype should treat equipment primarily as cosmetic.

Gameplay effects should only be introduced if they improve the game without making equipment feel like mandatory stat upgrades.

---

# 8. Career

The long-term career structure may include:

* School competition
* Regional competition
* State-level competition
* Recruiting
* College
* Professional competition

The exact career structure is not finalized.

The MVP does not need the complete career system.

---

# 9. Sponsorships

A long-term feature is a sponsorship system inspired by professional sports games.

Potential sponsors could offer:

* Money
* Equipment
* Apparel
* Bonuses
* Contract extensions
* Performance incentives

Possible contract requirements could include:

* Performance targets
* Appearance requirements
* Brand exclusivity
* Social media/reputation requirements

The player should eventually have meaningful choices between different contracts rather than simply selecting the highest number.

---

# 10. Presentation

The game should eventually have a polished sports-broadcast presentation.

Potential features:

* Race introductions
* Athlete introductions
* Dynamic camera angles
* Commentary
* Crowd reactions
* Meet branding
* Replay system
* Personal records displayed during races
* Championship presentation

These are not MVP priorities.

---

# 11. Technical Philosophy

The project should favor clean systems and separation of responsibilities.

Important systems should not become tightly coupled just because doing so is faster initially.

The race simulation should be usable without requiring the full graphical presentation.

Data-driven systems should be preferred where practical.

Major systems should be testable independently.

The project should remain understandable enough that future development can happen without relying entirely on AI-generated code.

---

# 12. AI Development

AI coding tools may be used extensively during development.

AI should be treated as a development assistant rather than the sole architect.

AI-generated code should be reviewed, tested, and understood before becoming a permanent part of the project.

Important architectural decisions should be documented in this project.

---

# 13. Current Development Stage

Stage: Pre-production

Current objective:

Design the core architecture and build the first playable 800m prototype.

The first prototype does not need polished graphics.

The priority is proving that the racing system is fun.
