# Kubernetes Manifests for Application Deployment

This repository contains four Kubernetes YAML manifests used to deploy an application, expose it via a service, configure Ingress for external access, and manage TLS certificates using Cert-Manager.

## Files Overview

1. **deployment.yaml**:
   - Defines a Kubernetes `Deployment` for the application.
   - Specifies the number of replicas, the container image, and other settings.
   - Ensures that the application pods are running and managed by Kubernetes.

2. **service.yaml**:
   - Defines a Kubernetes `Service` to expose the application within the cluster.
   - Provides stable access to the application pods by grouping them under a common endpoint.
   - Usually of type `ClusterIP` or `NodePort` depending on your setup.

3. **ingress.yaml**:
   - Configures an `Ingress` resource for routing external HTTP/HTTPS traffic to the service.
   - Specifies domain routing rules and enables TLS by referencing the `ClusterIssuer` for SSL certificates.
   - This file ensures the application is accessible via a domain and securely via HTTPS.

4. **issuer.yaml**:
   - Defines a `ClusterIssuer` resource for Cert-Manager.
   - Configures Cert-Manager to automatically issue and manage Let's Encrypt SSL certificates for your Ingress resource.
   - This ensures that your domain is secured with valid TLS certificates.
