# coding: utf-8
require 'aws-sdk-cloudfront'
require 'aws-sdk-s3'
require 'jekyll'
require 'yaml'

deploy_config = YAML.load_file('deploy_config.yml')

# Extend string to allow for bold text.
class String
  def bold
    "\033[1m#{self}\033[0m"
  end
end

# Rake Jekyll tasks
task :build do
  puts 'Building _site...'.bold
  Jekyll::Commands::Build.process(profile: true)
end

task :clean do
  puts 'Cleaning up _site...'.bold
  Jekyll::Commands::Clean.process({})
end

task :serve do
  puts 'Starting local webserver...'.bold
  Jekyll::Commands::Serve.process({})
end


# Rake AWS tasks
# Be sure your credentials are set in ~/.aws/credentials or in appropriate environment variables
task :s3_upload do
  puts 'Deploying to S3...'.bold
  s3 = Aws::S3::Client.new()
  Dir["_site/**/*"].each do |file|
    next if File.directory?(file)
    puts "Uploading file #{file}"
    s3.put_object({key:file.split('/', 2)[1], body:File.read(file), bucket:deploy_config['deploy']['s3_bucket']})
  end
end

task :cloudfront_invalidation do
  puts 'Invalidating Cloudfront cache...'.bold
  cloudfront = Aws::CloudFront::Client.new()
  cloudfront.create_invalidation({
    distribution_id: deploy_config['deploy']['cloudfront_distribution'],
    invalidation_batch: {
      paths: {
        quantity: 1,
        items: ['/*'],
      },
    caller_reference: Time.now.to_i.to_s,
    }
  })
  puts 'Invalidation Sent'.bold
end

task :deploy => [:clean, :build, :s3_upload, :cloudfront_invalidation]