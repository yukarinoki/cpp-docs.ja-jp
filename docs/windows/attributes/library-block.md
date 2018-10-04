---
title: library_block (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.library_block
dev_langs:
- C++
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf4bcdd9290817bb77eeb20f1a014bd537d15d8b
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791719"
---
# <a name="libraryblock"></a>library_block

IDL ライブラリ ブロック内の構造を配置します。

## <a name="syntax"></a>構文

```cpp
[library_block]
```

## <a name="remarks"></a>Remarks

ライブラリ ブロック内の構造を配置するときに参照されているかどうかに関係なく、タイプ ライブラリに渡されることを確認します。 既定では、唯一の構造の変更によって、[コクラス](coclass.md)、 [dispinterface](dispinterface.md)、および[idl_module](idl-module.md)属性は、ライブラリ ブロックに配置されます。

## <a name="example"></a>例

次のコードでは、カスタム インターフェイスはライブラリ ブロック内に配置します。

```cpp
// cpp_attr_ref_library_block.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib")];
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface IMyInterface {
   HRESULT f1();
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|任意の場所|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)  