# Java

## De-serialization approach 

Find vulnerable code, i.e. using ObjectInputStream maybe ?

figure out if the application depends on vulnerable libraries \([https://github.com/frohoff/ysoserial](https://github.com/frohoff/ysoserial)\) -&gt;

searched for all \*.jar files in lib and bin etc....

generate payload example

```text
java -jar ysoserial-master-6eca5bc740-1.jar CommonsCollections3 calc.exe > payload.bin
```

