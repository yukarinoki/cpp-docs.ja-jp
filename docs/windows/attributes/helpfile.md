---
title: helpfile (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpfile
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
ms.openlocfilehash: 641823779346bf5417ec0db26b83083fa949e960
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87222122"
---
# <a name="helpfile"></a>helpfile

タイプライブラリのヘルプファイルの名前を設定します。

## <a name="syntax"></a>構文

```cpp
[ helpfile("filename") ]
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
ヘルプトピックが含まれているファイルの名前。

## <a name="remarks"></a>解説

**Helpfile** C++ 属性には、 [helpfile](/windows/win32/Midl/helpfile) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Helpfile**の使用例については、[モジュール](module-cpp.md)の例を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**適用対象**|**インターフェイス**、 **`typedef`** 、 **`class`** 、メソッド、**`property`**|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)<br/>
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)
