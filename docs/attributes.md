# Attribute Reference

This document defines the Roll20 attribute names used throughout the Arkham Horror character sheet scaffold. Values are stored as standard Roll20 character attributes and will be referenced by Sheet Workers and roll buttons in future iterations.

## Character Metadata

| Attribute | Type | Description |
|-----------|------|-------------|
| `character_name` | text | Primary name of the investigator. |
| `character_archetype` | text | Archetype or role descriptor. |
| `player_name` | text | Player controlling the investigator. |
| `total_xp` | number | Lifetime experience earned. |
| `unspent_xp` | number | XP available to spend. |
| `personality_trait_positive` | text | Positive half of the personality trait pair. |
| `personality_trait_negative` | text | Negative half of the personality trait pair. |

## Dice Pool & Horror Tracking

| Attribute | Type | Description |
|-----------|------|-------------|
| `dice_pool_current` | number | Dice currently available to spend. |
| `dice_pool_limit` | number | Current refill target after damage or strain. |
| `dice_pool_max` | number | Maximum dice pool size established at creation. |
| `horror_dice_limit` | number | Number of dice that become horror dice when refilling. |
| `horror_ones_this_scene` | number | Count of horror dice showing 1 this scene (feeds trauma modifiers). |

## Insight

| Attribute | Type | Description |
|-----------|------|-------------|
| `insight_current` | number | Insight currently available to spend. |
| `insight_limit` | number | Session refresh maximum. |

## Skills

Each skill stores the minimum die result needed for success (2–6). Notes fields provide optional context.

| Attribute | Type | Description |
|-----------|------|-------------|
| `skill_agility` | select (2–6) | Agility tier threshold. |
| `skill_agility_notes` | text | Narrative notes or specialty information. |
| `skill_athletics` | select (2–6) | Athletics tier threshold. |
| `skill_athletics_notes` | text | Notes for Athletics. |
| `skill_wits` | select (2–6) | Wits tier threshold. |
| `skill_wits_notes` | text | Notes for Wits. |
| `skill_presence` | select (2–6) | Presence tier threshold. |
| `skill_presence_notes` | text | Notes for Presence. |
| `skill_intuition` | select (2–6) | Intuition tier threshold. |
| `skill_intuition_notes` | text | Notes for Intuition. |
| `skill_knowledge` | select (2–6) | Knowledge tier threshold. |
| `skill_knowledge_notes` | text | Notes for Knowledge. |
| `skill_resolve` | select (2–6) | Resolve tier threshold. |
| `skill_resolve_notes` | text | Notes for Resolve. |
| `skill_melee_combat` | select (2–6) | Melee Combat tier threshold. |
| `skill_melee_combat_notes` | text | Notes for Melee Combat. |
| `skill_ranged_combat` | select (2–6) | Ranged Combat tier threshold. |
| `skill_ranged_combat_notes` | text | Notes for Ranged Combat. |
| `skill_lore` | select (2–6) | Lore tier threshold. |
| `skill_lore_notes` | text | Notes for Lore. |

## Trauma & Horror Effects

| Attribute | Type | Description |
|-----------|------|-------------|
| `trauma_last_result` | text | Most recent trauma table outcome. |
| `trauma_modifier_session` | number | Persistent modifier applied to trauma rolls for the session. |
| `trauma_notes` | text | Narrative notes and ongoing effects. |

## Knacks (Repeating Section: `repeating_knacks`)

| Attribute | Type | Description |
|-----------|------|-------------|
| `knack_tier` | select | Tier assignment (`tier1`–`tier4`). |
| `knack_name` | text | Knack title. |
| `knack_effect` | textarea | Description of benefits or triggers. |

## Weapons (Repeating Section: `repeating_weapons`)

| Attribute | Type | Description |
|-----------|------|-------------|
| `weapon_name` | text | Weapon or attack name. |
| `weapon_damage` | text | Base damage expression. |
| `weapon_range` | text | Effective range band. |
| `weapon_issue_rating` | text | Reliability/issue rating notation. |
| `weapon_special` | textarea | Special rules, ammunition tracking, or notes. |

## Injuries (Repeating Section: `repeating_injuries`)

| Attribute | Type | Description |
|-----------|------|-------------|
| `injury_name` | text | Injury table result or custom descriptor. |
| `injury_penalty` | text | Mechanical penalty reminder. |
| `injury_heal_difficulty` | select | Healing difficulty (`normal`, `difficult`, `very_difficult`). |
| `injury_recovery_timer` | text | Natural recovery timer or notes. |

## Social Scene Actions (Repeating Section: `repeating_socialactions`)

| Attribute | Type | Description |
|-----------|------|-------------|
| `social_action_actor` | text | Investigator leading the action. |
| `social_action_target` | text | NPC or faction targeted. |
| `social_action_skill` | text | Skill used to attempt the action. |
| `social_action_result` | select | Outcome tracking (`pending`, `success`, `reaction_negated`, `fail`). |
| `social_action_notes` | textarea | Consequences, insight spend, or modifiers. |

## Vehicle Log (Repeating Section: `repeating_vehicles`)

| Attribute | Type | Description |
|-----------|------|-------------|
| `vehicle_name` | text | Vehicle identifier. |
| `vehicle_condition` | select | Condition state (`operational`, `lightly_damaged`, `heavily_damaged`, `destroyed`). |
| `vehicle_last_check` | text | Last maintenance, repair, or chase note. |
| `vehicle_notes` | textarea | Additional context, repairs needed, or complications. |

## Scene Tracking

| Attribute | Type | Description |
|-----------|------|-------------|
| `scene_type` | select | Current scene mode (`narrative`, `structured`, `social`). |
| `scene_round` | number | Current structured-scene round count. |
| `scene_turn` | text | Whose turn is active or whose dice refresh next. |
| `scene_social_difficulty` | select | Difficulty for social scenes (`easy`, `average`, `hard`). |
| `scene_social_success_goal` | number | Required number of successful complex actions. |
| `scene_social_successes` | number | Successful complex actions achieved so far. |
| `scene_notes` | text | Additional context, timers, or environmental notes. |

These definitions will guide the next implementation steps, including Sheet Worker automation and roll button construction.
