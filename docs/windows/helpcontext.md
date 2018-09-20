---
title: helpcontext |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: d9c2efecf34e5d58f633bc21e62801157b1b8955
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46388590"
---
# <a name="helpcontext"></a>helpcontext

ユーザーには、この要素に関する情報を表示できるようにコンテキスト ID を指定します、**ヘルプ**ファイル。

## <a name="syntax"></a>構文

```cpp
[ helpcontext(
   id
) ]
```

### <a name="parameters"></a>パラメーター

*ID*<br/>
ヘルプ トピックのコンテキスト ID。 参照してください[HTML ヘルプ: プログラムの状況依存のヘルプ](../mfc/html-help-context-sensitive-help-for-your-programs.md)コンテキスト Id の詳細についてはします。

## <a name="remarks"></a>Remarks

**Helpcontext** C++ 属性と同じ機能を持つ、 [helpcontext](/windows/desktop/Midl/helpcontext) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[defaultvalue](../windows/defaultvalue.md)を使用する方法の例については**helpcontext**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**インターフェイス**、 **typedef**、**クラス**メソッド、プロパティ|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[インターフェイス属性](../windows/interface-attributes.md)<br/>
[クラス属性](../windows/class-attributes.md)<br/>
[メソッド属性](../windows/method-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](../windows/helpfile.md)<br/>
[helpstring](../windows/helpstring.md)  