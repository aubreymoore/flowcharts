graph TD
  start((start)) --> lock_booking
  lock_booking --> process_payment
  process_payment --> successful_payment{"success?"}
  successful_payment -->|NO|release_booking
  successful_payment -->|YES|reserve_booking
  reserve_booking --> send_email
  finish(((finish)))
  send_email --> finish
  release_booking --> finish
