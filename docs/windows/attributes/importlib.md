---
title: importlib (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importlib
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
ms.openlocfilehash: d0bedb4bac91aa1a5aa72c8334db07aea0f04a97
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649879"
---
# <a name="importlib"></a>importlib

既に他のタイプ ライブラリでコンパイル済みの型を、作成中のタイプ ライブラリで使用できるようにします。

## <a name="syntax"></a>構文

```cpp
[ importlib("tlb_file") ];
```

### <a name="parameters"></a>パラメーター

*tlb_file*<br/>
現在のプロジェクトのタイプ ライブラリにインポートする .tlb ファイルの名前 (引用符で囲む)。

## <a name="remarks"></a>Remarks

**Importlib** C++ 属性によって、`importlib`ステートメントが生成された .idl ファイルのライブラリ ブロックに配置されます。 **Importlib**属性と同じ機能を持つ、 [importlib](/windows/desktop/Midl/importlib) MIDL 属性。

## <a name="example"></a>例

次のコードを使用する方法の例を示します**importlib**:

```cpp
// cpp_attr_ref_importlib.cpp
// compile with: /LD
[module(name="MyLib")];
[importlib("importlib.tlb")];
```

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)