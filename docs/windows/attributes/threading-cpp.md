---
title: スレッド (C++ COM 属性) |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.threading
dev_langs:
- C++
helpviewer_keywords:
- threading attribute
ms.assetid: 9b558cd6-fbf0-4602-aed5-31c068550ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 85ffa775fd18b6979fccf4354ce243f017634d02
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/25/2018
ms.locfileid: "50059676"
---
# <a name="threading-c"></a>threading (C++)

COM オブジェクトのスレッド モデルを指定します。

## <a name="syntax"></a>構文

```cpp
[ threading(model=enumeration) ]
```

### <a name="parameters"></a>パラメーター

*model*<br/>
(省略可能)次のスレッド モデルのいずれか:

- `apartment` (アパートメント スレッド)

- `neutral` (ユーザー インターフェイスを持たないコンポーネントを .NET framework)

- `single` (簡易スレッド)

- `free` (フリー スレッド)

- `both` (アパートメントとフリー スレッド)

既定値は `apartment` です。

## <a name="remarks"></a>Remarks

**スレッド**C++ 属性が生成された .idl ファイルに表示されないが、COM オブジェクトの実装で使用されます。

、ATL プロジェクトの場合、[コクラス](coclass.md)属性が存在することもによって指定されたスレッド処理モデル*モデル*をテンプレート パラメーターとして渡される、 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)クラス、によって挿入された、`coclass`属性。

**スレッド**属性もへのアクセスを保護する[event_source](event-source.md)します。

## <a name="example"></a>例

参照してください、[ライセンス](licensed.md)の使用サンプルの例を**スレッド**します。

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|**coclass**|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[COM 属性](com-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)<br/>
[クラス属性](class-attributes.md)<br/>
[旧形式のコードのためのマルチスレッド サポート (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)<br/>
[ニュートラル アパートメント](/windows/desktop/cossdk/neutral-apartments)