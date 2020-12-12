---
description: '詳細情報: ディスパッチインターフェイス'
title: ディスパッチインターフェイス (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dispinterface
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
ms.openlocfilehash: fe39e537ccbc350f3733653a710dfd0f0d817339
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122136"
---
# <a name="dispinterface"></a>dispinterface

ディスパッチ インターフェイスとしてインターフェイスを .idl ファイルに配置します。

## <a name="syntax"></a>構文

```cpp
[dispinterface]
```

## <a name="remarks"></a>解説

**dispinterface** C++ 属性がインターフェイスの前にあると、インターフェイスは生成される .idl ファイルのライブラリ ブロック内に配置されます。

基底クラスを指定しないと、ディスパッチ インターフェイスは `IDispatch`から派生します。 ディスパッチ インターフェイスのメンバーの [id](id.md) を指定する必要があります。

MIDL のドキュメントには [dispinterface](/windows/win32/Midl/dispinterface) の次のような使用例があります。

```cpp
dispinterface helloPro
   { interface hello; };
```

これは、 **dispinterface** 属性の有効な使用方法ではありません。

## <a name="example"></a>例

[dispinterface](bindable.md) の使用方法の例については、 **bindable** の例を参照してください。

## <a name="requirements"></a>要件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|**interface**|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|`dual`, `object`, `oleautomation`, `local`, `ms_union`|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[使用法別の属性](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[×](dual.md)<br/>
[ショー](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)
