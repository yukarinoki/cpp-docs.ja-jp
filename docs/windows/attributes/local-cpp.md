---
title: ローカル (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: e24efe4d4ad4f4e28b93503ecf82936e3113c1ed
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791954"
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

参照してください[call_as](call-as.md)を使用する方法の例については**ローカル**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**インターフェイス**、インターフェイス メソッド|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`dispinterface`|

詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[call_as](call-as.md)  