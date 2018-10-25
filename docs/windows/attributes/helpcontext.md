---
title: helpcontext (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpcontext
dev_langs:
- C++
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 831ca61f82eee913efd1ab2b1420fefb011d6c1a
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062835"
---
# <a name="helpcontext"></a>helpcontext

ユーザーには、この要素に関する情報を表示できるようにコンテキスト ID を指定します、**ヘルプ**ファイル。

## <a name="syntax"></a>構文

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>パラメーター

*ID*<br/>
ヘルプ トピックのコンテキスト ID。 参照してください[HTML ヘルプ: プログラムの状況依存のヘルプ](../../mfc/html-help-context-sensitive-help-for-your-programs.md)コンテキスト Id の詳細についてはします。

## <a name="remarks"></a>Remarks

**Helpcontext** C++ 属性と同じ機能を持つ、 [helpcontext](/windows/desktop/Midl/helpcontext) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[defaultvalue](defaultvalue.md)を使用する方法の例については**helpcontext**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**インターフェイス**、 **typedef**、**クラス**メソッド、プロパティ|
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
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)