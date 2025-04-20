
Service object operates at OSI level 4 while Ingress at level 7.
	CMD to look up where to the service route the traffic.  
		`kubectl get endpoints chat-server-service`

**Ingress** routes requests based on host/path to the appropriate **service**. It can also handle WebSocket connections, provided the Ingress Controller supports it. A **Service** does not manage protocol-level features like WebSockets — it simply forwards traffic to pods.
 ingress-config.yaml
	`apiVersion: networking.k8s.io/v1`
	`kind: Ingress`
	`metadata:`
	  `name: my-ingress`
	  `namespace: default`
	  `annotations:`
	    `nginx.ingress.kubernetes.io/rewrite-target: /`
	`spec:`
	  `ingressClassName: nginx  # depends on your Ingress Controller`
	  `rules:`
	    `- host: example.com`
	      `http:`
	        `paths:`
	          `- path: /app1`
	            `pathType: Prefix`
	            `backend:`
	              `service:`
	                `name: app1-service`
	                `port:`
	                  `number: 80`
	          `- path: /app2`
	            `pathType: Prefix`
	            `backend:`
	              `service:`
	                `name: app2-service`
	                `port:`
	                  `number: 80`
	    `- host: api.example.com`
	      `http:`
	        `paths:`
	          `- path: /`
	            `pathType: Prefix`
	            `backend:`
	              `service:`
	                `name: api-service`
	                `port:`
	                  `number: 8080`
