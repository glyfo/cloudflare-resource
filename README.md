# Cloudflare Resource

This page review Cloudflare Resource and how use into the Cloudflare Workers

###  Detail Resource 

+ Workers KV 
+ Durable Object 
+ R2
+ D1 

#### Workers KV  

Workers KV is a global, low-latency, key-value data store. It stores data in a small number of centralized data centers, then caches that data in Cloudflare’s data centers after access. 

https://developers.cloudflare.com/workers/learning/how-kv-works/

##### 1- Read KV Typescript

```code
interface Env {
  TODO_LIST: KVNamespace;
}
export const onRequest: PagesFunction<Env> = async (context) => {
  const task = await context.env.TODO_LIST.get("Task:123");
  return new Response(task);
}

```

##### 2- Write KV


```code
interface Env {
  TODO_LIST: KVNamespace;
}
export const onRequest: PagesFunction<Env> = async (context) => {
  const result = await context.env.TODO_LIST.put("data", JSON.stringify(defaultData))
  return new Response(result);
}

```

#### Durable Object  

Cloudflare’s Durable Object storage solution. 

#### R2 

Cloudflare’s R2 storage solution. 

#### D1 

Cloudflare’s D1 storage solution. 


### Resource 

https://github.com/cloudflare/wrangler2
https://developers.cloudflare.com/pages/platform/functions/bindings/
