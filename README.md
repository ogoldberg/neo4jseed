Neo4j on Heroku with Sinatra using Neography
============================================

This is a tiny little [Neo4j](http://neo4j.org) application, a 'seed' ready
to grow into graph-powered glory. 

* [Neo4j](http://neo4j.org) - the graph database
* [Neography](https://github.com/maxdemarzi/neography) - a ruby driver
* [Heroku](http://heroku.com) - cloud hosting simplicity
* [Neo4j Add-On](https://addons.heroku.com/marketplace/neo4j) - Neo4j on Heroku

## Clone, Build and Go!

1. Get Neo4j
   * [Download Neo4j](http://neo4j.org/download)
   * Follow Neo4j's README to start the database
   * Make sure it is running by browsing Neo4j's Web Interface at [http://localhost:7474](http://localhost:7474)
2. Get this seed app 
   * `git clone https://github.com/akollegger/neo4j-heroku-seeds.git`
   * `cd neo4j-heroku-seeds/ruby/sinatra-neography`
3. Prepare the app
   * `bundle install`
4. Run it locally
   * `ruby graphapp.rb`
   * Browse [http://localhost:4567](http://localhost:4567)

## Deploying to Heroku

1. Got Heroku? Get it
   * create an account on [Heroku](http://heroku.com)
   * get the [Heroku Toolbelt](https://toolbelt.heroku.com)
   * prepare the CLI with `heroku login`
   * make sure your public SSH keys are [available to Heroku](https://devcenter.heroku.com/articles/keys)
2. Heroku'ify the seed application
   * use the `detachme.sh` script to make the subdir into a separate repository: `sh detachme.sh`
   * create the heroku app: `heroku create`
3. Provision Neo4j Add-on
   * `heroku addons:add neo4j`
   * Give the database a minute to start up
3. Deploy to Heroku
   * `git push heroku master`
4. Make sure that it launched successfully
   * `heroku ps`
   * Any problems? Check `heroku logs`
5. Browse your application
   * `heroku open`
