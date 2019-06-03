# Axway-Amplify-Mesh-Init

## Create the needed namespaces
```Shell
kubectl create namespace istio-system #if not existing
kubectl create namespace apic-control #if not exisiting
```

## Run the Init
```Shell
# (Optional) If you specify gatewayHost, a self signed certificate will be created for your gateway Host.
install https://github.com/asayah/Axway-Amplify-Mesh-Init/releases/download/0.1/Axway-Amplify-Mesh-Init-0.1.0.tgz --set gatewayHost=foo.com
```

## Start the init (Form github Repo)

```Shell
git clone https://github.com/asayah/Axway-Amplify-Mesh-Init
# (Optional) If you specify gatewayHost, a self signed certificate will be created for your gateway Host. 
helm install . -n apic-init --set gatewayHost=example.com
```

## If You want to use diffrents namespaces

```Shell
git clone https://github.com/asayah/Axway-Amplify-Mesh-Init
kubectl create namespace foo
kubectl create namespace bar
# (Optional) If you specify gatewayHost, a self signed certificate will be created for your gateway Host. 
helm install https://github.com/asayah/Axway-Amplify-Mesh-Init/releases/download/0.1/Axway-Amplify-Mesh-Init-0.1.0.tgz -n apic-init --set gatewayHost=example.com --set apic.namespace=foo --set istio.namespace=bar
```