## Laravel Stats Tracker Upgrading Guide

### to 0.4.0

- Add the following keys to your `app/config/packages/pragmarx/tracker/config.php`:

```
	'log_geoip' => true,
	'log_user_agents' => true,
	'log_users' => true,
	'log_devices' => true,
	'log_referers' => true,
	'log_paths' => true,
	'log_queries' => true,
	'log_routes' => true,
```

- On `tracker_sessions` table, alter columns `device_id` and `agent_id` to be nullable.
- On `tracker_log` table, alter column `path_id` to be nullable.

### to 0.3.2

- Add a is_robot boolean column to: `ALTER TABLE tracker_sessions ADD is_robot BOOL;`
- Add `'do_not_track_robots' => true or false,` to `tracker\config.php`.
- Change `tracker_events_log.class_id` to be a nullable column.
