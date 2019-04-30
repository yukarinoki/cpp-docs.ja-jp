---
title: エクスポート (C++ COM 属性)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.export
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
ms.openlocfilehash: 5ffa4283b8a2b265809d06b72be96e217cf8bf9f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409617"
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

## <a name="requirements"></a>必要条件

### <a name="attribute-context"></a>属性コンテキスト

|||
|-|-|
|**対象**|**共用体**、 **typedef**、 **enum**、**構造体**、または**インターフェイス**|
|**反復可能**|いいえ|
|**必要な属性**|なし|
|**無効な属性**|なし|

詳細については、「 [属性コンテキスト](cpp-attributes-com-net.md#contexts)」を参照してください。

## <a name="see-also"></a>関連項目

[コンパイラ属性](compiler-attributes.md)<br/>
[Typedef、Enum、Union、および Struct 型の属性](typedef-enum-union-and-struct-attributes.md)