---
title: helpfile |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpfile
dev_langs:
- C++
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 66cd89c28ea01c3a75d0cb25aa6f96a234e379b2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418204"
---
# <a name="helpfile"></a>helpfile

タイプ ライブラリのヘルプ ファイルの名前を設定します。

## <a name="syntax"></a>構文

```cpp
[ helpfile(
   "filename"
) ]
```

### <a name="parameters"></a>パラメーター

*ファイル名*<br/>
ヘルプ トピックを含むファイルの名前。

## <a name="remarks"></a>Remarks

**Helpfile** C++ 属性と同じ機能を持つ、 [helpfile](/windows/desktop/Midl/helpfile) MIDL 属性。

## <a name="example"></a>例

例をご覧ください[モジュール](../windows/module-cpp.md)を使用する方法の例については**helpfile**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**インターフェイス**、 **typedef**、**クラス**、メソッド、**プロパティ**|
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
[helpcontext](../windows/helpcontext.md)<br/>
[helpstring](../windows/helpstring.md)  