---
title: オブジェクト (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 9e1cf7f100c34023e6fea96c9764cce2371dcaaf
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46412693"
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

参照してください[nonbrowsable](../windows/nonbrowsable.md)を使用する方法の例については**オブジェクト**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)<br/>
[インターフェイス属性](../windows/interface-attributes.md)<br/>
[dual](../windows/dual.md)<br/>
[dispinterface](../windows/dispinterface.md)<br/>
[custom](../windows/custom-cpp.md)<br/>
[__interface](../cpp/interface.md)  