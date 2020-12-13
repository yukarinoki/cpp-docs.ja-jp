---
description: 詳細については、「helpcontext」を参照してください。
title: helpcontext (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: cfedec2f7650490dd266331e6853ba47265aa4ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335724"
---
# <a name="helpcontext"></a>helpcontext

**ヘルプ** ファイル内のこの要素に関する情報をユーザーが表示できるようにするコンテキスト ID を指定します。

## <a name="syntax"></a>構文

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>パラメーター

*id*<br/>
ヘルプトピックのコンテキスト ID。 コンテキスト Id の詳細については [、「HTML ヘルプ: Context-Sensitive プログラムのヘルプ](../../mfc/html-help-context-sensitive-help-for-your-programs.md) 」を参照してください。

## <a name="remarks"></a>解説

**Helpcontext** C++ 属性には、 [helpcontext](/windows/win32/Midl/helpcontext) MIDL 属性と同じ機能があります。

## <a name="example"></a>例

**Helpcontext** の使用例については、 [defaultvalue](defaultvalue.md)の例を参照してください。

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**interface**、 **`typedef`** 、 **`class`** 、メソッド、プロパティ|
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
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)
