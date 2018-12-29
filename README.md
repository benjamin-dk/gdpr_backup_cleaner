Install:

- With Drush: `drush en gdpr_backup_cleaner -y`

Requirements:

- Backup and Migrate (7.x-3.6)
- General Data Protection Regulation

After installation, create new database and modify settings.php file by adding info about your new database

````
$conf['gdpr_backup_cleaner'] = 'gdpr';

$databases['default']['default'] = array(
  'database' => 'old_database', // database you're using on your site
  'username' => 'username',
  'password' => 'password',
  'host' => 'localhost',
  'port' => '',
  'driver' => 'mysql',
  'prefix' => '',
);
$databases[$conf['gdpr_backup_cleaner']]['default'] = array(
  'database' => 'gdpr_backup_cleaner', // new created database
  'username' => 'username',
  'password' => 'password',
  'host' => 'localhost',
  'port' => '',
  'driver' => 'mysql',
  'prefix' => '',
);
````
Important! This module is integrated with the "backup and migrate" project, that's why we have some restrictions regarding making and restoring backups. This module only works with backups created via the "backup and migrate" project.
