# =============================================================================
# MOST COMMON AIRFLOW SCHEDULE_INTERVAL CRON EXAMPLES
# =============================================================================
# Format: minute hour day month day_of_week
# -----------------------------------------------------------------------------

# HOURLY SCHEDULES
"0 * * * *"        # Every hour at minute 0 (e.g., 1:00, 2:00)
"30 * * * *"       # Every hour at minute 30 (e.g., 1:30, 2:30)
"*/15 * * * *"     # Every 15 minutes

# DAILY SCHEDULES
"0 0 * * *"        # Every day at midnight (00:00)
"0 6 * * *"        # Every day at 6:00 AM
"0 9 * * *"        # Every day at 9:00 AM
"0 18 * * *"       # Every day at 6:00 PM
"0 23 * * *"       # Every day at 11:00 PM
"30 4 * * *"       # Every day at 4:30 AM

# BUSINESS HOURS
"0 9 * * 1-5"      # Weekdays at 9:00 AM (Mon-Fri)
"0 17 * * 1-5"     # Weekdays at 5:00 PM (Mon-Fri)

# WEEKLY SCHEDULES
"0 0 * * 0"        # Every Sunday at midnight
"0 0 * * 1"        # Every Monday at midnight
"0 9 * * 1"        # Every Monday at 9:00 AM
"0 0 * * 6"        # Every Saturday at midnight

# BI-WEEKLY (Every 2 weeks on Monday at 9 AM)
"0 9 * * 1/2"      # Every 2nd Monday at 9:00 AM

# MONTHLY SCHEDULES
"0 0 1 * *"        # 1st day of every month at midnight
"0 0 15 * *"       # 15th day of every month at midnight
"0 0 28 * *"       # 28th day of every month at midnight
"0 9 1 * *"        # 1st day of every month at 9:00 AM

# QUARTERLY SCHEDULES
"0 0 1 1,4,7,10 *" # First day of each quarter (Jan, Apr, Jul, Oct)
"0 0 1 */3 *"      # Alternative: First day every 3 months

# YEARLY SCHEDULES
"0 0 1 1 *"        # January 1st every year at midnight
"0 0 1 12 *"       # December 1st every year at midnight

# COMPLEX SCHEDULES
"30 6,18 * * *"    # At 6:30 AM and 6:30 PM every day
"0 8-17 * * 1-5"   # Every hour from 8 AM to 5 PM on weekdays
"0 12 1,15 * *"    # 1st and 15th of every month at noon
"0 0 */5 * *"      # Every 5 days at midnight
"0 22 * * 1-5"     # Every weekday at 10:00 PM

# WEEKEND SCHEDULES
"0 9 * * 6,0"      # Saturday and Sunday at 9:00 AM
"0 12 * * 6"       # Every Saturday at noon

# =============================================================================
# CRON PRESET EQUIVALENTS (for reference)
# =============================================================================
# @hourly   -> "0 * * * *"
# @daily    -> "0 0 * * *" 
# @weekly   -> "0 0 * * 0"
# @monthly  -> "0 0 1 * *"
# @yearly   -> "0 0 1 1 *"
# =============================================================================