---
title: immediatebind (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 76a0a6baec4f775d2ec4f7ca0236530125fe7973
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083413"
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

参照してください[バインド可能な](bindable.md)を使用する方法の例については**immediatebind**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[defaultbind](defaultbind.md)<br/>
[displaybind](displaybind.md)<br/>
[requestedit](requestedit.md)