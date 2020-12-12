---
description: '詳細については、次を参照してください: library_block'
title: library_block (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.library_block
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
ms.openlocfilehash: 486c40fa8641e74b6e3bc72bc7f980e3ee1216e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97329825"
---
# <a name="library_block"></a>library_block

コンストラクターを IDL ライブラリブロック内に配置します。

## <a name="syntax"></a>構文

```cpp
[library_block]
```

## <a name="remarks"></a>解説

構造体をライブラリブロック内に配置すると、参照されているかどうかに関係なく、そのコンストラクトがタイプライブラリに渡されます。 既定では、 [コクラス](coclass.md)、 [ディスパッチインターフェイス](dispinterface.md)、および [idl_module](idl-module.md) 属性によって変更されたコンストラクトのみがライブラリブロックに配置されます。

## <a name="example"></a>例

次のコードでは、カスタムインターフェイスがライブラリブロック内に配置されています。

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

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|任意の場所|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)
