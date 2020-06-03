---
title: ディスパッチインターフェイスC++ (COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.dispinterface
helpviewer_keywords:
- dispinterface attribute
ms.assetid: 61c5a4a1-ae92-47e9-8ee4-f847be90172b
ms.openlocfilehash: 66567b0a1b043136e0a754e3a52bbdd7c463e178
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80168240"
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

[dispinterface](bindable.md) の使用方法の例については、 **bindable**の例を参照してください。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**interface**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|`dual`、`object`、`oleautomation`、`local`、`ms_union`|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>参照

[IDL 属性](idl-attributes.md)<br/>
[使用法別の属性](attributes-by-usage.md)<br/>
[uuid](uuid-cpp-attributes.md)<br/>
[dual](dual.md)<br/>
[custom](custom-cpp.md)<br/>
[object](object-cpp.md)<br/>
[__interface](../../cpp/interface.md)
