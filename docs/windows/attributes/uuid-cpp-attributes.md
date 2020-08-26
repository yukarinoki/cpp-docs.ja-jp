---
title: uuid (C++ 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.uuid
helpviewer_keywords:
- uuid attribute
ms.assetid: 90562a94-5e28-451b-a4b0-cadda7f66efe
ms.openlocfilehash: 9ff8888c26945d7f118e71002e3b3290217b463c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843041"
---
# <a name="uuid-c-attributes"></a>uuid (C++ 属性)

クラスまたはインターフェイスの一意の ID を指定します。

## <a name="syntax"></a>構文

```cpp
[ uuid( "uuid" ) ]
```

### <a name="parameters"></a>パラメーター

*uuid*<br/>
128ビットの一意の識別子。

## <a name="remarks"></a>解説

インターフェイスまたはクラスの定義で C++ 属性が指定されていない場合は、 `uuid` Microsoft c++ コンパイラによって提供されます。 を指定する場合は、 `uuid` 引用符を含める必要があります。

を指定しないと `uuid` 、コンピューター上の異なる属性プロジェクトで同じ名前を持つインターフェイスまたはクラスに対して、コンパイラによって同じ GUID が生成されます。

Uuidgen.exe または Guidgen.exe を使用して、独自の一意の Id を生成できます。 (これらのツールのいずれかを実行するには、[ **スタート** ] ボタンをクリックし、メニューの [ **実行** ] をクリックします。 次に、必要なツールの名前を入力します)。

ATL を使用しないプロジェクトで使用する場合、属性を指定すること `uuid` は [uuid](../../cpp/uuid-cpp.md)修飾子を指定することと同じです **`__declspec`** 。 クラスのを取得するに `uuid` は、を使用し [__uuidof](../../cpp/uuidof-operator.md)

## <a name="example"></a>例

の使用例については、 [バインド](bindable.md) 可能な例を参照してください `uuid` 。

## <a name="requirements"></a>必要条件

| 属性コンテキスト | 値 |
|-|-|
|**適用対象**|`class`, `struct`, `interface`, `union`, `enum`|
|**Repeatable**|いいえ|
|**必須属性**|なし|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 属性](typedef-enum-union-and-struct-attributes.md)<br/>
[uuid](/windows/win32/Midl/uuid)
