---
title: Platform::collections Namespace |Microsoft Docs
ms.custom: ''
ms.date: 01/18/2018
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- collection/Platform::Collections
dev_langs:
- C++
helpviewer_keywords:
- Platform::Collections Namespace
ms.assetid: b5042864-5f22-40b7-b7a5-c0691f65cc47
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d872df7294e33ef47247609af4606da842bb6184
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/04/2018
ms.locfileid: "43686548"
---
# <a name="platformcollections-namespace"></a>Platform::Collections 名前空間

Platform::collections 名前空間が含まれています、 `Map`、 `MapView`、 `Vector`、および`VectorView`クラス。 これらのクラスで定義されている対応するインターフェイスの具象実装は、 [:foundation](/uwp/api/Windows.Foundation.Collections)名前空間。 具体的なコレクション型は、(Javascript または C# で書かれたプログラムが C ++ コンポーネントを呼び出すなど) ABI を越えて移植することはできませんが、対応するインターフェイスの型に暗黙的に変換できます。 たとえばを設定してコレクションを返すパブリック メソッドを実装する場合、使用して[platform::collections:](../cppcx/platform-collections-vector-class.md)内部的にコレクションを実装して使用する[:foundation:: IVector](/uwp/api/Windows.Foundation.Collections.IVector_T_)戻り値の型として。 詳細については、次を参照してください。[コレクション](../cppcx/collections-c-cx.md)と[C++ での Windows ランタイム コンポーネントの作成](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)です。

Platform::Collections::Vector は [std::vector](../standard-library/vector-class.md) から構築でき、 [Platform::Collections::Map](../cppcx/platform-collections-map-class.md) は [std::map](../standard-library/map-class.md)から構築できます。

さらに、platform::collections 名前空間は挿入し、入力反復子のサポートを提供し、`Vector`と`VectorView`反復子。

含める必要があります (`#include`) platform::collections 名前空間の型の使用には、collection.h ヘッダー。

## <a name="syntax"></a>構文

```cpp
#include <collection.h>
using namespace Platform::Collections;
```

### <a name="members"></a>メンバー

この名前空間には、次のメンバーが含まれます。

|名前|説明|
|----------|-----------------|
|[Platform::Collections::BackInsertIterator クラス](../cppcx/platform-collections-backinsertiterator-class.md)|コレクションの末尾に要素を挿入する反復子を表します。|
|[Platform::Collections::InputIterator クラス](../cppcx/platform-collections-inputiterator-class.md)|コレクションの先頭に要素を挿入する反復子を表します。|
|[Platform::Collections::Map クラス](../cppcx/platform-collections-map-class.md)|キーによりアクセスされるキーと値のペアの変更可能なコレクションを表します。 [std::map](../standard-library/map-class.md)に似ています。|
|[Platform::Collections::MapView クラス](../cppcx/platform-collections-mapview-class.md)|キーによりアクセスされるキーと値のペアの読み取り専用のコレクションを表します。|
|[Platform::Collections::Vector Class](../cppcx/platform-collections-vector-class.md)|要素の変更可能なシーケンスを表します。 [std::vector](../standard-library/vector-class.md)に似ています。|
|[Platform::Collections::VectorIterator クラス](../cppcx/platform-collections-vectoriterator-class.md)|`Vector` コレクションを走査する反復子を表します。|
|[Platform::Collections::VectorView クラス](../cppcx/platform-collections-vectorview-class.md)|要素の読み取り専用のシーケンスを表します。|
|[Platform::Collections::VectorViewIterator クラス](../cppcx/platform-collections-vectorviewiterator-class.md)|`VectorView` コレクションを走査する反復子を表します。|

## <a name="inheritance-hierarchy"></a>継承階層

[Platform 名前空間](../cppcx/platform-namespace-c-cx.md)

### <a name="requirements"></a>要件

**メタデータ:** platform.winmd

**名前空間:** Platform::Collections

**コンパイラ オプション:** /ZW

## <a name="see-also"></a>関連項目

[プラットフォーム Namespace](../cppcx/platform-namespace-c-cx.md)  
