# Kajabi-http-post
Creates a new member in Kajabi from external event (shopping cart outside Kajabi)
kajabi http post

---------
POST / HTTP/ 1.1
host http so://checkout.newkajabi.com/webhooks/offers/oDLs9DoScZGPVh9F/674/activate
content-length: (don't know)
require 'json'
def post_to_endpoint(endpoint)
uri = URI.parse(endpoint)
post_params = {
:name => "Bob Smith",
:email => "bsmith@yahoo.com",
:external_user_id => "bismith814572"
}
# Convert the parameters into JSON and set the content type as application/json
req = Net::HTTP::Post.new(uri.path)
req.body = JSON.generate(post_params)
req["Content-Type"] = "application/json"
http = Net::HTTP.new(uri.host, uri.port)
response = http.start {|htt| htt.request(req)}
end
