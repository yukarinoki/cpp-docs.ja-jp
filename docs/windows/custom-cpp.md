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
ms.openlocfilehash: 848ea415d0638b6135c69cd14e442f45dab40237
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220362"
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

*uuid*  
一意の ID。

*値*  
バリアントを入れる値。

## <a name="remarks"></a>Remarks

**カスタム**情報をタイプ ライブラリに格納すると、C++ 属性。 ツールをタイプ ライブラリからカスタムの値を読み取る必要があります。

**カスタム**属性と同じ機能を持つ、[カスタム](/windows/desktop/Midl/custom)MIDL 属性。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|非 COM**インターフェイス**、**クラス**、**列挙**s、`idl_module`メソッド、インターフェイスのメンバー、インターフェイスのパラメーター、 **typedef**、s**共用体**s、**構造体**s|
|**反復可能**|[はい]|
|**必要な属性**|**コクラス**(クラスで使用) 場合|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[IDL 属性](../windows/idl-attributes.md)  
[スタンドアロン属性](../windows/stand-alone-attributes.md)  
[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)  
[パラメーター属性](../windows/parameter-attributes.md)  
[メソッド属性](../windows/method-attributes.md)  
[クラス属性](../windows/class-attributes.md)  
[インターフェイス属性](../windows/interface-attributes.md)  