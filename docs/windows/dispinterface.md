---
title: dispinterface |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.dispinterface
dev_langs:
- C++
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 873527b76e9194fb4b38ee2f5598cf07028e0449
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591512"
---
# <a name="dispinterface"></a>dispinterface

ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。

## <a name="syntax"></a>構文

```cpp
[dispinterface]
```

## <a name="remarks"></a>Remarks

**dispinterface** C++ 属性がインターフェイスの前にあると、インターフェイスは生成される .idl ファイルのライブラリ ブロック内に配置されます。

基底クラスを指定しないと、ディスパッチ インターフェイスは `IDispatch`から派生します。 ディスパッチ インターフェイスのメンバーの [id](../windows/id.md) を指定する必要があります。

MIDL のドキュメントには [dispinterface](http://msdn.microsoft.com/library/windows/desktop/aa366802) の次のような使用例があります。

```cpp
dispinterface helloPro
   { interface hello; };
```

これは、 **dispinterface** 属性の有効な使用方法ではありません。

## <a name="example"></a>例

[dispinterface](../windows/bindable.md) の使用方法の例については、 **bindable**の例を参照してください。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[使用法別の属性](../windows/attributes-by-usage.md)  
[uuid](../windows/uuid-cpp-attributes.md)  
[dual](../windows/dual.md)  
[custom](../windows/custom-cpp.md)  
[object](../windows/object-cpp.md)  
[__interface](../cpp/interface.md)  