---
title: カスタム (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.custom
dev_langs:
- C++
helpviewer_keywords:
- custom attributes, defining
ms.assetid: 3abac928-4d55-4ea6-8cf6-8427a4ad79f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5a491c120dff7f8f505878d6887498eb5f05fb22
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791431"
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

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|非 COM**インターフェイス**、**クラス**、**列挙**s、`idl_module`メソッド、インターフェイスのメンバー、インターフェイスのパラメーター、 **typedef**、s**共用体**s、**構造体**s|
|**反復可能**|はい|
|**必要な属性**|**コクラス**(クラスで使用) 場合|
|**無効な属性**|なし|

属性コンテキストの詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[IDL 属性](idl-attributes.md)<br/>
[スタンドアロン属性](stand-alone-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[パラメーター属性](parameter-attributes.md)<br/>
[メソッド属性](method-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[インターフェイス属性](interface-attributes.md)  