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
| `horror_dice_current` | number | Count of horror dice currently occupying the pool. |
| `horror_ones_this_scene` | number | Count of horror dice showing 1 this scene (feeds trauma modifiers). |
| `pending_trauma_check` | checkbox | Flag indicating a trauma roll is pending after a horror die shows 1. |
| `pending_trauma_notes` | textarea | Reminder text for the trigger or consequences of the pending trauma check. |
| `horror_gain_amount` | number | Amount of horror to add when applying a gain via the UI controls. |
| `horror_gain_reason` | text | Narrative reason or trigger for the latest horror increase. |
| `horror_die_face` | select | Latest horror die face rolled (1–6). |
| `horror_die_ones` | number | Number of horror dice that showed a result of 1 in the roll. |
| `horror_die_notes` | text | Context for the horror die roll (action attempted, situation, etc.). |
| `horror_reduce_amount` | number | Amount of horror limit reduction to apply from external healing or effects. |
| `horror_reduce_notes` | text | Notes about the source of a direct horror reduction. |
| `horror_rest_notes` | text | Details recorded when a week of rest removes all horror. |

## Insight

| Attribute | Type | Description |
|-----------|------|-------------|
| `insight_current` | number | Insight currently available to spend. |
| `insight_limit` | number | Session refresh maximum. |
| `insight_spent_session` | number | Running total of insight spent this session. |
| `insight_success_notes` | text | Context for spending insight on an additional success. |
| `insight_advantage_notes` | text | Notes describing the roll that will benefit from spent advantage. |
| `insight_clue_cost` | number | GM-assigned cost when requesting a clue. |
| `insight_clue_notes` | text | Clue target or question being asked. |
| `insight_edit_cost` | number | Cost of the requested narrative edit. |
| `insight_edit_notes` | text | Description of the desired narrative element. |
| `insight_survival_notes` | text | Explanation of how the investigator avoided certain doom. |

## Sheet Navigation

| Attribute | Type | Description |
|-----------|------|-------------|
| `sheet_tab` | radio | Active tab selection controlling visible layout (`overview`, `combat`, `status`, `scenes`, `notes`). |

## Skills

Each skill stores the minimum die result needed for success (2–6). Notes fields provide optional context.

| Attribute | Type | Description |
|-----------|------|-------------|
| `skill_agility` | radio (2–6) | Agility tier threshold selected via pip controls. |
| `skill_agility_notes` | text | Narrative notes or specialty information. |
| `skill_athletics` | radio (2–6) | Athletics tier threshold selected via pip controls. |
| `skill_athletics_notes` | text | Notes for Athletics. |
| `skill_wits` | radio (2–6) | Wits tier threshold selected via pip controls. |
| `skill_wits_notes` | text | Notes for Wits. |
| `skill_presence` | radio (2–6) | Presence tier threshold selected via pip controls. |
| `skill_presence_notes` | text | Notes for Presence. |
| `skill_intuition` | radio (2–6) | Intuition tier threshold selected via pip controls. |
| `skill_intuition_notes` | text | Notes for Intuition. |
| `skill_knowledge` | radio (2–6) | Knowledge tier threshold selected via pip controls. |
| `skill_knowledge_notes` | text | Notes for Knowledge. |
| `skill_resolve` | radio (2–6) | Resolve tier threshold selected via pip controls. |
| `skill_resolve_notes` | text | Notes for Resolve. |
| `skill_melee_combat` | radio (2–6) | Melee Combat tier threshold selected via pip controls. |
| `skill_melee_combat_notes` | text | Notes for Melee Combat. |
| `skill_ranged_combat` | radio (2–6) | Ranged Combat tier threshold selected via pip controls. |
| `skill_ranged_combat_notes` | text | Notes for Ranged Combat. |
| `skill_lore` | radio (2–6) | Lore tier threshold selected via pip controls. |
| `skill_lore_notes` | text | Notes for Lore. |

## Trauma & Horror Effects

| Attribute | Type | Description |
|-----------|------|-------------|
| `trauma_last_result` | text | Most recent trauma table outcome. |
| `trauma_roll_total` | number | Total after modifiers when rolling on Table 2-2. |
| `trauma_modifier_session` | number | Persistent modifier applied to trauma rolls for the session. |
| `trauma_duration_scope` | select | Duration reminder for current trauma (`turn`, `scene`, `session`, `ongoing`). |
| `trauma_insight_spent` | number | Insight spent to mitigate the most recent trauma. |
| `trauma_personality_triggered` | checkbox | Notes when the negative personality trait was forced to trigger. |
| `insight_buffer` | number | Insight reserved to offset trauma triggers. |
| `introspection_attempts` | number | Introspection actions logged for the current scene. |
| `counseling_attempts` | number | Counseling actions logged for the current scene. |
| `introspection_successes` | number | Pending successes to apply when spending an Introspection action. |
| `introspection_notes` | text | Notes about how the character centers themselves during Introspection. |
| `counseling_successes` | number | Pending successes to apply when receiving Counseling. |
| `counseling_target` | text | Who provided (or received) counseling support. |
| `counseling_notes` | text | Summary of the counseling focus or outcome. |
| `trauma_notes` | text | Narrative notes and ongoing effects. |
| `horror_limit_track` | text (read only) | Auto-generated indicator string showing the horror dice limit for the visual track. |
| `horror_current_track` | text (read only) | Auto-generated indicator string representing current horror dice in the pool. |

## Trauma Log (Repeating Section: `repeating_trauma`)

