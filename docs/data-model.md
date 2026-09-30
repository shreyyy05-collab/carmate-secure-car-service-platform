# CARMATE Logical Data Model

CARMATE was designed around seven principal data stores.

## USERS
- `user_id` — UUID
- `role` — customer, provider, or admin
- `email` — unique account email
- `phone` — contact information
- `rating_avg` — aggregate user/provider rating

## SERVICE_REQUESTS
- `request_id`
- `customer_id`
- `category`
- `description`
- `photos` — structured photo metadata
- `zip_code`
- `budget`
- `status` — open, matched, completed, or canceled

## QUOTES
- `quote_id`
- `request_id`
- `provider_id`
- `amount`
- `eta_minutes`
- `message`
- `status` — sent, accepted, rejected, or expired

## JOBS
- `job_id`
- `request_id`
- `provider_id`
- `start_time`
- `end_time`
- `status` — accepted, in_progress, done, or canceled

## PAYMENTS
- `payment_id`
- `job_id`
- `amount`
- `method` — card or wallet
- `status` — authorized, captured, refunded, or failed

## REVIEWS
- `review_id`
- `job_id`
- `rating`
- `comment`
- `created_at`

## NOTIFICATIONS
- `notif_id`
- `user_id`
- `type`
- `payload` — structured notification data
- `read_flag`

## Relationships

The model connects customers to service requests, requests to provider quotes, accepted service relationships to jobs, and completed workflows to payments and reviews. Notifications are associated with users and provide status communication throughout the workflow.

This is a logical design artifact and does not claim that the complete schema was deployed to a production database.
