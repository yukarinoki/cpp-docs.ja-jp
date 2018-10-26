---
title: オブジェクト (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.object
dev_langs:
- C++
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8828ada429875245d583c30d65259300a01f6a5d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067437"
---
# <a name="object-c"></a>object (C++)

カスタム インターフェイスを識別します。

## <a name="syntax"></a>構文

```cpp
[object]
```

## <a name="remarks"></a>Remarks

インターフェイス定義の直前、**オブジェクト**C++ 属性により、インターフェイスのカスタム インターフェイスとして .idl ファイル内に配置されます。

オブジェクトでマークされた任意のインターフェイスを継承する必要があります`IUnknown`します。 継承する基本インターフェイスのいずれかの場合、この条件が満たされる`IUnknown`します。 基底インターフェイスを継承しない場合`IUnknown`、コンパイラでマークされたインターフェイスと、**オブジェクト**から派生する`IUnknown`します。

## <a name="example"></a>例

参照してください[nonbrowsable](nonbrowsable.md)を使用する方法の例については**オブジェクト**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[custom](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)