---
title: immediatebind |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.immediatebind
dev_langs:
- C++
helpviewer_keywords:
- immediatebind attribute
ms.assetid: 186d40e6-9166-4d0c-9853-4e7e4d25226f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dc4c42132b2b964d0606fc3287e9d9fd98d64370
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46400740"
---
# <a name="immediatebind"></a>immediatebind

データ バインド オブジェクトのプロパティに対するすべての変更のデータベースに直ちに通知されることを示します。

## <a name="syntax"></a>構文

```cpp
[immediatebind]
```

## <a name="remarks"></a>Remarks

**Immediatebind** C++ 属性と同じ機能を持つ、 [immediatebind](/windows/desktop/Midl/immediatebind) MIDL 属性。

## <a name="example"></a>例

参照してください[バインド可能な](../windows/bindable.md)を使用する方法の例については**immediatebind**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[メソッド属性](../windows/method-attributes.md)<br/>
[defaultbind](../windows/defaultbind.md)<br/>
[displaybind](../windows/displaybind.md)<br/>
[requestedit](../windows/requestedit.md)  