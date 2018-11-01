---
title: helpfile (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpfile
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
ms.openlocfilehash: 594ab4d02065e9b4efe1142c5ced9b76642e5481
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488050"
---
# <a name="helpfile"></a>helpfile

タイプ ライブラリのヘルプ ファイルの名前を設定します。

## <a name="syntax"></a>構文

```cpp
[ helpfile("filename") ]
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
ヘルプ トピックを含むファイルの名前。

## <a name="remarks"></a>Remarks

**Helpfile** C++ 属性と同じ機能を持つ、 [helpfile](/windows/desktop/Midl/helpfile) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[モジュール](module-cpp.md)を使用する方法の例については**helpfile**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**インターフェイス**、 **typedef**、**クラス**、メソッド、**プロパティ**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)