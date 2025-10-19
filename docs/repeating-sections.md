# Repeating Section Planning

This guide explains how the sheet's repeating sections are structured and how they will evolve as automation is added. Each section maps to a Roll20 repeating collection, enabling players to add, reorder, or remove rows dynamically.

## Knacks (`repeating_knacks`)
- **Purpose:** Record tiered character knacks gained during progression.
- **Fields:**
  - `attr_knack_tier`: dropdown to tag the tier (1–4) for quick filtering.
  - `attr_knack_name`: short title that will appear on roll buttons or summaries.
  - `attr_knack_effect`: textarea for rules text; future styling will support emphasis and bullet lists.
- **Future automation:** Sheet Workers will auto-sort by tier, aggregate passive bonuses, and expose quick toggles if a knack grants conditional modifiers.

## Weapons (`repeating_weapons`)
- **Purpose:** Track melee and ranged weapons alongside their mechanical properties.
- **Fields:**
  - `attr_weapon_name`: weapon label shown in roll buttons.
  - `attr_weapon_type`: quick identifier for melee, ranged, or other attack forms.
  - `attr_weapon_damage`: freeform damage expression for flexibility.
  - `attr_weapon_injury_rating`: injury threshold reminder.
  - `attr_weapon_range`: text band (e.g., "Engaged", "15 ft") used to warn about range penalties.
  - `attr_weapon_cover_penalty`: per-weapon penalty to stack with global cover tracking.
  - `attr_weapon_skill_target`: selected skill attribute used for attack thresholds.
  - `attr_weapon_reaction_skill`: skill reference for defensive reactions.
  - `attr_weapon_requires_engaged`: checkbox to warn when engagement is required.
  - `attr_weapon_special`: textarea for ammunition counts, special rules, or additional notes.
- **Future automation:** Attack and reaction buttons will sync with Sheet Workers to auto-toggle advantage/disadvantage, validate engagement status, and decrement ammunition or charges.

## Injuries (`repeating_injuries`)
- **Purpose:** Catalogue current injuries and their associated penalties or timers.
- **Fields:**
  - `attr_injury_roll_total`: recorded Table 2–1 roll after modifiers.
  - `attr_injury_table_result`: dropdown referencing core and unique injuries (Burned, Choking, Sickened).
  - `attr_injury_name`: customizable descriptor for flavor or differentiation.
  - `attr_injury_heal_difficulty`: dropdown flagging the number of successes required to heal.
  - `attr_injury_recovery_days`: numeric natural healing countdown in days.
  - `attr_injury_recovery_timer`: milestone reminder (date, session marker, or narrative cue).
  - `attr_injury_medical_attempts`: once-per-scene guardrail for Knowledge healing attempts.
  - `attr_injury_penalty_active`: checkbox to remind when penalties should be enforced.
  - `attr_injury_requires_insight`: checkbox for injuries requiring insight mitigation (e.g., Dire).
  - `attr_injury_flag_burned` / `attr_injury_flag_choking` / `attr_injury_flag_sickened`: toggles for unique injury riders.
  - `attr_injury_penalty`: textarea documenting dice modifiers or action restrictions.
  - `attr_injury_notes`: textarea for treatment plans, natural healing progress, or narrative flavor.
- **Current automation:**
  - Sheet Workers can add new rows automatically when you roll on Table 2–1 or strain yourself, prefilling the table result, default healing difficulty, natural recovery timer, and reminder text.
  - Selecting a different table result updates the penalty summary, recovery difficulty, and timer fields, while flagging insight requirements for Dire outcomes and toggling the unique injury switches.
- **Planned extensions:** Enforce penalties, adjust dice pool caps, countdown natural recovery timers, and surface alerts when insight mitigation is available.

## Trauma Log (`repeating_trauma`)
- **Purpose:** Preserve a history of trauma results, mitigation choices, and lingering durations.
- **Fields:**
  - `attr_trauma_entry_roll`: roll total (including +1 per horror die showing 1).
  - `attr_trauma_entry_result`: dropdown mirroring Table 2–2 outcomes.
  - `attr_trauma_entry_duration`: reminder for when the effect expires (turn, scene, session, ongoing).
  - `attr_trauma_entry_insight`: amount of insight spent to resist or reduce the trauma.
  - `attr_trauma_entry_personality`: checkbox logging whether the negative personality triggered.
  - `attr_trauma_entry_notes`: textarea for consequences, RP cues, or recovery milestones.
- **Future automation:** Sheet Workers will auto-populate entries when horror dice roll 1s, adjust trauma modifiers for subsequent rolls, and prompt insight spend opportunities.

## Horror Event Log (`repeating_horrorlog`)
- **Purpose:** Track every adjustment to the horror dice limit, including gains, recoveries, and die results that trigger trauma.
- **Fields:**
  - `attr_horror_event_type`: categorical flag (`gain`, `die`, `introspection`, `counseling`, `reduction`, `rest`).
  - `attr_horror_event_amount`: numeric amount applied (positive for gains, negative for reductions, or die face).
  - `attr_horror_event_total`: resulting horror dice limit after the adjustment.
  - `attr_horror_event_notes`: summary of the trigger, method, or narrative justification.
  - `attr_horror_event_timestamp`: timestamp capturing when the entry was logged.
- **Future automation:** Workers populate rows whenever horror is gained, reduced, or a trauma roll resolves, giving players an audit trail across scenes.

## Insight Ledger (`repeating_insightlog`)
- **Purpose:** Maintain a chronological ledger of insight expenditures and life-saving limit reductions.
- **Fields:**
  - `attr_insight_log_type`: reason for the spend (`bonus_success`, `advantage`, `clue`, `narrative_edit`, `survival`).
  - `attr_insight_log_amount`: amount of insight spent or permanent limit reduced.
  - `attr_insight_log_notes`: descriptive notes for the GM agreement or narrative outcome.
  - `attr_insight_log_timestamp`: timestamp noting when the spend occurred.
- **Future automation:** Insight controls will append log entries automatically and surface reminders when session refresh triggers.

## Social Scene Actions (`repeating_socialactions`)
- **Purpose:** Monitor complex actions taken during social scenes and track progress toward the success threshold.
- **Fields:**
  - `attr_social_action_actor`: investigator leading the action for quick reference.
  - `attr_social_action_target`: NPC or faction targeted.
  - `attr_social_action_skill`: skill leveraged for the action.
  - `attr_social_action_result`: standardized dropdown values for success/failure/reaction negation.
  - `attr_social_action_notes`: freeform notes for consequences, insight spend, or reaction costs.
- **Current automation:** Adding or updating a row immediately recalculates the scene success counter so the tracker reflects completed complex actions toward the social difficulty target.
- **Planned extensions:** Reminders for once-per-scene limits and prompts for GM-granted auto-successes from roleplay.

## Vehicle Log (`repeating_vehicles`)
- **Purpose:** Track the status of vehicles, including damage states and repair history.
- **Fields:**
  - `attr_vehicle_name`: identifier of the vehicle (e.g., "Packard Roadster").
  - `attr_vehicle_condition`: dropdown representing operational status.
  - `attr_vehicle_last_check`: last maintenance action or chase event summary.
  - `attr_vehicle_notes`: expanded notes for hazards, modifiers, or cargo.
- **Current automation:** Changing the vehicle condition stamps the entry with a dated note so you know when the status changed during play.
- **Planned extensions:** Toggle disadvantage on vehicle actions based on condition, surface repair DC reminders, and integrate with chase trackers.

These plans ensure that the visual scaffolding in `sheet.html` aligns with forthcoming Sheet Worker automation and gameplay logic.
