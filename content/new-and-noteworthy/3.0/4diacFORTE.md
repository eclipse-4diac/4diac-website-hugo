---
title: 4diac FORTE

---

 - Support for ARRAYs with arbitrary boundaries [n..m]
 - Support for variable length ARRAYs [*]
 - Support for negated outputs ( => NOT)
 - Fixed casting behavior for type where binary transfer or sign extension is necessary
 - Added LTIME types
 - Improved partial ANY_BIT support (comparisons + assignments to partials (non standard))
 - Improved standard compliance for implicit and explicit casts
 - Improved STRING support (partial access)
 - Added all IEC 61131-3 standard functions
 - Added support for all variadic functions (MIN, MAX, CONCAT, ADD, MUL)
 - Fixed that now STRINGS and CHARS can be CONCATenated to a STRING
 - Improved return type support for FUNCTIONS with ANY-type return types
 - Added standard-conformant FOR loop
 - Support of high resolution clocks
 - Fixed representations of TIME data types and ANY_REAL types
 - Improved support for ANY type IN/OUTs
 - Fixed SHR/SHL/ROR/ROL to standard conformity
 - Fixed XOR corner case when BOOL is involved
 - Changed code base to C++20