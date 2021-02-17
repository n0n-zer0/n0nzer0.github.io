# Java

## De-serialization approach 

Find vulnerable code, i.e. using ObjectInputStream or XStream maybe ?

figure out if the application depends on vulnerable libraries \([https://github.com/frohoff/ysoserial](https://github.com/frohoff/ysoserial)\) -&gt;

searched for all \*.jar files in lib and bin etc....

generate payload example

```text
java -jar ysoserial-master-6eca5bc740-1.jar CommonsCollections3 calc.exe > payload.bin
```

also see:

{% embed url="https://blog.jamesotten.com/post/applications-manager-rce/" %}





