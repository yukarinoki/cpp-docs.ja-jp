---
title: ディスパッチ インターフェイス (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 3b02244e0576f99cc0a6940f2ee4a13511cfbe6f
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791102"
---
# <a name="dispinterface"></a>dispinterface

ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。

## <a name="syntax"></a>構文

```cpp
[dispinterface]
```

## <a name="remarks"></a>Remarks

**dispinterface** C++ 属性がインターフェイスの前にあると、インターフェイスは生成される .idl ファイルのライブラリ ブロック内に配置されます。

基底クラスを指定しないと、ディスパッチ インターフェイスは `IDispatch`から派生します。 指定する必要があります、 [id](id.md)ディスパッチ インターフェイスのメンバー。

使用例[dispinterface](/windows/desktop/Midl/dispinterface) MIDL のドキュメントで。

```cpp
dispinterface helloPro
   { interface hello; };
```

これは、 **dispinterface** 属性の有効な使用方法ではありません。

## <a name="example"></a>例

例をご覧ください[バインド可能な](bindable.md)を使用する方法の例については**dispinterface**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[使用法別の属性](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[dual](dual.md)<br/>
[custom](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)  