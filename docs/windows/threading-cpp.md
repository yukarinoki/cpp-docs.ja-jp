---
title: スレッド (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 700e8915535a38233b1cd1e55669c1e3c5f372dd
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42591554"
---
# <a name="threading-c"></a>threading (C++)

COM オブジェクトのスレッド モデルを指定します。

## <a name="syntax"></a>構文

```cpp
[ threading(
   model=enumeration
) ]
```

### <a name="parameters"></a>パラメーター

*モデル*(省略可能)  
次のスレッド モデルのいずれか:

- `apartment` (アパートメント スレッド)

- `neutral` (ユーザー インターフェイスを持たないコンポーネントを .NET framework)

- `single` (簡易スレッド)

- `free` (フリー スレッド)

- `both` (アパートメントとフリー スレッド)

既定値は `apartment` です。

## <a name="remarks"></a>Remarks

**スレッド**C++ 属性が生成された .idl ファイルに表示されないが、COM オブジェクトの実装で使用されます。

、ATL プロジェクトの場合、[コクラス](../windows/coclass.md)属性が存在することもによって指定されたスレッド処理モデル*モデル*をテンプレート パラメーターとして渡される、 [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md)クラス、によって挿入された、`coclass`属性。

**スレッド**属性もへのアクセスを保護する[event_source](../windows/event-source.md)します。

## <a name="example"></a>例

参照してください、[ライセンス](../windows/licensed.md)の使用サンプルの例を**スレッド**します。

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**クラス**、**構造体**|
|**反復可能**|いいえ|
|**必要な属性**|**coclass**|
|**無効な属性**|なし|

属性コンテキストの詳細については、「 [属性コンテキスト](../windows/attribute-contexts.md)」を参照してください。

## <a name="see-also"></a>関連項目

[COM 属性](../windows/com-attributes.md)  
[Typedef、Enum、Union、および Struct 型の属性](../windows/typedef-enum-union-and-struct-attributes.md)  
[クラス属性](../windows/class-attributes.md)  
[旧形式のコードのためのマルチスレッド サポート (Visual C++)](../parallel/multithreading-support-for-older-code-visual-cpp.md)  
[ニュートラル アパートメント](http://msdn.microsoft.com/library/windows/desktop/ms681813)  