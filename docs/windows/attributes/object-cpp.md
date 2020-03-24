---
title: object (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.object
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
ms.openlocfilehash: 4545d899c13a1eabf8ea5fb6fe3918fb5f05b626
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214681"
---
# <a name="object-c"></a>object (C++)

カスタムインターフェイスを識別します。

## <a name="syntax"></a>構文

```cpp
[object]
```

## <a name="remarks"></a>解説

インターフェイス定義の前では、**オブジェクト** C++属性によってインターフェイスが .idl ファイル内にカスタムインターフェイスとして配置されます。

オブジェクトでマークされたインターフェイスは、`IUnknown`から継承する必要があります。 この条件は、いずれかの基本インターフェイスが `IUnknown`から継承している場合に満たされます。 `IUnknown`から継承する基本インターフェイスがない場合、コンパイラは、**オブジェクト**でマークされたインターフェイスを `IUnknown`から派生させます。

## <a name="example"></a>例

**オブジェクト**の使用方法の例については、「[非ブラウズ](nonbrowsable.md)」を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[custom](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)
