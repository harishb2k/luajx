# luajx

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
