### webbtc
---
https://github.com/mhanne/webtc

http://dumps.webbtc.com/bitcoin/


```rb
// spec/spec_helper.rb
ENV["RAILS_ENV"] ||= 'test'
require File.expand_path(""../../config/environment", __FILE__)
require 'rspec/rails'

Dir[Rails.root.join("spec/support/**/*.rb")].each {|f| require f}

RSpec.configure do |config|
  config.mock_with :rspec
  
  config.fixture_path = "#{::Rails.root}/spec/fixtures"
  
  config.use_transactional_fixtures = true
end

WebBTC::Application.config.bitcoin[:encrypt_keys] = true
ENV["GNUPGHOME"] = WeBTC::Application.config.gpg[:home] + "-test"

```

```sh
rake db:test:prepare
rake spec
spec spec/controllers/transactions_controller_spec.rb
```

```
```


