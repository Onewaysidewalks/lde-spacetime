print("""
-----------------------------------------------------------------
✨ Spacetime + Unity LDE
-----------------------------------------------------------------
""".strip())

# Ensure spacetime is up and running on port 3000 for the host
k8s_yaml(['spacetime.yaml'])
k8s_resource('spacetime', port_forwards=['3000:3000'])

# Ensure spacetime cli installed and terminal-browser available
docker_build('console', 'console/', dockerfile='console/Dockerfile')
k8s_yaml('console/console_k8s.yaml')
k8s_resource('console', objects=[], port_forwards=['7681:7681'], resource_deps=["spacetime"])
