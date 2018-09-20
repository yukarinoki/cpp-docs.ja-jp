---
title: ローカル (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.local
dev_langs:
- C++
helpviewer_keywords:
- local attribute
ms.assetid: 35cdd668-bd8e-492a-b7b8-263e7b662437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d0b45106609c4bc93684e0d89737bb0753e36fb4
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421090"
---
# <a name="local-c"></a>local (C++)

インターフェイスのヘッダーで使用されているときにジェネレーターをヘッダーとして、MIDL コンパイラを使用することができます。 個々 の関数で使用する場合は、スタブが生成されたないローカル プロシージャを指定します。

## <a name="syntax"></a>構文

```cpp
[local]
```

## <a name="remarks"></a>Remarks

**ローカル**C++ 属性と同じ機能を持つ、[ローカル](/windows/desktop/Midl/local)MIDL 属性。

## <a name="example"></a>例

参照してください[call_as](../windows/call-as.md)を使用する方法の例については**ローカル**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**インターフェイス**、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`dispinterface`|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[インターフェイス属性](../windows/interface-attributes.md)<br/>
[メソッド属性](../windows/method-attributes.md)<br/>
[call_as](../windows/call-as.md)  