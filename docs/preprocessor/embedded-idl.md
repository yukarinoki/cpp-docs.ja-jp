---
title: embedded_idl |Microsoft Docs
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- embedded_idl
dev_langs:
- C++
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7337595111b01ceeec53cc97f11ec2f35a081c5
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808343"
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