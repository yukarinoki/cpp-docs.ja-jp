---
title: (C++ COM 属性) のエクスポート |Microsoft Docs
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.export
dev_langs:
- C++
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a636b7d4c943896bcd1e5e7b3580c2d3f7410fc8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791195"
---
# <a name="export"></a>export

.Idl ファイルに配置するデータ構造をによりします。

## <a name="syntax"></a>構文

```cpp
[export]
```

## <a name="remarks"></a>Remarks

**エクスポート**C++ 属性は、.idl ファイルに配置して、ある使用可能な任意の言語で使用できるようにするバイナリ互換性のある形式で、タイプ ライブラリ内のデータ構造をによりします。

適用することはできません、**エクスポート**クラスでは、パブリック メンバーのみが持つ場合でも、属性をクラス (と同等の**構造体**)。

名前のないをエクスポートする場合**enum**または**構造体**で始まる名前を指定、 **_ _unnamed**<em>x</em>ここで、 *x*シーケンシャル番号です。

エクスポートの有効な typedef は、基本型、構造体、共用体、列挙型はか、識別子を入力します。  参照してください[typedef](/windows/desktop/Midl/typedef)詳細についてはします。

## <a name="example"></a>例

次のコードを使用する方法を示しています、**エクスポート**属性。

```cpp
// cpp_attr_ref_export.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```

## <a name="requirements"></a>要件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**共用体**、 **typedef**、 **enum**、**構造体**、または**インターフェイス**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、次を参照してください。[属性コンテキスト](cpp-attributes-com-net.md#contexts)します。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)  