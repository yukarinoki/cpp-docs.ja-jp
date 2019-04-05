---
title: custom (C++)
ms.date: 11/04/2016
f1_keywords:
- vc-attr.custom
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
ms.openlocfilehash: 227e67696e679452a9c6c0e18c04e3d918f7a93f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/05/2019
ms.locfileid: "59029435"
---
# <a name="custom-c"></a>custom (C++)

タイプ ライブラリ内のオブジェクトのメタデータを定義します。

## <a name="syntax"></a>構文

```cpp
[ custom(
   uuid,
   value
) ];
```

### <a name="parameters"></a>パラメーター

*uuid*<br/>
一意の ID。

*値*<br/>
バリアントを入れる値。

## <a name="remarks"></a>Remarks

**カスタム**情報をタイプ ライブラリに格納すると、C++ 属性。 ツールをタイプ ライブラリからカスタムの値を読み取る必要があります。

**カスタム**属性と同じ機能を持つ、[カスタム](/windows/desktop/Midl/custom)MIDL 属性。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|非 COM**インターフェイス**、**クラス**、**列挙**s、`idl_module`メソッド、インターフェイスのメンバー、インターフェイスのパラメーター、 **typedef**、s**共用体**s、**構造体**s|
|**反復可能**|はい|
|**必要な属性**|**コクラス**(クラスで使用) 場合|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)