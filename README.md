```java

package luajx;

import luajx.func.util.ListFunction;
import org.luaj.vm2.LuaValue;
import org.luaj.vm2.lib.TwoArgFunction;

public class util extends TwoArgFunction {
    public static final String ListGetNumberAtIndex = "ListGetNumberAtIndex";
    
    @Override
    public org.luaj.vm2.LuaValue call(LuaValue moduleName, org.luaj.vm2.LuaValue env) {
        LuaValue library = LuaValue.tableOf();
        library.set(ListGetNumberAtIndex, new ListFunction.GetNumberAtIndex());
        env.set("util", library);
        return library;
    }
}




e.eval(
  "require 'luajx.util' " +
  "output = util.ListGetNumberAtIndex(input_array, 0) "
);

```

#### How to access Array in Lua
```java
 Map<String, Object> data = new HashMap<>();
        e.put("output", 0);
        e.put("input_array", Arrays.asList(1, 2L, 3.0f, 4.0, 5.1, 6.1, longValue).toArray());


        e.eval("output = input_array[1] ");
        assertEquals(1, e.get("output"));
```
