print("""
-----------------------------------------------------------------
✨ Spacetime + Unity LDE
-----------------------------------------------------------------
""".strip())

# Ensure spacetime is up and running on port 3000 for the host
k8s_yaml(['spacetime.yaml'])
k8s_resource('spacetime', port_forwards=['3000:80'])
