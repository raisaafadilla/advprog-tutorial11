# Tutorial 11

## Reflection on Hello Minikube

1. Compare the application logs before and after you exposed it as a Service. What do you see in the logs? Does the number of logs increase each time you open the app?
   
**Before Exposure**

<img width="572" alt="Screenshot 2024-05-15 at 5 05 34 PM" src="https://github.com/raisaafadilla/advprog-tutorial11/assets/134634814/a7dd7f40-93b0-4a9c-8c77-f77dcc02e2fa">

**After Exposure**

<img width="529" alt="Screenshot 2024-05-15 at 5 45 55 PM" src="https://github.com/raisaafadilla/advprog-tutorial11/assets/134634814/c212fc76-e002-46fe-80de-ef6e1a4504e3">

After the application was exposed as a service, the logs not only include the initial startup sequence but also record multiple GET / requests. Each of these entries represents a new interaction or request received by the server. Consequently, the logs show an increased number of entries, indicating that the application is actively handling incoming HTTP requests.

2. Notice that there are two versions of `kubectl get` invocation during this tutorial section. The first does not have any option, while the latter has `-n` option with value set to `kube-system`. What is the purpose of the `-n` option and why did the output not list the pods/services that you explicitly created?

The `-n` option in the `kubectl get` command serves to specify a namespace for filtering resources within a Kubernetes cluster. For instance, when running `kubectl get services` without the `-n` option, it defaults to the default namespace, displaying resources such as `hello-node`, as seen in tutorials. Conversely, utilizing `kubectl get pods,services -n kube-system` directs the command to the kube-system namespace, which hosts critical system processes. Consequently, any pods and services created, likely in the default namespace, would not be visible in the output of the latter command.

