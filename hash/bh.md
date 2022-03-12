> English

**Name**: basic_hash

**About**: A kind of slow hash method that helps make it harder for attackers to duplicate user password or start too many requests

**Parameters**:

|Name|Type|Descryption|Other Information|
|----|----|-----------|-----------------|
|data|string|data needed to be hashed||
|grade|uint|security grade for the hash|**·** The maximum value for this parameter is 64<br>**·** The bigger this number is, the slower the hash works, which makes it harder to duplicate. However, the efficiency of the program is also decreased|

**How It Works**:

Finds a string `hash_str` with only characters from `'0'` to `'9'` that makes the `sha256` value of the string `(data+hash_str)` begins with `grade` `'0'`s
