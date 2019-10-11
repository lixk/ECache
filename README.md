# ECache
simple memory cache for Java
# method description
| method | description |
| :--- | :--- |
| put(key, value) | put data to cache |
| put(key, value, expire) | put data to cache with expire. `expire`: data survival time in milliseconds |
| get(key) | get data from cache |
| remove(key) | remove data from cache |

# usage
```java
public class ECacheTest {
 	public static void main(String[] args) throws InterruptedException {
 		ECache.put("id", 123);
 		Integer id = ECache.get("id");
 		System.out.println(id);
 
 		ECache.put("id", 123, 3000);
 		id = ECache.get("id");
 		System.out.println(id);
 		Thread.sleep(3001);
 		id = ECache.get("id");
 		System.out.println("expired id:"+id);
 	}
 }
```
# performance
Number of key-values for test: `100,0000`

**put**: take about `2000` milliseconds

**get**: take about `300` milliseconds

