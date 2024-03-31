services = ['users', 'users-worker', 'redis', 'postgres', 'ingress']
yaml_files = ["k8s/%s.yaml" % service for service in services]

k8s_yaml(yaml_files)
docker_build('users', 'FastApi-boilerplate', dockerfile='FastAPI-boilerplate/docker/Dockerfile')
docker_build('users-worker', 'FastApi-boilerplate', dockerfile='FastAPI-boilerplate/docker/worker.dockerfile')
k8s_resource(workload="users-deployment", port_forwards="8000:80")
