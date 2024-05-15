require "rake"
require "logger"

logger = Logger.new($stdout)

task :update do
  Dir.glob("charts/*").each do |app|
    logger.info("Updating #{app}")
    `cd #{app} && helm dependency update`
  end
end

task :create, [:application] do |t, args|
  puts "Create argo project for #{args.application}"
  command = "argocd app create #{args.application} \
    --repo https://gitlab.com/neutronium-external/app-of-apps-demo.git \
    --path #{args.application} \
    --dest-server https://kubernetes.default.svc \
    --dest-namespace #{args.application}"
  `#{command}`
end
