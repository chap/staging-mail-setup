Staging Mail Setup
==================

Signup for a free account at [stagingmail.com](http://www.stagingmail.com)

### Rails
Add to config/environments/development.rb and any other environment you want
```ruby
ActionMailer::Base.smtp_settings = {
  :user_name => "your@email.com",
  :password => "your-api-password",
  :address => "smtp.stagingmail.com",
  :port => 10587,
  :authentication => :plain,
  :enable_starttls_auto => true
}
```

### PHP

Add to factories.yml
```php
$this->Email->smtpOptions = array(
'port'=>'10587',
'host' => 'smtp.stagingmail.com',
'username'=>'your@email.com',
'password'=>'your-api-password',
);
$this->Email->delivery = 'smtp';
$this->Email->from = 'Your Name ';
$this->Email->to = 'Recipient Name ';
$this->set('name', 'Recipient Name');
$this->Email->subject = 'My Subject';
$this->Email->template = 'registration';
$this->Email->sendAs = 'both';
$this->Email->send();
```

### Django
Add to settings.py
```python
EMAIL_HOST = 'smtp.stagingmail.com'
EMAIL_HOST_USER = 'your@email.com'
EMAIL_HOST_PASSWORD = 'your-api-password'
EMAIL_PORT = 10587
EMAIL_USE_TLS = True
```