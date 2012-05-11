# Rails Notes

This is a collection of rails notes.

## Cucumber
* Place holders: `"(.*?)"`, `(\w+)`
* Check input tags exists

		Then /^I should see an? "(.*)" text field$/ do |field_name|
		  response.should have_tag('input[type=text][name*=?]', /#{field_name}/i)
		end
		
		Then /^I should see an? "(.*)" check box$/ do |field_name|
		  response.should have_tag('input[type=checkbox][name*=?]', /#{field_name}/i)
		end

		Then /^I should see a "(.*)" dropdown$/ do |text|
		  response.should have_tag("select option", text)
		end

## RSpec
### Controller
* Routes

		def route_matches(path, method, params)
		  it "maps #{params.inspect} to #{path.inspect}" do
		    route_for(params).should == {:path => path, :method => method}
		  end

		  it "generates params #{params.inspect} from #{method.to_s.upcase} to #{path.inspect}" do
		    params_from(method.to_sym, path).should == params
		  end
		end
		
		describe User do
		  route_matches("/users",        :post,   :controller => "users", :action => "create")
		  route_matches("/users/1",      :delete, :controller => "users", :action => "destroy", :id => "1")
		end

## Interesting Open Source Projects
* <https://github.com/rmu/university-web>
* <https://github.com/spot-us/spot-us>
* <https://github.com/diaspora/diaspora>
* <https://github.com/radar/rboard>
* <https://github.com/riseuplabs/crabgrass>
* <https://github.com/teambox/teambox>
* <https://github.com/resolve/refinerycms>
* <https://github.com/dalibor/popravi.mk>