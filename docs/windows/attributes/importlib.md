---
title: importlib (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importlib
helpviewer_keywords:
- importlib attribute
ms.assetid: f129e459-b8d3-4aca-a0bc-ee53e18b62ed
ms.openlocfilehash: 451204aae52d884b9cbc81d7e589028f5cfefae5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80166810"
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

## <a name="remarks"></a>解説

**Importlib** C++属性を指定すると、生成された .idl ファイルのライブラリブロックに `importlib` ステートメントが配置されます。 **Importlib**属性には、 [importlib](/windows/win32/Midl/importlib) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

次のコードは、 **importlib**の使用方法の例を示しています。

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

## <a name="see-also"></a>参照

[コンパイラ属性](compiler-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)
