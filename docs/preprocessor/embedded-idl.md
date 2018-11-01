---
title: embedded_idl
ms.date: 10/18/2018
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: 202d5b23a5e2e8e673e3c220b9618cfe6cd4f0d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525607"
---
# <a name="embeddedidl"></a>embedded_idl

**C++ 固有の仕様**

属性が生成されたコードを保持して、タイプ ライブラリを .tlh ファイルに書き込むことを指定します。

## <a name="syntax"></a>構文

```
embedded_idl[("param")]
```

### <a name="parameters"></a>パラメーター

*param*<br/>
次の 2 つの値のいずれかを指定します。

- **emitidl**: typelib からインポートされた情報は、属性付きプロジェクト用に生成された IDL に表示されます。  これは既定値であり、`embedded_idl` にパラメーターを指定しない場合に有効になります。

- **no_emitidl**: typelib からインポートされた情報は、属性付きプロジェクト用に生成された IDL に存在できません。

## <a name="example"></a>例

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

## <a name="remarks"></a>Remarks

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)