| Attribute | Type | Description |
|-----------|------|-------------|
| `trauma_entry_roll` | number | Roll total (after modifiers) recorded for the entry. |
| `trauma_entry_result` | select | Table 2-2 result classification. |
| `trauma_entry_duration` | select | Duration reminder (`turn`, `scene`, `session`, `ongoing`). |
| `trauma_entry_insight` | number | Insight spent to resist or mitigate the trauma. |
| `trauma_entry_personality` | checkbox | Indicates whether the negative personality trait triggered. |
| `trauma_entry_notes` | textarea | Notes about effects, roleplay, or recovery. |

## Combat Controls

| Attribute | Type | Description |
|-----------|------|-------------|
| `advantage_active` | checkbox | Indicates advantage is active for the next roll. |
| `disadvantage_active` | checkbox | Indicates disadvantage is active for the next roll. |
| `cover_penalty` | number | Penalty per die from cover or similar hindrances. |
| `is_engaged` | checkbox | Tracks whether the investigator is currently engaged. |
| `reaction_dice_reserved` | number | Dice held back for reactions. |
| `active_weapon` | text | Focus weapon or maneuver for quick reference. |
| `combat_notes` | textarea | Situation reminders, enemy conditions, or modifiers. |

## Action Tracking

| Attribute | Type | Description |
|-----------|------|-------------|
| `actions_turn_simple` | number | Count of simple actions performed during the current turn. |
| `actions_turn_complex` | number | Count of complex actions performed during the current turn. |
| `actions_turn_reactions` | number | Number of reactions resolved during the current turn. |
| `dice_spent_turn` | number | Dice spent from the pool during the current turn. |
| `actions_scene_simple` | number | Simple actions completed in the ongoing scene. |
| `actions_scene_complex` | number | Complex actions completed in the ongoing scene. |
| `actions_scene_reactions` | number | Reactions resolved across the ongoing scene. |
| `dice_spent_scene` | number | Dice spent in total across the scene to monitor attrition. |
| `same_task_attempted_turn` | checkbox | Flags that the same complex task has already been attempted this turn. |
| `same_task_attempted_scene` | checkbox | Flags that the same complex task has already been attempted this scene. |
| `action_reserve_dice_flag` | checkbox | Reminder that dice are being held for future reactions. |
| `action_restriction_noted` | checkbox | Indicates additional limits or situational modifiers have been recorded. |
| `action_notes` | textarea | Notes for once-per-scene abilities, reaction planning, or task variants. |

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
| `weapon_type` | select | Classification (`melee`, `ranged`, `other`) for quick filtering. |
| `weapon_damage` | text | Base damage expression. |
| `weapon_injury_rating` | text | Injury rating threshold for inflicting injuries. |
| `weapon_range` | text | Effective range band or description. |
| `weapon_cover_penalty` | number | Additional penalty per die applied when target has cover. |
| `weapon_skill_target` | select | Reference to the skill attribute used for the attack roll threshold. |
| `weapon_reaction_skill` | select | Reference to the skill attribute rolled for defensive reactions. |
| `weapon_requires_engaged` | checkbox | Indicates the attack requires the user to be engaged with the target. |
| `weapon_special` | textarea | Special rules, ammunition tracking, or notes. |

## Injuries (Repeating Section: `repeating_injuries`)

| Attribute | Type | Description |
|-----------|------|-------------|
| `injury_roll_total` | number | Recorded roll total used to consult Table 2-1. |
| `injury_table_result` | select | Table 2-1 or unique injury identifier. |
| `injury_name` | text | Custom label or additional context for the injury. |
| `injury_heal_difficulty` | select | Healing difficulty (`normal`, `difficult`, `very_difficult`). |
| `injury_recovery_days` | number | Natural healing countdown in days. |
| `injury_recovery_timer` | text | Date, scene, or other reminder for natural healing checkpoints. |
| `injury_medical_attempts` | number | Count of medical healing attempts this scene. |
| `injury_penalty_active` | checkbox | Tracks whether the penalty is currently applied. |
| `injury_requires_insight` | checkbox | Highlights injuries requiring insight expenditure to stave off consequences. |
| `injury_flag_burned` | checkbox | Flags burn-specific rules (disadvantage, dice loss on 1s). |
| `injury_flag_choking` | checkbox | Flags choking rules (simple action cost 2 dice, complex becomes difficult). |
| `injury_flag_sickened` | checkbox | Flags sickened rules (1d3 max dice spent). |
| `injury_penalty` | textarea | Detailed mechanical penalties or dice adjustments. |
| `injury_notes` | textarea | Treatment plan, recovery story beats, or additional notes. |

## Status Notes

| Attribute | Type | Description |
|-----------|------|-------------|
| `condition_notes` | textarea | Miscellaneous conditions, status effects, or reminders. |

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
| `scene_reactions_logged` | number | Counter for reactions used during the current scene. |
| `scene_advantage_pool` | number | Available advantage dice shared among investigators. |
| `scene_notes` | text | Additional context, timers, or environmental notes. |

## Investigator Notes

| Attribute | Type | Description |
|-----------|------|-------------|
| `clue_log` | textarea | Player-managed record of clues and leads. |
| `contacts_log` | textarea | Allies, contacts, or factions supporting the investigators. |
| `personal_journal` | textarea | Session notes, personal reflections, or outstanding questions. |

These definitions will guide the next implementation steps, including Sheet Worker automation and roll button construction.
