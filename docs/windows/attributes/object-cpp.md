---
title: object (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.object
helpviewer_keywords:
- object attribute
ms.assetid: f2d3c231-630d-4b4c-bd15-b1c30df362dd
ms.openlocfilehash: c0c0ff552d8a33ebe70f56b9b186e963cc8e9b3d
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843106"
---
# <a name="object-c"></a>object (C++)

カスタムインターフェイスを識別します。

## <a name="syntax"></a>構文

```cpp
[object]
```

## <a name="remarks"></a>解説

インターフェイス定義の前に **オブジェクト** C++ 属性を指定すると、インターフェイスはカスタムインターフェイスとして .idl ファイルに配置されます。

オブジェクトでマークされたインターフェイスは、から継承する必要があり `IUnknown` ます。 この条件は、いずれかの基本インターフェイスがから継承している場合に満たされ `IUnknown` ます。 基底インターフェイスがから継承されていない場合 `IUnknown` 、コンパイラは、 **オブジェクト** でマークされたインターフェイスをから派生させ `IUnknown` ます。

## <a name="example"></a>例

**オブジェクト**の使用方法の例については、「[非ブラウズ](nonbrowsable.md)」を参照してください。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**interface**|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[dual](dual.md)<br/>
[dispinterface](dispinterface.md)<br/>
[ショー](custom-cpp.md)<br/>
[__interface](../../cpp/interface.md)
