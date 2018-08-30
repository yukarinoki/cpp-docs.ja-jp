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
ms.openlocfilehash: dd546f6d3eb3b2eae60b4bbc8c8fa9b0b4ed00f1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201026"
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

[IDL 属性](../windows/idl-attributes.md)  
[メソッド属性](../windows/method-attributes.md)  
[defaultbind](../windows/defaultbind.md)  
[displaybind](../windows/displaybind.md)  
[requestedit](../windows/requestedit.md)  